---
title: IDebugBinder::Bind | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder::Bind
helpviewer_keywords:
- IDebugBinder::Bind method
ms.assetid: 15a11ad7-0fcc-4e80-ae34-8a7dd7bae3c3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bcb3535a2ace5818664a34a5d7b818d7dfd8b025
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56704941"
---
# <a name="idebugbinderbind"></a>IDebugBinder::Bind
Cette méthode obtient le contexte de la mémoire ou d’un objet qui contient la valeur actuelle du symbole.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Bind( 
   IDebugObject*  pContainer,
   IDebugField*   pField,
   IDebugObject** ppObject
);
```

```csharp
int Bind(
   IDebugObject     pContainer,
   IDebugField      pField,
   out IDebugObject ppObject
);
```

#### <a name="parameters"></a>Paramètres
 `pContainer`

 [in] Le [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) qui contient l’enfant référencée par `pField`.

 `pField`

 [in] Le [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) qui représente le symbole.

 `ppObject`

 [out] Retourne le `IDebugObject` qui représente l’instance du symbole.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="see-also"></a>Voir aussi
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)