---
title: Définir le processus actuel
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a3440c66d79fef3eac3744681870c9ce1ed0e97b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75593549"
---
# <a name="set-current-process"></a>Définir le processus actuel
Définit le processus spécifié comme processus actif dans le débogueur.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.SetCurrentProcess index
```

## <a name="arguments"></a>Arguments
`index`

Obligatoire. Index du processus.

## <a name="remarks"></a>Notes
Pendant le débogage, vous pouvez attacher plusieurs processus à la fois, mais seul l’un d’entre eux est actif dans le débogueur à un moment donné. Vous pouvez utiliser la commande `SetCurrentProcess` pour définir le processus actif.

## <a name="example"></a>Exemple

```cmd
>Debug.SetCurrentProcess 1
```

## <a name="see-also"></a>Voir aussi

- [Commandes Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Fenêtre commande](../../ide/reference/command-window.md)
- [Alias de commandes Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
