---
title: PENDING_BP_STATE_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PENDING_BP_STATE_INFO
helpviewer_keywords:
- PENDING_BP_STATE_INFO structure
ms.assetid: 4d73ceff-43f9-4e95-8dba-88e1fab2def3
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 306f3f6ac5f12d2a26da958d50fae87c6e174355
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66349879"
---
# <a name="pendingbpstateinfo"></a>PENDING_BP_STATE_INFO
Contient des informations sur l’état d’un point d’arrêt est prêt à lier à un emplacement de code.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _tagPENDING_BP_STATE_INFO { 
   PENDING_BP_STATE       state;
   PENDING_BP_STATE_FLAGS flags;
} PENDING_BP_STATE_INFO;
```

```csharp
public struct PENDING_BP_STATE_INFO { 
   public uint state;
   public uint flags;
};
```

## <a name="members"></a>Membres
 `state`\
 Une valeur comprise entre le [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md) énumération qui spécifie l’état de point d’arrêt en attente.

 `flags`\
 Une combinaison d’indicateurs de la [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md) énumération qui spécifie si le point d’arrêt est virtualisé.

## <a name="remarks"></a>Notes
 Cette structure est passée à la [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md) méthode où il est renseigné.

## <a name="requirements"></a>Configuration requise
 En-tête : msdbg.h

 Espace de noms : Microsoft.VisualStudio.Debugger.Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Structures et unions](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetState](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-getstate.md)
- [PENDING_BP_STATE](../../../extensibility/debugger/reference/pending-bp-state.md)
- [PENDING_BP_STATE_FLAGS](../../../extensibility/debugger/reference/pending-bp-state-flags.md)