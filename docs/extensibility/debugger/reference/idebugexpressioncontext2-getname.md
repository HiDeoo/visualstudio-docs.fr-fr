---
title: 'IDebugExpressionContext2 :: GetName | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionContext2::GetName
helpviewer_keywords:
- IDebugExpressionContext2::GetName
ms.assetid: c2b70d22-17af-4986-a7e3-930910367216
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 500d5c1788e837a27b4affada50ecc59db122e8a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80729664"
---
# <a name="idebugexpressioncontext2getname"></a>IDebugExpressionContext2::GetName
Récupère le nom du contexte d’évaluation.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetName( 
   BSTR* pbstrName
);
```

```csharp
int GetName( 
   out string pbstrName
);
```

## <a name="parameters"></a>Paramètres
`pbstrName`\
à Retourne le nom du contexte d’évaluation.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.

## <a name="remarks"></a>Notes
 Le nom est la description de ce contexte d’évaluation. Il s’agit généralement d’un nom qui peut être analysé par un évaluateur d’expression qui fait référence à ce contexte d’évaluation exact. Par exemple, en C++, le nom est le suivant :

```
"{ function-name, source-file-name, module-file-name }"
```

## <a name="see-also"></a>Voir aussi
- [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)
