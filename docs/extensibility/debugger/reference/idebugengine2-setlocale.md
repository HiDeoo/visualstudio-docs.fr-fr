---
title: 'IDebugEngine2 :: SetLocale | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::SetLocale
helpviewer_keywords:
- IDebugEngine2::SetLocale
ms.assetid: cd0d2cf1-2aac-43da-a830-4bb3d696c219
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8616dd827f99dfcfbc337cb5cdf5ac5a7d392e88
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80730918"
---
# <a name="idebugengine2setlocale"></a>IDebugEngine2::SetLocale
Définit les paramètres régionaux du moteur de débogage (DE).

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetLocale( 
   WORD wLangID
);
```

```csharp
int SetLocale( 
   ushort wLangID
);
```

## <a name="parameters"></a>Paramètres
`wLangID`\
dans Spécifie les paramètres régionaux de langue. Par exemple, 1033 pour l’anglais.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.

## <a name="remarks"></a>Notes
 Cette méthode est appelée par le gestionnaire de débogage de session (SDM) pour propager les paramètres régionaux de l’IDE afin que les chaînes retournées par le DE soient correctement localisées.

## <a name="see-also"></a>Voir aussi
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
