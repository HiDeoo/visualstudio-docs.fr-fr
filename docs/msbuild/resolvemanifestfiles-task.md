---
title: ResolveManifestFiles, tâche | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveManifestFiles task [MSBuild]
- MSBuild, ResolveManifestFiles task
ms.assetid: e1e14f67-9b69-433f-94d4-a783a68676b2
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2628f06ac4eafc7d57123460771793005597b039
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "77632691"
---
# <a name="resolvemanifestfiles-task"></a>ResolveManifestFiles (tâche)

Résout les éléments suivants dans le processus de génération en fichiers pour la génération de manifeste : éléments générés, dépendances, satellites, contenu, symboles de débogage et documentation.

## <a name="parameters"></a>Paramètres

 Le tableau ci-dessous décrit les paramètres de la tâche `ResolveManifestFiles` .

|Paramètre|Description|
|---------------|-----------------|
|`DeploymentManifestEntryPoint`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Spécifie le nom du manifeste de déploiement.|
|`EntryPoint`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Spécifie l’assembly managé ou la référence de manifeste ClickOnce qui est le point d’entrée au manifeste.|
|`ExtraFiles`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie les fichiers supplémentaires.|
|`ManagedAssemblies`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie les assemblys managés.|
|`NativeAssemblies`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie les assemblys natifs.|
|`OutputAssemblies`|Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie les assemblys générés.|
|`OutputDeploymentManifestEntryPoint`|Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Spécifie le point d’entrée du manifeste de déploiement de sortie.|
|`OutputEntryPoint`|Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Spécifie le point d’entrée de sortie.|
|`OutputFiles`|Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie les fichiers de sortie.|
|`PublishFiles`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie les fichiers de publication.|
|`SatelliteAssemblies`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie les assemblys satellites.|
|`SigningManifests`|Paramètre `Boolean` facultatif.<br /><br /> Si `true`, les manifestes sont signés.|
|`TargetCulture`|Paramètre `String` facultatif.<br /><br /> Spécifie la culture cible pour les assemblys satellites.|
|`TargetFrameworkVersion`|Paramètre `String` facultatif.<br /><br /> Spécifie la version du .NET Framework cible.|

## <a name="remarks"></a>Notes

 En plus des paramètres répertoriés dans le tableau, cette tâche comprend des paramètres qu’elle hérite de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [classe de base TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Voir aussi

- [Tâches](../msbuild/msbuild-tasks.md)
- [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)
