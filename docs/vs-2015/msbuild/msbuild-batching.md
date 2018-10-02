---
title: Traitement par lots de MSBuild | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, batching
ms.assetid: d35c085b-27b8-49d7-b6f8-8f2f3a0eec38
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d868beddd498b112fa2f5a4de52f473c8ba3041
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47505672"
---
# <a name="msbuild-batching"></a>Traitement par lots de MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [le traitement par lots de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-batching).  
  
  
[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] a la capacité de diviser les listes d’éléments en différentes catégories, ou lots, en fonction des métadonnées des éléments, et d’exécuter une cible ou une tâche une fois avec chaque lot.  
  
## <a name="task-batching"></a>Traitement de tâches par lots  
 Le traitement de tâches par lots vous permet de simplifier vos fichiers projet en fournissant un moyen de diviser les listes d’éléments en différents lots et de passer chacun de ces lots dans une tâche séparément. Cela signifie qu’une tâche et ses attributs ne doivent être déclarés qu’une seule fois dans un fichier projet, même si elle peut être exécutée plusieurs fois.  
  
 Vous spécifiez ce que [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] doit effectuer comme traitement par lots avec une tâche en utilisant la notation %(*ItemMetaDataName*) dans un des attributs de la tâche. L’exemple suivant fractionne la liste d’éléments `Example` en lots en fonction de la valeur des métadonnées de l’élément `Color` et passe séparément chacun des lots à la tâche `MyTask`.  
  
> [!NOTE]
>  Si vous ne référencez pas la liste d’éléments ailleurs dans les attributs de tâche, ou si le nom des métadonnées peut être ambigu, vous pouvez utiliser la notation %(*ItemCollection.ItemMetaDataName*) pour qualifier complètement la valeur des métadonnées de l’élément à utiliser pour le traitement par lots.  
  
```  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 Pour obtenir des exemples de traitement par lots plus spécifiques, consultez [Métadonnées d’éléments dans le traitement par lots de tâches](../msbuild/item-metadata-in-task-batching.md).  
  
## <a name="target-batching"></a>Traitement de cibles par lots  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] vérifie si les entrées et sorties d’une cible sont à jour avant d’exécuter la cible. Si les entrées et les sorties sont à jour, la cible est ignorée. Si une tâche à l’intérieur d’une cible utilise le traitement par lots, [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] doit déterminer si les entrées et sorties de chaque lot d’éléments sont à jour. Sinon, la cible est exécutée chaque fois qu’elle est atteinte.  
  
 L’exemple suivant montre un élément `Target` contenant un attribut `Outputs` avec la notation %(*ItemMetaDataName*). [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] divise la liste d’éléments `Example` en lots en fonction des métadonnées de l’élément `Color` et analyse les horodatages des fichiers de sortie pour chaque lot. Si les sorties d’un lot ne sont pas à jour, la cible est exécutée. Sinon, la cible est ignorée.  
  
```  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Example Include="Item1">  
            <Color>Blue</Color>  
        </Example>  
        <Example Include="Item2">  
            <Color>Red</Color>  
        </Example>  
    </ItemGroup>  
  
    <Target Name="RunMyTask"  
        Inputs="@(Example)"  
        Outputs="%(Color)\MyFile.txt">  
        <MyTask  
            Sources = "@(Example)"  
            Output = "%(Color)\MyFile.txt"/>  
    </Target>  
  
</Project>  
```  
  
 Pour un autre exemple de traitement de cible par lots, consultez [Métadonnées d’éléments dans le traitement par lots de cibles](../msbuild/item-metadata-in-target-batching.md).  
  
## <a name="property-functions-using-metadata"></a>Fonctions de propriété utilisant des métadonnées  
 Le traitement par lots peut être contrôlé par des fonctions de propriété qui incluent des métadonnées. Par exemple :  
  
 `$([System.IO.Path]::Combine($(RootPath),%(Compile.Identity)))`  
  
 utilise <xref:System.IO.Path.Combine%2A> pour combiner un chemin de dossier racine avec un chemin d’élément de compilation.  
  
 Les fonctions de propriété ne peuvent pas apparaître dans des valeurs de métadonnées.  Par exemple :  
  
 `%(Compile.FullPath.Substring(0,3))`  
  
 n’est pas autorisé.  
  
 Pour plus d’informations sur les fonctions de propriété, consultez [Fonctions de propriété](../msbuild/property-functions.md).  
  
## <a name="see-also"></a>Voir aussi  
 [ItemMetadata, élément (MSBuild)](../msbuild/itemmetadata-element-msbuild.md)   
 [Concepts MSBuild](../msbuild/msbuild-concepts.md)   
 [Référence MSBuild](../msbuild/msbuild-reference.md)   
 [Concepts avancés](../msbuild/msbuild-advanced-concepts.md)



