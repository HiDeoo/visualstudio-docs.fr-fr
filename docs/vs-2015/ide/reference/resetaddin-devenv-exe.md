---
title: -ResetAddin (devenv.exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- disable addin
- addin state
- reset addin
ms.assetid: 9e339c8d-d768-4d86-8f45-2f479fc8255b
caps.latest.revision: 9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 9958e6e9a540dce1a405df8991780600b8f4a702
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72665601"
---
# <a name="resetaddin-devenvexe"></a>/ResetAddin (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Supprime les commandes et l’interface utilisateur des commandes associées au complément.

## <a name="syntax"></a>Syntaxe

```
Devenv /ResetAddin AddIn
```

## <a name="arguments"></a>Arguments
 `AddIn` Facultatif. Nom de commande du complément.

## <a name="remarks"></a>Notes
 Par défaut, le nom de commande du complément est égal à *\<AddInSolutionName>* . Connect<em>. \<AddInSolutionName> </em>et apparaît dans Connect.cs comme `commandName` paramètre de la `Exec` méthode. Vous pouvez également vérifier le nom de la commande en tapant les premières lettres du nom du complément dans la fenêtre Commandes de Visual Studio, puis en utilisant Intellisense pour compléter la saisie.

## <a name="example"></a>Exemple
 L’exemple suivant démarre Visual Studio et empêche le complément `MyAddin` de s’exécuter au démarrage.

```
Devenv.exe /ResetAddin MyAddin.Connect.MyAddin
```

## <a name="see-also"></a>Voir aussi
 [Personnalisation des paramètres de développement dans](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3) les [commutateurs de ligne de commande devenv](../../ide/reference/devenv-command-line-switches.md) de Visual Studio
