---
title: Diagnostic des échecs de tâches | Microsoft Docs
ms.date: 09/25/2019
ms.topic: troubleshooting
f1_keywords:
- MSBuild.ToolTask.ToolCommandFailed
dev_langs:
- VB
- CSharp
- C++
- jsharp
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 89dcb8bddf2c92406ad5eff952d1f4050d7f9262
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75593276"
---
# <a name="diagnosing-task-failures"></a>Diagnostic des échecs de tâches

`MSB6006` est émis lorsqu’une <xref:Microsoft.Build.Utilities.ToolTask> classe dérivée de exécute un processus outil qui retourne un code de sortie différent de zéro si la tâche n’a pas journalisé une erreur plus spécifique.

## <a name="identifying-the-failing-task"></a>Identification de la tâche ayant échoué

Lorsque vous rencontrez une erreur de tâche, la première étape consiste à identifier la tâche qui échoue.

Le texte de l’erreur spécifie le nom de l’outil (soit un nom convivial fourni par l’implémentation de la tâche de, <xref:Microsoft.Build.Utilities.ToolTask.ToolName> soit le nom de l’exécutable) et le code de sortie numérique. Par exemple, dans

```text
error MSB6006: "custom tool" exited with code 1.
```

Le nom de l’outil est `custom tool` et le code de sortie est `1` .

### <a name="command-line-builds"></a>Générations à partir de la ligne de commande

Si la Build a été configurée pour inclure un résumé (valeur par défaut), le résumé se présente comme suit :

```text
Build FAILED.

"S:\MSB6006_demo\MSB6006_demo.csproj" (default target) (1) ->
(InvokeToolTask target) ->
  S:\MSB6006_demo\MSB6006_demo.csproj(19,5): error MSB6006: "custom tool" exited with code 1.
```

Ce résultat indique que l’erreur s’est produite dans une tâche définie à la ligne 19 du fichier `S:\MSB6006_demo\MSB6006_demo.csproj` , dans une cible nommée `InvokeToolTask` , dans le projet `S:\MSB6006_demo\MSB6006_demo.csproj` .

### <a name="in-visual-studio"></a>Dans Visual Studio

Les mêmes informations sont disponibles dans la liste d’erreurs de Visual Studio dans les colonnes `Project` , `File` et `Line` .

## <a name="finding-more-failure-information"></a>Recherche d’informations supplémentaires sur les échecs

Cette erreur est émise lorsque la tâche n’a pas journaliser une erreur spécifique. L’échec de journalisation d’une erreur est souvent dû au fait que la tâche n’est pas configurée pour comprendre le format d’erreur émis par l’outil qu’elle appelle.

Les outils corrects émettent généralement des informations contextuelles ou d’erreur dans leur flux de sortie ou d’erreur standard, et les tâches capturent et journalisent ces informations par défaut. Recherchez dans les entrées de journal avant que l’erreur ne s’est produite pour obtenir des informations supplémentaires. La réexécution de la build avec un niveau de journalisation plus élevé peut être nécessaire pour conserver ces informations.

## <a name="next-steps"></a>Étapes suivantes

Espérons que le contexte supplémentaire ou les erreurs identifiées dans la journalisation révèlent la cause initiale du problème.

Si ce n’est pas le cas, vous devrez peut-être limiter les causes potentielles en examinant les propriétés et les éléments qui sont des entrées de la tâche ayant échoué.
