---
title: IDebugDefaultPort2::QueryIsLocal - France Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDefaultPort2::QueryIsLocal
helpviewer_keywords:
- IDebugDefaultPort2::QueryIsLocal
ms.assetid: 1a42e774-c6ed-419a-a0e3-cab5778652ca
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c06230f7bbd1825fe73a22f9b1fdc35aea35c499
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80732326"
---
# <a name="idebugdefaultport2queryislocal"></a>IDebugDefaultPort2::QueryIsLocal
Cette méthode détermine si ce port est sur la machine locale.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT QueryIsLocal(
   void
);
```

```csharp
int QueryIsLocal();
```

## <a name="return-value"></a>Valeur de retour
 Retourne `S_OK` si ce port est local (sur la `S_FALSE` même machine que l’appelant) ou si le port est sur une autre machine.

## <a name="see-also"></a>Voir aussi
- [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)
