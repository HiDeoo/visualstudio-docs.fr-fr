---
title: CreateCSharpManifestResourceName, tâche | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CreateCSharpManifestResourceName task
- CreateCSharpManifestResourceName task [MSBuild]
ms.assetid: 2ace88c1-d757-40a7-8158-c1d3f5ff0511
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b7ddede6870a982520b87cf8ec497788b4731244
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640543"
---
# <a name="createcsharpmanifestresourcename-task"></a>CreateCSharpManifestResourceName (tâche)
Crée un nom de manifeste de style [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] à partir d’un nom de fichier *.resx* donné ou d’une autre ressource.

## <a name="parameters"></a>Paramètres
 Le tableau suivant décrit les paramètres de la [tâche CreateCSharpManifestResourceName](../msbuild/createcsharpmanifestresourcename-task.md).


| Paramètre | Description |
| - | - |
| `ManifestResourceNames` | Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem> `[]` en lecture seule.<br /><br /> Noms des manifestes résultants. |
| `ResourceFiles` | Paramètre `String` requis.<br /><br /> Nom du fichier de ressources à partir duquel créer le nom du manifeste [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]. |
| `RootNamespace` | Paramètre `String` facultatif.<br /><br /> Espace de noms racine du fichier de ressources, qui provient généralement du fichier projet. Peut avoir la valeur `null`. |
| `PrependCultureAsDirectory` | Paramètre `Boolean` facultatif.<br /><br /> Si `true`, le nom de culture est ajouté comme nom de répertoire juste avant le nom de ressource de manifeste. La valeur par défaut est `true`. |
| `ResourceFilesWithManifestResourceNames` | Paramètre de sortie `String` en lecture seule facultatif.<br /><br /> Retourne le nom du fichier de ressources qui inclut maintenant le nom de ressource de manifeste. |

## <a name="remarks"></a>Remarques
 La [tâche CreateVisualBasicManifestResourceName](../msbuild/createvisualbasicmanifestresourcename-task.md) détermine le nom de ressource de manifeste approprié à assigner à un fichier *.resx* ou autre fichier de ressources donné. La tâche fournit un nom logique à un fichier de ressources, puis l’attache à un paramètre de sortie en tant que métadonnées.

 En plus des paramètres énumérés ci-dessus, cette tâche hérite des paramètres de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [Classe de base TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Voir aussi
- [Tâches](../msbuild/msbuild-tasks.md)
- [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)