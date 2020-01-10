---
title: CombinePath, tâche | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CombinePath task
- CombinePath task [MSBuild]
ms.assetid: c20edbf4-3d4f-4f66-b1d5-753a0d858ed8
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a52e0d770a535b0fa7d29a379a7f6aba63e62d78
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75593341"
---
# <a name="combinepath-task"></a>CombinePath (tâche)
Combine les chemins spécifiés en un chemin unique.

## <a name="task-parameters"></a>Paramètres de tâche
 Le tableau ci-dessous décrit les paramètres de la tâche [CombinePath](../msbuild/combinepath-task.md).

|Paramètre|Description|
|---------------|-----------------|
|`BasePath`|Paramètre `String` requis.<br /><br /> Chemin de base à combiner aux autres chemins. Peut être un chemin relatif, absolu ou vide.|
|`Paths`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` obligatoire.<br /><br /> Liste de chemins individuels à combiner avec BasePath pour former le chemin combiné. Les chemins peuvent être relatifs ou absolus.|
|`CombinedPaths`|Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Chemin combiné créé par cette tâche.|

## <a name="remarks"></a>Notes
 En plus des paramètres énumérés ci-dessus, cette tâche hérite des paramètres de la classe <xref:Microsoft.Build.Tasks.TaskExtension> , qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task> . Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [Classe de base TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Voir aussi
- [Tâches MSBuild](../msbuild/msbuild-tasks.md)
- [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)
