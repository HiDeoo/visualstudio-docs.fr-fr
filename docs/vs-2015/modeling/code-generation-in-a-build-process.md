---
title: Génération de code dans un processus de génération | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, build tasks
- text templates, transforming by using msbuild
ms.assetid: 4da43429-2a11-4d7e-b2e0-9e4af7033b5a
caps.latest.revision: 30
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: ce072f85873530d419589f0d1830dc76688afa5c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47503960"
---
# <a name="code-generation-in-a-build-process"></a>Génération de code dans un processus de génération
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [génération de Code dans un processus de génération](https://docs.microsoft.com/visualstudio/modeling/code-generation-in-a-build-process).

Transformation de texte peut être appelée dans le cadre du processus de génération d’une solution Visual Studio. Il existe des tâches de génération qui sont spécialisées pour la transformation de texte. Les tâches de génération T4 exécutent les modèles de texte au moment du design. En outre, elles compilent les modèles de texte (prétraités) au moment de l'exécution.

Il existe quelques différences en matière de possibilités offertes par les tâches de génération, selon le moteur de génération que vous utilisez. Lorsque vous générez la solution dans Visual Studio, un modèle de texte peut accéder à l’API Visual Studio (EnvDTE) si le [hostspecific = « true »](../modeling/t4-template-directive.md) attribut est défini. Mais cela n'est pas vrai lorsque vous générez la solution à partir de la ligne de commande ou lorsque vous démarrez une génération serveur via Visual Studio. Dans ces situations, la génération est exécutée par MSBuild et un autre hôte T4 est utilisé.

Cela signifie que vous ne pouvez pas accéder aux éléments tels que les noms de fichiers projet de la même manière lorsque vous générez un modèle de texte dans MSBuild. Toutefois, vous pouvez [passer des informations sur l’environnement dans les modèles de texte et les processeurs de directive à l’aide des paramètres de build](#parameters).

##  <a name="buildserver"></a> Configurer vos ordinateurs

Pour activer les tâches de génération sur votre ordinateur de développement, installez [Modeling SDK pour Visual Studio](http://www.microsoft.com/download/details.aspx?id=40754).

Si [votre serveur de builds](http://msdn.microsoft.com/library/788443c3-0547-452e-959c-4805573813a9) s’exécute sur un ordinateur sur lequel Visual Studio n’est pas installé, copiez les fichiers suivants sur l’ordinateur de build à partir de votre ordinateur de développement. Remplacez ‘*’ par les numéros de version les plus récents.

-   $(ProgramFiles)\MSBuild\Microsoft\VisualStudio\v*.0\TextTemplating

    -   Microsoft.VisualStudio.TextTemplating.Sdk.Host.*.0.dll

    -   Microsoft.TextTemplating.Build.Tasks.dll

    -   Microsoft.TextTemplating.targets

-   $(ProgramFiles)\Microsoft Visual Studio *.0\VSSDK\VisualStudioIntegration\Common\Assemblies\v4.0

    -   Microsoft.VisualStudio.TextTemplating.*.0.dll

    -   Microsoft.VisualStudio.TextTemplating.Interfaces.*.0.dll (plusieurs fichiers)

    -   Microsoft.VisualStudio.TextTemplating.VSHost.*.0.dll

-   $(ProgramFiles)\Microsoft Visual Studio *.0\Common7\IDE\PublicAssemblies\

    -   Microsoft.VisualStudio.TextTemplating.Modeling.*.0.dll

## <a name="to-edit-the-project-file"></a>Pour modifier le fichier projet

Vous devrez modifier votre fichier projet pour configurer certaines fonctionnalités dans MSBuild.

Dans l’Explorateur de solutions, choisissez **Unload** dans le menu contextuel de votre projet. Cela vous permet de modifier le fichier .csproj ou .vbproj dans l'éditeur XML.

Lorsque vous avez terminé la modification, choisissez **recharger**.

## <a name="import-the-text-transformation-targets"></a>Importation des cibles de la transformation de texte

Dans le fichier .vbproj ou .csproj, recherchez une ligne telle que :

`<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />`

\- ou -

`<Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />`

Après cette ligne, insérez l'importation de modèles de texte :

```xml
<!-- Optionally make the import portable across VS versions -->
  <PropertyGroup>
    <!-- Get the Visual Studio version – defaults to 10: -->
    <VisualStudioVersion Condition="'$(VisualStudioVersion)' == ''">10.0</VisualStudioVersion>
    <!-- Keep the next element all on one line: -->
    <VSToolsPath Condition="'$(VSToolsPath)' == ''">$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)</VSToolsPath>
  </PropertyGroup>

<!-- This is the important line: -->
  <Import Project="$(VSToolsPath)\TextTemplating\Microsoft.TextTemplating.targets" />
```

## <a name="transforming-templates-in-a-build"></a>Transformation des modèles d'une build

Il existe des propriétés que vous pouvez insérer dans votre fichier projet afin de contrôler la tâche de transformation :

-   Exécutez la tâche de transformation au début de chaque génération :

    ```xml
    <PropertyGroup>
        <TransformOnBuild>true</TransformOnBuild>
    </PropertyGroup>
    ```

-   Remplacez les fichiers en lecture seule, par exemple, car ils ne sont pas vérifiés :

    ```xml
    <PropertyGroup>
        <OverwriteReadOnlyOutputFiles>true</OverwriteReadOnlyOutputFiles>
    </PropertyGroup>
    ```

-   Transformez chaque modèle à chaque fois :

    ```xml
    <PropertyGroup>
        <TransformOutOfDateOnly>false</TransformOutOfDateOnly>
    </PropertyGroup>
    ```

     Par défaut, la tâche T4 MSBuild régénère un fichier de sortie s'il est antérieur à son fichier modèle, aux fichiers inclus ou aux fichiers qui ont été précédemment lus par le modèle ou par un processeur de directive qu'il utilise. Notez qu'il s'agit d'un test de dépendance beaucoup plus puissant que celui de la commande Transformer tous les modèles dans Visual Studio. Ce dernier ne fait que comparer les dates du fichier modèle et du fichier de sortie.

Pour exécuter uniquement les transformations de texte dans votre projet, appelez la tâche TransformAll :

`msbuild myProject.csproj /t:TransformAll`

Pour transformer un modèle de texte spécifique :

`msbuild myProject.csproj /t:Transform /p:TransformFile="Template1.tt"`

Vous pouvez utiliser des caractères génériques dans TransformFile :

`msbuild dsl.csproj /t:Transform /p:TransformFile="GeneratedCode\**\*.tt"`

## <a name="source-control"></a>Contrôle de code source

Il n'existe aucune intégration prédéfinie spécifique avec un système de contrôle de code source. Toutefois, vous pouvez ajouter vos propres extensions, par exemple pour extraire et archiver un fichier généré. Par défaut, la tâche de transformation de texte évite de remplacer un fichier en lecture seule. Lorsqu'un tel fichier est trouvé, une erreur est journalisée dans la liste d'erreurs de Visual Studio, et la tâche échoue.

Pour spécifier que les fichiers en lecture seule doivent être remplacés, insérez la propriété suivante :

`<OverwriteReadOnlyOuputFiles>true</OverwriteReadOnlyOuputFiles>`

À moins que vous ne personnalisiez l'étape de post-traitement, un avertissement sera consigné dans la liste d'erreurs lorsqu'un fichier est remplacé.

## <a name="customizing-the-build-process"></a>Personnalisation du processus de génération

La transformation de texte se produit avant les autres tâches du processus de génération. Pour définir les tâches appelées avant et après la transformation, définissez les propriétés `$(BeforeTransform)` et `$(AfterTransform)` :

```xml
<PropertyGroup>
    <BeforeTransform>CustomPreTransform</BeforeTransform>
    <AfterTransform>CustomPostTransform</AfterTransform>
  </PropertyGroup>
  <Target Name="CustomPreTransform">
    <Message Text="In CustomPreTransform..." Importance="High" />
  </Target>
  <Target Name="CustomPostTransform">
    <Message Text="In CustomPostTransform..." Importance="High" />
  </Target>
```

Dans `AfterTransform`, vous pouvez référencer des listes de fichiers :

-   GeneratedFiles : liste des fichiers écrits par le processus. Pour les fichiers qui ont remplacé des fichiers en lecture seule existants, %(GeneratedFiles.ReadOnlyFileOverwritten) a la valeur true. Ces fichiers peuvent être extraits du contrôle de code source.

-   NonGeneratedFiles : liste des fichiers en lecture seule qui n'ont pas été remplacés.

 Par exemple, vous définissez une tâche afin d'extraire GeneratedFiles.

## <a name="outputfilepath-and-outputfilename"></a>OutputFilePath et OutputFileName

Ces propriétés sont utilisées uniquement par MSBuild. Elles n'affectent pas la génération du code dans Visual Studio. Elles redirigent le fichier de sortie généré vers un autre dossier ou fichier. Le dossier cible doit déjà exister.

```xml
<ItemGroup>
  <None Include="MyTemplate.tt">
    <Generator>TextTemplatingFileGenerator</Generator>
    <OutputFilePath>MyFolder</OutputFilePath>
    <LastGenOutput>MyTemplate.cs</LastGenOutput>
  </None>
</ItemGroup>
```

`$(IntermediateOutputPath).` est un dossier utile pour la redirection

Si vous spécifiez un nom de fichier de sortie, il est prioritaire par rapport à l'extension spécifiée dans la directive de sortie des modèles.

```xml
<ItemGroup>
  <None Include="MyTemplate.tt">
    <Generator>TextTemplatingFileGenerator</Generator>
    <OutputFileName>MyOutputFileName.cs</OutputFileName>
    <LastGenOutput>MyTemplate.cs</LastGenOutput>
  </None>
</ItemGroup>
```

Il est déconseillé de spécifier OutputFileName ou OutputFilePath si vous transformez également des modèles dans Visual Studio via la commande Transformer tous les modèles, ou si vous exécutez le générateur de fichier unique. Vous obtiendrez des chemins d'accès de fichiers distincts selon la façon dont vous avez déclenché la transformation. Cela peut vraiment prêter à confusion.

## <a name="adding-reference-and-include-paths"></a>Ajout de chemins d'accès des références et Include

L'hôte possède un ensemble de chemins d'accès par défaut dans lesquels il recherche les assemblys référencés dans les modèles. Pour effectuer un ajout à cet ensemble :

```
<ItemGroup>
    <T4ReferencePath Include="$(VsIdePath)PublicAssemblies\" />
    <!-- Add more T4ReferencePath items here -->
</ItemGroup>
```

Pour définir les dossiers où rechercher les fichiers Include, fournissez une liste d'éléments délimités par des points-virgules. Généralement, vous effectuez l’ajout à la liste des dossiers existants.

```
<PropertyGroup>
    <IncludeFolders>
$(IncludeFolders);$(MSBuildProjectDirectory)\Include;AnotherFolder;And\Another</IncludeFolders>
</PropertyGroup>
```

##  <a name="parameters"></a> Passer des données de contexte de build dans les modèles

Vous pouvez définir des valeurs de paramètre dans le fichier projet. Par exemple, vous pouvez passer des propriétés de build et [variables d’environnement](../msbuild/how-to-use-environment-variables-in-a-build.md):

```xml
<ItemGroup>
  <T4ParameterValues Include="ProjectFolder">
    <Value>$(ProjectDir)</Value>
    <Visible>false</Visible>
  </T4ParameterValues>
</ItemGroup>
```

Dans un modèle de texte, définissez `hostspecific` dans la directive de modèle. Utilisez le [paramètre](../modeling/t4-parameter-directive.md) directive pour obtenir les valeurs :

```
<#@template language="c#" hostspecific="true"#>
<#@ parameter type="System.String" name="ProjectFolder" #>
The project folder is: <#= ProjectFolder #>
```

##  <a name="msbuild"></a> À l’aide des propriétés du projet dans l’assembly et directives #include

Les macros Visual Studio telles que $(SolutionDir) ne fonctionnent pas dans MSBuild. Vous pouvez utiliser des propriétés de projet à la place.

Modifiez votre fichier projet .csproj ou .vbproj pour définir une propriété de projet. Cet exemple définit une propriété nommée `myLibFolder` :

```xml
<!-- Define a project property, myLibFolder: -->
<PropertyGroup>
    <myLibFolder>$(MSBuildProjectDirectory)\..\libs</myLibFolder>
</PropertyGroup>

<!-- Tell the MSBuild T4 task to make the property available: -->
<ItemGroup>
    <T4ParameterValues Include="myLibFolder">
      <Value>$(myLibFolder)</Value>
    </T4ParameterValues>
  </ItemGroup>

```

Désormais, vous pouvez utiliser votre propriété de projet dans les directives d'assembly et Include :

```
<#@ assembly name="$(myLibFolder)\MyLib.dll" #>
<#@ include file="$(myLibFolder)\MyIncludeFile.t4" #>
```

 Ces directives obtiennent des valeurs à partir de T4parameterValues dans MSBuild et les hôtes Visual Studio.

## <a name="q--a"></a>Questions et réponses

**Pourquoi devrais-je transformer les modèles dans le serveur de builds ? J’ai déjà transformé des modèles dans Visual Studio avant d’archiver mon code.**

Si vous mettez à jour un fichier inclus ou tout autre fichier lu par le modèle, Visual Studio ne transforme pas le fichier automatiquement. La transformation des modèles dans le cadre de la build permet de s'assurer que tout est à jour.

**Ce que sont les autres options pour la transformation de modèles de texte ?**

-   Le [utilitaire TextTransform](../modeling/generating-files-with-the-texttransform-utility.md) peut être utilisée dans les scripts de commande. Dans la plupart des cas, il est plus facile d'utiliser MSBuild.

-   [Appel d’une transformation de texte dans une extension VS](../modeling/invoking-text-transformation-in-a-vs-extension.md)

-   [Les modèles de texte au moment du design](../modeling/design-time-code-generation-by-using-t4-text-templates.md) sont transformés par Visual Studio.

-   [Modèles de texte d’exécution](../modeling/run-time-text-generation-with-t4-text-templates.md) sont transformés en cours d’exécution dans votre application.

## <a name="read-more"></a>En lire plus

Vous trouverez de bons conseils dans le modèle T4 MSbuild, $(VSToolsPath)\TextTemplating\Microsoft.TextTemplating.targets

- [Écriture d’un modèle de texte T4](../modeling/writing-a-t4-text-template.md)
- [Visual Studio Visualization and Modeling SDK](http://go.microsoft.com/fwlink/?LinkID=185579)
- [Oleg Sych : Présentation de T4 : intégration](http://www.olegsych.com/2010/04/understanding-t4-msbuild-integration/)