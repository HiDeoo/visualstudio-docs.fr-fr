---
title: 'Comment : utiliser des variables d’environnement dans une génération | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- environment variables, referencing
- projects [.NET Framework], environment variables
- MSBuild, environment variables
ms.assetid: 7f9e4469-8865-4b59-aab3-3ff26bd36e77
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2f5afe7f58e85b1ddfc5671b635d4df7fad3bd3
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39078239"
---
# <a name="how-to-use-environment-variables-in-a-build"></a>Guide pratique pour utiliser des variables d’environnement dans une build
Lorsque vous générez des projets, il est souvent nécessaire de définir des options de génération à l’aide des informations qui ne figurent pas dans le fichier projet ou dans les fichiers qui composent votre projet. Ces informations sont généralement stockées dans les variables d’environnement.  
  
## <a name="reference-environment-variables"></a>Référencer des variables d’environnement  
 Toutes les variables d’environnement sont disponibles pour le fichier projet [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]) en tant que propriétés.  
  
> [!NOTE]
>  Si le fichier projet contient une définition explicite d’une propriété qui porte le même nom qu’une variable d’environnement, la propriété du fichier projet remplace la valeur de la variable d’environnement.  
  
#### <a name="to-use-an-environment-variable-in-an-msbuild-project"></a>Pour utiliser une variable d’environnement dans un projet MSBuild  
  
-   Référencez la variable d’environnement comme vous le feriez pour une variable déclarée dans votre fichier projet. Par exemple, le code suivant référence la variable d’environnement BIN_PATH :  
  
     `<FinalOutput>$(BIN_PATH)\MyAssembly.dll</FinalOutput>`  
  
 Vous pouvez utiliser un attribut `Condition` pour fournir la valeur par défaut d’une propriété si la variable d’environnement n’a pas été définie.  
  
#### <a name="to-provide-a-default-value-for-a-property"></a>Pour fournir la valeur par défaut d’une propriété  
  
-   Utilisez un attribut `Condition` dans une propriété pour définir la valeur uniquement si la propriété n’a aucune valeur. Par exemple, le code suivant définit la propriété `ToolsPath` sur *c:\tools* uniquement si la variable d’environnement `ToolsPath` n’est pas définie :  
  
     `<ToolsPath Condition="'$(TOOLSPATH)' == ''">c:\tools</ToolsPath>`  
  
    > [!NOTE]
    >  Comme les noms de propriété ne respectent pas la casse, `$(ToolsPath)` et `$(TOOLSPATH)` référencent la même variable d’environnement ou propriété.  
  
## <a name="example"></a>Exemple  
 Le fichier projet suivant utilise des variables d’environnement pour spécifier l’emplacement des répertoires.  
  
```xml  
<Project DefaultTargets="FakeBuild">  
    <PropertyGroup>  
        <FinalOutput>$(BIN_PATH)\myassembly.dll</FinalOutput>  
        <ToolsPath Condition=" '$(ToolsPath)' == '' ">  
            C:\Tools  
        </ToolsPath>  
    </PropertyGroup>  
    <Target Name="FakeBuild">  
        <Message Text="Building $(FinalOutput) using the tools at $(ToolsPath)..."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Voir aussi  
[MSBuild ](../msbuild/msbuild.md)  
[Propriétés MSBuild](../msbuild/msbuild-properties.md)  
[Guide pratique pour générer les mêmes fichiers sources avec des options différentes](../msbuild/how-to-build-the-same-source-files-with-different-options.md)  
