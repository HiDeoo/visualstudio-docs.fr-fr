---
title: MSBuild | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, about MSBuild
- MSBuild, overview
ms.assetid: e39f13f7-1e1d-4435-95ca-0c222bca071c
caps.latest.revision: 62
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7ac637c478b5bb105b48abeb1d0ec074122e3dda
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68739692"
---
# <a name="msbuild"></a>MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Le [!INCLUDE[vstecmsbuildengine](../includes/vstecmsbuildengine-md.md)] est une plateforme de génération d'applications. Ce moteur, également appelé MSBuild, fournit un schéma XML pour un fichier projet qui contrôle la manière dont la plateforme de génération traite et génère les logiciels. Visual Studio utilise MSBuild, mais il ne dépend pas de Visual Studio. En appelant msbuild.exe sur votre fichier projet ou solution, vous pouvez gérer et générer des produits dans les environnements où Visual Studio n'est pas installé.  
  
 Visual Studio utilise MSBuild pour charger et générer des projets managés. Les fichiers projet dans Visual Studio (.csproj, .vbproj, vcxproj et autres) contiennent le code XML MSBuild qui s'exécute lorsque vous générez un projet à l'aide de l'IDE. Les projets Visual Studio importent tous les paramètres et processus de génération nécessaires pour effectuer le travail de développement classique, mais vous pouvez les développer ou les modifier à partir de Visual Studio ou en utilisant un éditeur XML.  
  
 Pour plus d’informations sur MSBuild pour C++, consultez [MSBuild (Visual C++)](https://msdn.microsoft.com/library/7a1be7ff-0312-4669-adf2-5f5bf507d560).  
  
 Les exemples suivants illustrent les cas où vous pouvez exécuter des builds à l'aide d'une ligne de commande MSBuild au lieu de l'IDE de Visual Studio.  
  
- Visual Studio n'est pas installé.  
  
- Vous souhaitez utiliser la version 64 bits de MSBuild. Cette version MSBuild est généralement inutile, mais elle permet à MSBuild d'accéder à plus de mémoire.  
  
- Vous souhaitez exécuter une build dans plusieurs processus. Toutefois, vous pouvez utiliser l'IDE pour obtenir le même résultat sur les projets dans C++ et C#.  
  
- Vous souhaitez modifier le système de génération. Par exemple, vous pouvez souhaiter effectuer les actions suivantes :  
  
  - Prétraitez les fichiers avant qu'ils n'atteignent le compilateur.  
  
  - Copiez les sorties de génération à un autre emplacement.  
  
  - Créez des fichiers compressés à partir des sorties de génération.  
  
  - Procédez à une étape de post-traitement. Par exemple, vous pouvez souhaiter horodater un assembly avec une version différente.  
  
  Vous pouvez écrire du code dans l'IDE de Visual Studio, mais les générations s'exécutent à l'aide de MSBuild. Autre solution, vous pouvez générer le code dans l'IDE sur un ordinateur de développement mais utiliser une ligne de commande MSBuild pour générer du code qui est intégré par plusieurs développeurs.  
  
> [!NOTE]
> Vous pouvez utiliser Team Foundation Build automatiquement pour compiler, tester, puis déployer votre application. Votre système de génération peut automatiquement exécuter des générations lorsque les développeurs archivent du code (par exemple, dans le cadre d'une stratégie continue d'intégration) ou selon une planification (par exemple, une build nocturne de test de vérification de build). Team Foundation Build compile votre code à l’aide de MSBuild. Pour plus d’informations, consultez l’article [Générer l’application](/azure/devops/pipelines/index).  
  
 Cette rubrique fournit une vue d'ensemble de MSBuild. Pour un didacticiel d’introduction, consultez la [Procédure pas à pas : utilisation de MSBuild](../msbuild/walkthrough-using-msbuild.md).  
  
 **Dans cette rubrique**  
  
- [Utilisation de MSBuild dans une invite de commandes](#BKMK_CommandPrompt)  
  
- [Fichier projet](#BKMK_ProjectFile)  
  
  - [Propriétés](#BKMK_Properties)  

  - [Éléments](#BKMK_Items)  

  - [Tâches](#BKMK_Tasks)  

  - [Cibles](#BKMK_Targets)  

- [Journaux de génération](#BKMK_BuildLogs)  
  
- [Utilisation de MSBuild dans Visual Studio](#BKMK_VisualStudio)  
  
- [MULTICIBLAGE](#BKMK_Multitargeting)  
  
## <a name="using-msbuild-at-a-command-prompt"></a><a name="BKMK_CommandPrompt"></a> Utilisation de MSBuild dans une invite de commandes  
 Pour exécuter [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] à partir d’une invite de commandes, transmettez un fichier projet à MSBuild.exe, avec les options de ligne de commande appropriées. Les options de ligne de commande vous permettent de définir des propriétés, d'exécuter des cibles spécifiques et de définir d'autres options qui contrôlent le processus de génération. Par exemple, vous utilisez la syntaxe de ligne de commande suivante pour générer le fichier `MyProj.proj` avec la propriété `Configuration` ayant `Debug` comme valeur.  
  
```  
MSBuild.exe MyProj.proj /property:Configuration=Debug  
```  
  
 Pour plus d’informations sur les options de ligne de commande [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)], consultez l’article [Command-Line Reference (Informations de référence sur la ligne de commande MSBuild)](../msbuild/msbuild-command-line-reference.md).  
  
> [!IMPORTANT]
> Avant de télécharger un projet, déterminez la crédibilité du code.  
  
## <a name="project-file"></a><a name="BKMK_ProjectFile"></a> Fichier projet  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] utilise un format de fichier projet XML qui est simple et extensible. Le format du fichier projet [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] permet aux développeurs de décrire les éléments qui seront générés et la manière dont ils le seront pour différents systèmes d’exploitation et configurations. De plus, le format de fichier projet permet aux développeurs de créer des règles de génération réutilisables qui peuvent être réparties en fichiers distincts, de telle sorte que les builds puissent être exécutées de façon cohérente sur différents projets du produit.  
  
 Les sections suivantes décrivent certains éléments de base du format de fichier projet [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]. Pour suivre un didacticiel sur la création d’un fichier projet de base, consultez la [Procédure pas à pas : création d’un fichier projet MSBuild en partant de zéro](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md).  
  
### <a name="properties"></a><a name="BKMK_Properties"></a> Propriétés  
 Les propriétés sont des paires clé/valeur qui peuvent être utilisées pour configurer les générations. Les propriétés sont déclarées en créant un élément portant le nom de la propriété comme enfant d’un élément [PropertyGroup](../msbuild/propertygroup-element-msbuild.md). Par exemple, le code suivant crée une propriété nommée `BuildDir` avec la valeur `Build`.  
  
```  
<PropertyGroup>  
    <BuildDir>Build</BuildDir>  
</PropertyGroup>  
```  
  
 Vous pouvez définir une propriété conditionnellement en plaçant un attribut `Condition` dans l'élément. Le contenu des éléments conditionnels est ignoré, à moins que la condition ait la valeur `true`. Dans l'exemple suivant, l'élément `Configuration` est défini s'il n'a pas encore été défini.  
  
```  
<Configuration  Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
```  
  
 Les propriétés sont référencées dans tout le fichier projet à l’aide de la syntaxe $(*PropertyName*). Par exemple, vous pouvez référencer les propriétés dans les exemples précédents en utilisant `$(BuildDir)` et `$(Configuration)`.  
  
 Pour plus d’informations sur les propriétés, consultez [propriétés MSBuild](msbuild-properties1.md).  
  
### <a name="items"></a><a name="BKMK_Items"></a> Contenus  
 Les éléments sont des entrées du système de génération qui représentent généralement des fichiers. Les éléments sont groupés dans différents types d'élément, selon leurs noms d'élément définis par l'utilisateur. Ces types d’éléments peuvent être utilisés comme paramètres des tâches, lesquelles utilisent les éléments pour exécuter les étapes du processus de génération.  
  
 Les éléments sont déclarés dans le fichier projet en créant un élément avec le nom du type d’élément comme enfant d’un élément [ItemGroup](../msbuild/itemgroup-element-msbuild.md). Par exemple, le code suivant crée un type d'élément nommé `Compile` et composé de deux fichiers.  
  
```  
<ItemGroup>  
    <Compile Include = "file1.cs"/>  
    <Compile Include = "file2.cs"/>  
</ItemGroup>  
```  
  
 Les types d’élément peuvent être référencés dans tout le fichier projet à l’aide de la syntaxe @(*ItemType*). Par exemple, le type d'élément dans l'exemple serait référencé avec la syntaxe `@(Compile)`.  
  
 Dans MSBuild, les noms d'éléments et des attributs respectent la casse. En revanche, ce n'est pas le cas pour les noms de propriétés, d'items et de métadonnées. L'exemple suivant crée le type d'élément `Compile`, `comPile` ou toute autre variation au niveau de la casse, et la valeur « one.cs;two.cs » est affectée au type d'item.  
  
```  
<ItemGroup>  
  <Compile Include="one.cs" />  
  <comPile Include="two.cs" />  
</ItemGroup>  
```  
  
 Les éléments peuvent être déclarés à l'aide de caractères génériques et peuvent contenir des métadonnées supplémentaires dans le cas de scénarios de génération plus avancés. Pour plus d’informations sur les éléments, consultez l’article [Éléments MSBuild](../msbuild/msbuild-items.md).  
  
### <a name="tasks"></a><a name="BKMK_Tasks"></a> Tâches  
 Les tâches sont des unités de code exécutable auxquelles les projets [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] ont recours pour exécuter des opérations de génération. Par exemple, une tâche peut compiler des fichiers d'entrée ou exécuter un outil externe. Les tâches peuvent être réutilisées et partagées par plusieurs développeurs dans différents projets.  
  
 La logique d’exécution d’une tâche est écrite en code managé et mappée à [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] avec l’élément [UsingTask](../msbuild/usingtask-element-msbuild.md). Vous pouvez écrire votre propre tâche en créant un type managé qui implémente l'interface <xref:Microsoft.Build.Framework.ITask>. Pour plus d’informations sur l’écriture de tâches, consultez l’article [Task Writing (Écriture de tâches)](../msbuild/task-writing.md).  
  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] inclut des tâches communes que vous pouvez modifier pour les adapter à vos spécifications.  Voici des exemples : [Copy](../msbuild/copy-task.md), qui copie des fichiers, [MakeDir](../msbuild/makedir-task.md), qui crée des répertoires et [Csc](../msbuild/csc-task.md), qui compile des fichiers de code source Visual C#. Pour obtenir la liste des tâches disponibles avec les informations sur leur utilisation, consultez l’article [Task Reference (Informations de référence sur les tâches MSBuild)](../msbuild/msbuild-task-reference.md).  
  
 Une tâche est exécutée dans un fichier projet [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] en créant un élément avec le nom de la tâche comme enfant d’un élément [Target](../msbuild/target-element-msbuild.md). En général, les tâches acceptent les paramètres passés comme des attributs de l’élément. Les propriétés et les éléments [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] peuvent être utilisés comme des paramètres. Par exemple, le code suivant appelle la tâche [MakeDir](../msbuild/makedir-task.md) et lui transmet la valeur de la propriété `BuildDir` déclarée dans l’exemple précédent.  
  
```  
<Target Name="MakeBuildDirectory">  
    <MakeDir  Directories="$(BuildDir)" />  
</Target>  
```  
  
 Pour plus d’informations sur les tâches, consultez l’article [Tâches MSBuild](../msbuild/msbuild-tasks.md).  
  
### <a name="targets"></a><a name="BKMK_Targets"></a> Compilé  
 Les cibles regroupent les tâches selon un ordre particulier et exposent les sections du fichier projet comme points d’entrée du processus de génération. Les cibles sont souvent groupées en sections logiques afin d'accroître la lisibilité et de permettre une expansion. L'éclatement des étapes de génération en plusieurs cibles permet d'appeler une partie du processus de génération à partir d'autres cibles sans copier cette section de code dans chaque cible. Par exemple, si plusieurs points d'entrée du processus de génération requièrent la génération de références, vous pouvez créer une cible qui génère les références et exécuter cette cible à partir de chaque point d'entrée nécessaire.  
  
 Les cibles sont déclarées dans le fichier projet avec l’élément [Target](../msbuild/target-element-msbuild.md). Par exemple, le code suivant crée une cible nommée `Compile`, qui appelle ensuite la tâche [Csc](../msbuild/csc-task.md) comportant la liste d’éléments déclarée dans l’exemple précédent.  
  
```  
<Target Name="Compile">  
    <Csc Sources="@(Compile)" />  
</Target>  
```  
  
 Dans des scénarios plus avancés, les cibles peuvent être utilisées pour décrire les relations entre chacune d'elles et exécuter une analyse de dépendance, qui permet d'ignorer des sections entières du processus de génération si la cible correspondante est à jour. Pour plus d’informations sur les cibles, consultez l’article [Targets (Cibles MSBuild)](../msbuild/msbuild-targets.md).  
  
## <a name="build-logs"></a><a name="BKMK_BuildLogs"></a> Journaux de génération  
 Vous pouvez consigner les erreurs de build, les avertissements et les messages dans la console ou un autre périphérique de sortie. Pour plus d’informations, consultez les articles [Obtention de journaux de génération avec MSBuild](../msbuild/obtaining-build-logs-with-msbuild.md) et [Journalisation dans MSBuild](../msbuild/logging-in-msbuild.md).  
  
## <a name="using-msbuild-in-visual-studio"></a><a name="BKMK_VisualStudio"></a> Utilisation de MSBuild dans Visual Studio  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] utilise le format de fichier projet [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] pour stocker les informations de génération des projets managés. Les paramètres de projet ajoutés ou modifiés à l’aide de l’interface [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] sont répercutés dans le fichier .*proj généré pour chaque projet. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] utilise une instance hébergée de [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] pour générer des projets managés. Cela signifie qu’un projet managé peut être généré dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ou à partir d’une invite de commandes (même si [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] n’est pas installé) ; les résultats seront identiques.  
  
 Pour suivre un didacticiel sur l’utilisation de MSBuild dans Visual Studio, consultez la [Procédure pas à pas : utilisation de MSBuild](../msbuild/walkthrough-using-msbuild.md).  
  
## <a name="multitargeting"></a><a name="BKMK_Multitargeting"></a> MULTICIBLAGE  
 Visual Studio vous permet de compiler une application pour l'exécuter sur n'importe quelle version du .NET Framework. Par exemple, vous pouvez compiler une application qui s'exécutera sur le .NET Framework version 2.0 sur une plateforme 32 bits, et vous pouvez compiler la même application pour qu'elle s'exécute sur le .NET Framework version 4.5 sur une plateforme 64 bits. Le multi-ciblage désigne la possibilité de compiler en plusieurs Frameworks.  
  
 Voici une partie des avantages offerts par le multi-ciblage :  
  
- Vous pouvez développer des applications qui ciblent des versions antérieures du .NET Framework (par exemple, les versions 2.0, 3.0 et 3.5).  
  
- Vous pouvez cibler des Frameworks autres que le .NET Framework (par exemple, Silverlight).  
  
- Vous pouvez cibler un *profil Framework*, qui est un sous-ensemble prédéfini d’une version cible de .NET Framework.  
  
- Si un service pack pour la version actuelle du .NET Framework est publié, vous pouvez le cibler.  
  
- Le multi-ciblage garantit qu'une application utilise uniquement les fonctionnalités qui sont disponibles dans le framework et la plateforme cibles.  
  
  Pour plus d’informations, consultez l’article [Multiciblage de MSBuild](../msbuild/msbuild-multitargeting-overview.md).  
  
## <a name="related-topics"></a>Rubriques connexes  
  
|Intitulé|Description|  
|-----------|-----------------|  
|[Procédure pas à pas : création d’un fichier projet MSBuild en partant de zéro](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)|Indique comment créer de façon incrémentielle un fichier projet de base, en utilisant uniquement un éditeur de texte.|  
|[Procédure pas à pas : Utilisation de MSBuild](../msbuild/walkthrough-using-msbuild.md)|Présente les composantes de MSBuild et indique comment écrire, manipuler et déboguer des projets MSBuild sans fermer l'IDE de Visual Studio.|  
|[Concepts MSBuild](../msbuild/msbuild-concepts.md)|Présente les quatre composantes de MSBuild : propriétés, éléments, cibles et tâches.|  
|[Éléments](../msbuild/msbuild-items.md)|Décrit les concepts généraux sous-jacents au format de fichier [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] et la manière dont les éléments s'ajustent les uns aux autres.|  
|[Propriétés MSBuild](msbuild-properties1.md)|Présente les propriétés et les collections de propriétés. Les propriétés sont des paires clé/valeur qui peuvent être utilisées pour configurer les générations.|  
|[Cibles](../msbuild/msbuild-targets.md)|Explique comment grouper les tâches dans un ordre particulier et autoriser des sections du processus de génération à être appelées sur la ligne de commande.|  
|[Tâches](../msbuild/msbuild-tasks.md)|Indique comment créer une unité de code exécutable qui peut être utilisée par [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] afin d'exécuter des opérations de génération atomiques.|  
|[Conditions](../msbuild/msbuild-conditions.md)|Explique comment utiliser l'attribut `Condition` dans un élément MSBuild.|  
|[Concepts avancés](../msbuild/msbuild-advanced-concepts.md)|Présente le traitement par lot, l'exécution de transformations, le multiciblage, ainsi que d'autres techniques avancées.|  
|[Journalisation dans MSBuild](../msbuild/logging-in-msbuild.md)|Décrit comment consigner des événements, des messages et des erreurs de build.|  
|[Ressources supplémentaires](../msbuild/additional-msbuild-resources.md)|Répertorie les ressources de communauté et de prise en charge pour des informations supplémentaires sur MSBuild.|  
  
## <a name="reference"></a>Informations de référence  
 [Référence MSBuild](../msbuild/msbuild-reference.md)  
 Renvoie aux rubriques contenant les informations de référence.  
  
 Glossaire  
 Définit les termes courants relatifs à MSBuild.
