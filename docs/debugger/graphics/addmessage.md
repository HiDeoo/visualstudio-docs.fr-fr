---
title: AddMessage | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 41a71a69c916bf2fff30b2dee8784d5d9997436b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "62896353"
---
# <a name="addmessage"></a>AddMessage
Ajoute un message personnalisé à l’affichage à haute vue de Graphics Diagnostics *(affichage* principal).

## <a name="syntax"></a>Syntaxe

```C++
void AddMessage(
  wchar_t const * szMessage
);
```

#### <a name="parameters"></a>Paramètres
 `szMessage` Message à ajouter au HUD.

## <a name="remarks"></a>Notes
 Le HUD Graphics Diagnostics s’affiche dans l’angle supérieur gauche de l’application exécutée dans Graphics Diagnostics. Il affiche des informations d’exécution sur l’application et sur la capture des informations graphiques, ainsi que des messages ajoutés en appelant cette fonction.

 Pour ajouter un message à HUD, vous n’êtes pas obligé de capturer activement les informations graphiques, autrement dit, un message peut être ajouté par le biais d’une instance de la `VsgDbg` classe, mais la fonction membre [init](init.md) ne doit pas être appelée en premier. Les messages s’affichent uniquement dans le HUD, ils ne sont pas enregistrés dans le fichier journal de graphisme.