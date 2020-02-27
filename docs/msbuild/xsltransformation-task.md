---
title: XslTransformation, tâche | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, XslTransformation task
- XslTransformation task [MSBuild]
ms.assetid: 6f3a7d81-3ae3-4703-9a06-870b32b69d80
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 84bc83f60d133dcaf22c9fa690357fa2624adabd
ms.sourcegitcommit: 96737c54162f5fd5c97adef9b2d86ccc660b2135
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77630793"
---
# <a name="xsltransformation-task"></a>XslTransformation (tâche)

Transforme une entrée XML à l’aide d’une transformation XSLT ou XSLT compilée, et génère la sortie dans un fichier ou un périphérique de sortie.

## <a name="parameters"></a>Paramètres

 Le tableau ci-dessous décrit les paramètres de la tâche `XslTransformation`.

|Paramètre|Description|
|---------------|-----------------|
|`OutputPaths`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` obligatoire.<br /><br /> Spécifie les fichiers de sortie de la transformation XML.|
|`Parameters`|Paramètre `String` facultatif.<br /><br /> Spécifie les paramètres pour le document d’entrée XSLT.|
|`XmlContent`|Paramètre `String` facultatif.<br /><br /> Spécifie l’entrée XML sous forme de chaîne.|
|`XmlInputPaths`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie les fichiers d’entrée XML.|
|`XslCompiledDllPath`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Spécifie la transformation XSLT compilée.|
|`XslContent`|Paramètre `String` facultatif.<br /><br /> Spécifie l’entrée XSLT sous forme de chaîne.|
|`XslInputPath`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Spécifie le fichier d’entrée XSLT.|

## <a name="remarks"></a>Notes

 En plus des paramètres répertoriés dans le tableau, cette tâche comprend des paramètres qu’elle hérite de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [Classe de base TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Voir aussi

- [Tâches :](../msbuild/msbuild-tasks.md)
- [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)
