---
title: Classe VCToolTask | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
author: ghogen
ms.author: ghogen
ms.workload:
- multiple
ms.openlocfilehash: df75bb998d2b8c6486e20c4c3ca0d80347c8f88a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75591669"
---
# <a name="vctooltask-base-class"></a>Classe de base VCToolTask

De nombreuses tâches héritent au final de la classe <xref:Microsoft.Build.Utilities.Task> et de la classe [ToolTask](/dotnet/api/microsoft.build.utilities.tooltask). Cette classe ajoute plusieurs paramètres aux tâches qui en dérivent. Ces paramètres sont répertoriés dans ce document.

## <a name="parameters"></a>Paramètres

Le tableau ci-dessous décrit les paramètres de la classe de base **VCToolTask**.

|Paramètre|Description|
|---------------|-----------------|
|**ActiveToolSwitchesValues**|Paramètre **de \<string, ToolSwitch> dictionnaire** facultatif.|
|**AdditionalOptions**|Paramètre de **chaîne** facultatif.|
|**EffectiveWorkingDirectory**|Paramètre de **chaîne** facultatif.|
|**EnableErrorListRegex**|Paramètre **booléen** facultatif.<br/><br/>La valeur par défaut est `true`.|
|**ErrorListRegex**|Paramètre **ITaskItem []** facultatif.|
|**ErrorListListExclusion**|Paramètre **ITaskItem []** facultatif.|
|**GenerateCommandLine**|Paramètre de **chaîne** facultatif.<br/><br/>Utilise les valeurs **CommandLineFormat** *format* [par défaut = CommandLineFormat.ForBuildLog] et **EscapeFormat** *escapeFormat* [default = EscapeFormat.Default].|
|**GenerateCommandLineExceptSwitches**|Paramètre de **chaîne** facultatif.<br/><br/>Utilise les valeurs **chaîne[]** *switchesToRemove*, **CommandLineFormat** *format* [par défaut = CommandLineFormat.ForBuildLog] et **EscapeFormat** *escapeFormat* [par défaut = EscapeFormat.Default].|

## <a name="see-also"></a>Voir aussi

[Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)<br/>
[Tâches](../msbuild/msbuild-tasks.md)
