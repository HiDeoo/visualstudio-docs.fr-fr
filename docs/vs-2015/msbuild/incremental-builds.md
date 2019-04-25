---
title: Builds incrémentielles | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- msbuild, incremental builds
ms.assetid: 325e28c7-4838-4e3f-b672-4586adc7500c
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: eb11467d8d59e7af11741d7719da2858ac1a784c
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59654033"
---
# <a name="incremental-builds"></a>Builds incrémentielles
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Les builds incrémentielles sont des builds optimisées qui permettent de ne pas exécuter les cibles dont les fichiers de sortie sont à jour par rapport à leurs fichiers d’entrée correspondants. Un élément cible peut avoir à la fois un attribut `Inputs`, qui indique les éléments que la cible attend comme entrée, et un attribut `Outputs` qui indique les éléments qu’il produit comme sortie. MSBuild tente de trouver une correspondance « 1 à 1 » entre les valeurs de ces attributs. Si une correspondance « 1 à 1 » existe, MSBuild compare l’horodatage de chaque élément d’entrée avec celui de l’élément de sortie correspondant. Les fichiers de sortie sans correspondance « 1 à 1 » sont comparés à tous les fichiers d’entrée. Un élément est considéré comme à jour si son fichier de sortie a une date de création identique ou antérieure à celle du ou des fichiers d’entrée.  
  
 Si tous les éléments de sortie sont à jour, MSBuild ignore la cible. Cette *build incrémentielle* de la cible peut améliorer considérablement la vitesse de génération. Si seuls certains fichiers sont à jour, MSBuild exécute la cible en ignorant les éléments à jour, pour que tous les éléments soient à jour. C’est ce qu’on appelle une *build incrémentielle partielle*.  
  
 Les correspondances « 1 à 1 » sont généralement produites par des transformations d’éléments. Pour plus d’informations, consultez l’article [Transforms (Transformations MSBuild)](../msbuild/msbuild-transforms.md).  
  
 Examinons la cible suivante.  
  
```  
<Target Name="Backup" Inputs="@(Compile)"   
    Outputs="@(Compile->'$(BackupFolder)%(Identity).bak')">  
    <Copy SourceFiles="@(Compile)" DestinationFiles=  
        "@(Compile->'$(BackupFolder)%(Identity).bak')" />  
</Target>  
```  
  
 Le jeu de fichiers représenté par le type d’élément `Compile` est copié dans un répertoire de sauvegarde. Les fichiers de sauvegarde ont l’extension de nom de fichier .bak. Si les fichiers représentés par le type d’élément `Compile`, ou les fichiers de sauvegarde correspondants, ne sont pas supprimés ou modifiés après l’exécution de la cible de sauvegarde, celle-ci est ignorée dans les builds suivantes.  
  
## <a name="output-inference"></a>Inférence de sortie  
 MSBuild compare les attributs `Inputs` et `Outputs` d’une cible pour déterminer si celle-ci doit être exécutée. Dans l’idéal, le jeu de fichiers qui existe après une build incrémentielle doit rester le même, que les cibles associées soient exécutées ou non. Étant donné que les propriétés et les éléments qui sont créés ou modifiés par les tâches peuvent affecter la build, MSBuild doit déduire leurs valeurs, même si la cible associée est ignorée. C’est ce qu’on appelle *l’inférence de sortie*.  
  
 Celle-ci s’utilise dans trois cas :  
  
- La cible a un attribut `Condition` dont la valeur est `false`. Dans ce cas, la cible n’est pas exécutée et n’a aucun effet sur la build.  
  
- La cible comprend des sorties obsolètes, et est donc exécutée pour les mettre à jour.  
  
- La cible ne comprend aucune sortie obsolète, et est donc ignorée. MSBuild évalue la cible et apporte des modifications aux éléments et aux propriétés comme si la cible avait été exécutée.  
  
  Pour que la compilation incrémentielle soit prise en charge, les tâches doivent vérifier que la valeur de l’attribut `TaskParameter` d’un élément `Output` est égale à un paramètre d’entrée de tâche. Voici quelques exemples :  
  
```  
<CreateProperty Value="123">  
    <Output PropertyName="Easy" TaskParameter="Value" />  
</CreateProperty>  
```  
  
 Cela crée la propriété Easy, dont la valeur est « 123 », que la cible ait été ou non exécutée ou ignorée.  
  
```  
<CreateItem Include="a.cs;b.cs">  
    <Output ItemName="Simple" TaskParameter="Include" />  
</CreateItem>  
```  
  
 Cela crée le type d’élément Simple, qui comprend les deux éléments « a.cs » et « b.cs », que la cible ait été ou non exécutée ou ignorée.  
  
 À compter de MSBuild 3.5, l’inférence de sortie est exécutée automatiquement sur les groupes de propriétés et d’éléments de la cible. Les tâches `CreateItem` ne sont pas obligatoires dans la cible et doivent être évitées. De plus, les tâches `CreateProperty` ne doivent être utilisées dans une cible que pour déterminer si celle-ci a été exécutée.  
  
## <a name="determining-whether-a-target-has-been-run"></a>Déterminer si une cible a été exécutée  
 En raison de l’inférence de sortie, vous devez ajouter une tâche `CreateProperty` à une cible pour examiner les propriétés et les éléments, et ainsi, déterminer si la cible a été exécutée. Ajoutez la tâche `CreateProperty` à la cible et attribuez-lui un élément `Output` dont le `TaskParameter` est défini sur « ValueSetByTask ».  
  
```  
<CreateProperty Value="true">  
    <Output TaskParameter="ValueSetByTask" PropertyName="CompileRan" />  
</CreateProperty>  
```  
  
 Cela crée la propriété CompileRan et lui attribue la valeur `true`, mais uniquement si la cible est exécutée. Si la cible est ignorée, CompileRan n’est pas créé.  
  
## <a name="see-also"></a>Voir aussi  
 [Targets (Cibles MSBuild)](../msbuild/msbuild-targets.md)
