---
title: IDebugMemoryContext2::Compare | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryContext2::Compare
helpviewer_keywords:
- IDebugMemoryContext2::Compare method
- Compare method
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f04000d3e2675f766ae343836320aa7433ade87d
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211995"
---
# <a name="idebugmemorycontext2compare"></a>IDebugMemoryContext2::Compare
Compare le contexte de la mémoire pour chaque contexte dans le tableau spécifié de la manière indiquée par des indicateurs de comparaison, retournant le premier contexte qui correspond à un index.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Compare( 
   CONTEXT_COMPARE        compare,
   IDebugMemoryContext2** rgpMemoryContextSet,
   DWORD                  dwMemoryContextSetLen,
   DWORD*                 pdwMemoryContext
);
```

```csharp
int Compare(
   enum_CONTEXT_COMPARE   compare,
   IDebugMemoryContext2[] rgpMemoryContextSet,
   uint                   dwMemoryContextSetLen,
   out uint               pdwMemoryContext
);
```

## <a name="parameters"></a>Paramètres
`compare`\
[in] Une valeur comprise entre le [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md) énumération qui détermine le type de comparaison.

`rgpMemoryContextSet`\
[in] Un tableau de références à la [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objets à comparer.

`dwMemoryContextSetLen`\
[in] Le nombre de contextes dans le `rgpMemoryContextSet` tableau.

`pdwMemoryContext`\
[out] Retourne l’index du premier contexte mémoire qui satisfait à la comparaison.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur. Retourne `E_COMPARE_CANNOT_COMPARE` si les deux contextes ne peuvent pas être comparées.

## <a name="remarks"></a>Notes
 Un moteur de débogage (dé) n’a pas prendre en charge tous les types de comparaisons, mais il doit prendre en charge au moins `CONTEXT_EQUAL`, `CONTEXT_LESS_THAN`, `CONTEXT_GREATER_THAN` et `CONTEXT_SAME_SCOPE`.

## <a name="see-also"></a>Voir aussi
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
- [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)