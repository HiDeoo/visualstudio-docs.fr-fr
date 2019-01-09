---
title: RequiresFramework35SP1Assembly, tâche | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- RequiresFramework35SP1Assembly task [MSBuild]
- MSBuild, RequiresFramework35SP1Assembly task
ms.assetid: 755c018a-8a8b-4c94-8aee-3f171fc419e5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 915d837889153cf678695b493a853d9110522bee
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53831925"
---
# <a name="requiresframework35sp1assembly-task"></a>RequiresFramework35SP1Assembly (tâche)
Détermine si l’application nécessite le .NET Framework 3.5 SP1.  
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres de la tâche `RequiresFramework35SP1Assembly` .  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Assemblies`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie les assemblys référencés dans l’application.|  
|`CreateDesktopShortcut`|Paramètre `Boolean` facultatif.<br /><br /> Si `true`, crée une icône de raccourci sur le Bureau pendant l’installation.|  
|`DeploymentManifestEntryPoint`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Spécifie le nom du fichier manifeste de l’application.|  
|`EntryPoint`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Spécifie l’assembly qui doit être exécuté lors de l’exécution de l’application.|  
|`ErrorReportUrl`|Paramètre `String` facultatif.<br /><br /> Spécifie le site web affiché dans les boîtes de dialogue rencontrées pendant les installations ClickOnce.|  
|`Files`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie la liste des fichiers qui seront déployés au moment de la publication de l’application.|  
|`ReferencedAssemblies`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie les assemblys référencés dans le projet.|  
|`RequiresMinimumFramework35SP1`|Paramètre de sortie `Boolean` facultatif.<br /><br /> Si `true`, l’application nécessite le .NET Framework 3.5 SP1.|  
|`SigningManifests`|Paramètre de sortie `Boolean` facultatif.<br /><br /> Si `true`, les manifestes ClickOnce sont signés.|  
|`SuiteName`|Paramètre `String` facultatif.<br /><br /> Spécifie le nom du dossier dans le menu **Démarrer** dans lequel l’application va être installée.|  
|`TargetFrameworkVersion`|Paramètre `String` facultatif.<br /><br /> Spécifie la version du .NET Framework ciblée par l’application.|  
  
## <a name="remarks"></a>Notes  
 En plus des paramètres répertoriés dans le tableau, cette tâche comprend des paramètres qu’elle hérite de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [Classe de base TaskExtension](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Tâches](../msbuild/msbuild-tasks.md)   
 [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)