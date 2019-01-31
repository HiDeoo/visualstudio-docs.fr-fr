---
title: Touch, tâche | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 48c329b68449d9c92d6e501f81f2e3f0d2978cf5
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55003173"
---
# <a name="touch-task"></a>Touch (tâche)
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
 En plus des paramètres énumérés ci-dessus, cette tâche hérite des paramètres de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [Classe de base TaskExtension](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant utilise la tâche `Touch` pour modifier les heures d’accès et de modification des fichiers spécifiés dans la collection d’éléments `Files`, et place la liste de fichiers horodatés dans la collection d’éléments `FilesTouched`.  
  
```xml  
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
 [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)