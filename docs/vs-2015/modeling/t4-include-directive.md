---
title: Directive include T4 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 8c3de9f3-755a-47c5-a30a-65717dcaaac2
caps.latest.revision: 8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 669be50e11d3bf17d617c361b63f807149dbc823
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72658583"
---
# <a name="t4-include-directive"></a>Directive d'inclusion T4
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans un modèle de texte dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], vous pouvez inclure du texte d'un autre fichier à l'aide d'une directive `<#@include#>`. Vous pouvez placer les directives `include` n'importe où dans un modèle de texte avant le premier bloc de fonctionnalité de classe `<#+ ... #>`. Les fichiers inclus peuvent également contenir des directives `include` et d'autres directives. Cela vous permet de partager du code de modèle et du texte réutilisable entre les modèles.

## <a name="using-include-directives"></a>Utilisation de directives Include

```
<#@ include file="filePath" [once="true"] #>
```

- `filePath` peut être absolu ou relatif au fichier de modèle actuel.

   De plus, les extensions [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] spécifiques peuvent spécifier leurs propres répertoires dans lesquels rechercher des fichiers Include. Par exemple, lorsque vous avez installé le kit de développement logiciel (SDK) de visualisation et de modélisation (outils DSL), le dossier suivant est ajouté à la liste d’inclusion : `Program Files\Microsoft Visual Studio 10.0\Common7\IDE\Extensions\Microsoft\DSL SDK\DSL Designer\11.0\TextTemplates` .

   Ces dossiers d'inclusion supplémentaires peuvent dépendre de l'extension du fichier d'inclusion. Par exemple, le dossier d’inclusion des outils DSL est uniquement accessible aux fichiers d’inclusion ayant l’extension de fichier `.tt`

- `filePath` peut inclure des variables d'environnement délimitées par "%". Par exemple :

  ```
  <#@ include file="%HOMEPATH%\MyIncludeFile.t4" #>
  ```

- Le nom d’un fichier inclus n’a pas à utiliser l’extension `".tt"`.

   Vous pouvez utiliser une autre extension telle que `".t4"` pour les fichiers inclus. En effet, lorsque vous ajoutez un `.tt` fichier à un projet, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] affecte automatiquement à sa propriété **outil personnalisé** la valeur `TextTemplatingFileGenerator` . En général, vous ne souhaitez pas que les fichiers inclus soient transformés individuellement.

   D'un autre côté, vous devez savoir que dans certains cas, l'extension de fichier affecte les dossiers supplémentaires dans lesquels seront recherchés les fichiers Include. Cela peut être important lorsque vous possédez un fichier inclus qui contient d'autres fichiers.

- Le contenu inclus est traité presque comme s'il faisait partie du modèle de texte d'inclusion. Toutefois, vous pouvez inclure un fichier qui contient un bloc de fonctionnalité de classe `<#+...#>` même si la directive `include` est suivie de texte ordinaire et de blocs de contrôle standard.

- Utilisez `once="true"` pour vous assurer qu'un modèle est inclus une seule fois, même s'il est appelé par plusieurs autres fichiers include.

   Grâce à cette fonctionnalité, il est facile de créer une bibliothèque d’extraits de code T4 réutilisables que vous pouvez inclure dans, sans vous soucier que d’autres extraits de code les ont déjà inclus.  Par exemple, supposons que vous ayez une bibliothèque d’extraits de code très affinés qui traitent du traitement des modèles et de la génération en C#.  À leur tour, elles sont utilisées par d’autres utilitaires spécifiques à la tâche, tels que la génération d’exceptions, que vous pouvez ensuite utiliser à partir d’autres modèles spécifiques à l’application. Si vous dessinez le graphique de dépendance, vous constatez que certains extraits de code sont inclus plusieurs fois. Mais le paramètre `once` empêche les inclusions suivantes.

  **MyTextTemplate.tt :**

```
<#@ output extension=".txt" #>
Output message 1 (from top template).
<#@ include file="TextFile1.t4"#>
Output message 5 (from top template).
<#
   GenerateMessage(6); // defined in TextFile1.t4
   AnotherGenerateMessage(7); // defined in TextFile2.t4
#>

```

 **TextFile1.t4 :**

```
   Output Message 2 (from included file).
<#@include file="TextFile2.t4" #>
   Output Message 4 (from included file).
<#+ // Start of class feature control block.
void GenerateMessage(int n)
{
#>
   Output Message <#= n #> (from GenerateMessage method).
<#+
}
#>

```

 **TextFile2.t4 :**

```
        Output Message 3 (from included file 2).
<#+ // Start of class feature control block.
void AnotherGenerateMessage(int n)
{
#>
       Output Message <#= n #> (from AnotherGenerateMessage method).
<#+
}
#>

```

 **Fichier généré résultant, MyTextTemplate.txt :**

```
Output message 1 (from top template).
   Output Message 2 (from included file).
        Output Message 3 (from included file 2).

   Output Message 4 (from included file).

Output message 5 (from top template).
   Output Message 6 (from GenerateMessage method).
       Output Message 7 (from AnotherGenerateMessage method).

```

## <a name="using-project-properties-in-msbuild-and-visual-studio"></a><a name="msbuild"></a> Utilisation des propriétés de projet dans MSBuild et Visual Studio
 Bien que vous puissiez utiliser des macros Visual Studio telles que $(SolutionDir) dans une directive Include, celles-ci ne s'exécutent pas dans MSBuild. Si vous souhaitez transformer les modèles de votre ordinateur de build, vous devez utiliser les propriétés de projet à la place.

 Modifiez votre fichier projet .csproj ou .vbproj pour définir une propriété de projet. Cet exemple définit une propriété nommée `myIncludeFolder` :

```xml
<!-- Define a project property, myIncludeFolder: -->
<PropertyGroup>
    <myIncludeFolder>$(MSBuildProjectDirectory)\..\libs</myIncludeFolder>
</PropertyGroup>

<!-- Tell the MSBuild T4 task to make the property available: -->
<ItemGroup>
    <T4ParameterValues Include="myIncludeFolder">
      <Value>$(myIncludeFolder)</Value>
    </T4ParameterValues>
  </ItemGroup>

```

 Maintenant, vous pouvez utiliser votre propriété de projet dans les modèles de texte, lesquels se transforment correctement dans Visual Studio et MSBuild :

```
<#@ include file="$(myIncludeFolder)\defs.tt" #>
```
