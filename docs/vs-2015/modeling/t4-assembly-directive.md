---
title: T4 Directive d’Assembly | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 44949749-ce3c-4fb5-8690-a17f1564ac2f
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f81bdcad4f255585c2c554add59ed04dea5872d3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58952671"
---
# <a name="t4-assembly-directive"></a>Directive d'assembly T4
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans un modèle de texte au moment du design [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], la directive `assembly` charge un assembly afin que votre code de modèle puisse utiliser ses types. L'effet est semblable à l'ajout d'une référence d'assembly dans un projet [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 Pour obtenir une vue d’ensemble de l’écriture de modèles de texte, consultez [écriture d’un modèle de texte T4](../modeling/writing-a-t4-text-template.md).  
  
> [!NOTE]
>  Vous n'avez pas besoin de la directive `assembly` dans un modèle de texte au moment de l'exécution (prétraité). Au lieu de cela, ajoutez les assemblys nécessaires à la **références** de votre [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projet.  
  
## <a name="using-the-assembly-directive"></a>Utilisation de la directive d'assembly  
 La syntaxe de la directive est la suivante :  
  
```  
<#@ assembly name="[assembly strong name|assembly file name]" #>  
```  
  
 Le nom d'assembly doit correspondre à l'un des éléments suivants :  
  
- Nom fort d'un assembly dans le GAC, tel que `System.Xml.dll`. Vous pouvez également utiliser la forme longue, telle que `name="System.Xml, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"`. Pour plus d'informations, consultez <xref:System.Reflection.AssemblyName>.  
  
- Chemin d’accès absolu de l’assembly  
  
  Vous pouvez utiliser la syntaxe `$(variableName)` pour référencer des variables [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] telles que `$(SolutionDir)`, et `%VariableName%` pour référencer des variables d'environnement. Exemple :  
  
```  
<#@ assembly name="$(SolutionDir)\MyProject\bin\Debug\SomeLibrary.Dll" #>  
```  
  
 La directive assembly n'a aucun effet dans un modèle de texte prétraité. Au lieu de cela, incluez les références nécessaires dans le **références** section de votre [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projet. Pour plus d’informations, consultez [génération de texte d’exécution avec les modèles de texte T4](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
## <a name="standard-assemblies"></a>Assemblys standard  
 Les assemblys suivants sont chargés automatiquement, afin que vous n'ayez pas besoin d'écrire des directives d'assembly pour eux :  
  
- `Microsoft.VisualStudio.TextTemplating.1*.dll`  
  
- `System.dll`  
  
- `WindowsBase.dll`  
  
  Si vous utilisez une directive personnalisée, le processeur de directive peut charger des assemblys supplémentaires. Par exemple, si vous écrivez des modèles pour un langage spécifique au domaine (DSL), vous n'avez pas besoin d'écrire des directives d'assembly pour les assemblys suivants :  
  
- `Microsoft.VisualStudio.Modeling.Sdk.1*.dll`  
  
- `Microsoft.VisualStudio.Modeling.Sdk.Diagrams.1*.dsl`  
  
- `Microsoft.VisualStudio.TextTemplating.Modeling.1*.dll`  
  
- Assembly contenant votre langage spécifique à un domaine.  
  
##  <a name="msbuild"></a> À l’aide des propriétés du projet dans MSBuild et Visual Studio  
 Les macros Visual Studio telles que $(SolutionDir) ne fonctionnent pas dans MSBuild. Si vous souhaitez transformer les modèles de votre ordinateur de build, vous devez utiliser les propriétés de projet à la place.  
  
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
  
 Maintenant, vous pouvez utiliser votre propriété de projet dans les modèles de texte, lesquels se transforment correctement dans Visual Studio et MSBuild :  
  
```  
<#@ assembly name="$(myLibFolder)\MyLib.dll" #>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Directive d’inclusion T4](../modeling/t4-include-directive.md)
