---
title: Touch, tâche | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Touch
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Touch task
- Touch task [MSBuild]
ms.assetid: 8a978645-1393-4904-ae69-42afabd8c109
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ac0614a8496d932f733d7e8bbd2d2b954329dd05
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49302045"
---
# <a name="touch-task"></a>Touch, tâche
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Définit les heures d’accès et de modification des fichiers.  
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres de la tâche `Touch` .  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`AlwaysCreate`|Paramètre `Boolean` facultatif.<br /><br /> Si la valeur est `true`, crée tous les fichiers qui n’existent pas.|  
|`Files`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` obligatoire.<br /><br /> Spécifie la collection de fichiers à horodater.|  
|`ForceTouch`|Paramètre `Boolean` facultatif.<br /><br /> Si la valeur est `true`, force un horodatage de fichier même si les fichiers sont en lecture seule.|  
|`Time`|Paramètre `String` facultatif.<br /><br /> Spécifie une heure autre que l’heure actuelle. Le format doit être acceptable pour la méthode <xref:System.DateTime.Parse%2A>.|  
|`TouchedFiles`|Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Contient la collection d’éléments horodatés.|  
  
## <a name="remarks"></a>Notes  
 En plus des paramètres énumérés ci-dessus, cette tâche hérite des paramètres de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant utilise la tâche `Touch` pour modifier les heures d’accès et de modification des fichiers spécifiés dans la collection d’éléments `Files`, et place la liste de fichiers horodatés dans la collection d’éléments `FilesTouched`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
<ItemGroup>  
    <Files Include="File1.cs;File2.cs;File3.cs" />  
</ItemGroup>  
  
    <Target Name="TouchFiles">  
        <Touch  
            Files="@(Files)">  
            <Output  
                TaskParameter="TouchedFiles"  
                ItemName="FilesTouched"/>  
    </Touch>  
</Target>  
</Project>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Tâches](../msbuild/msbuild-tasks.md)   
 [Task Reference (Informations de référence sur les tâches MSBuild)](../msbuild/msbuild-task-reference.md)



