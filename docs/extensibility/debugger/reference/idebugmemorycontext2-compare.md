---
title: 'IDebugMemoryContext2 :: compare | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMemoryContext2::Compare
helpviewer_keywords:
- IDebugMemoryContext2::Compare method
- Compare method
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4b2551f8554d96186b90a1eed97a5a48ec5f0405
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80727489"
---
# <a name="idebugmemorycontext2compare"></a>IDebugMemoryContext2::Compare
Compare le contexte de mémoire à chaque contexte dans le tableau donné de la manière indiquée par les indicateurs de comparaison, en retournant un index du premier contexte qui correspond.

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
dans Valeur de l’énumération [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md) qui détermine le type de comparaison.

`rgpMemoryContextSet`\
dans Tableau de références aux objets [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) à comparer.

`dwMemoryContextSetLen`\
dans Nombre de contextes dans le `rgpMemoryContextSet` tableau.

`pdwMemoryContext`\
à Retourne l’index du premier contexte de mémoire qui satisfait à la comparaison.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur. Retourne `E_COMPARE_CANNOT_COMPARE` si les deux contextes ne peuvent pas être comparés.

## <a name="remarks"></a>Notes
 Un moteur de débogage (de) n’a pas besoin de prendre en charge tous les types de comparaisons, mais il doit prendre en charge au moins `CONTEXT_EQUAL` , `CONTEXT_LESS_THAN` , `CONTEXT_GREATER_THAN` et `CONTEXT_SAME_SCOPE` .

## <a name="see-also"></a>Voir aussi
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
- [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)
