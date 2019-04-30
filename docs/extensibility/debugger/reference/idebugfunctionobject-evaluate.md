---
title: IDebugFunctionObject::Evaluate | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionObject::Evaluate
helpviewer_keywords:
- IDebugFunctionObject::Evaluate method
ms.assetid: 29349ea3-d5c1-4135-aa76-ced073ab9683
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9deaf32a88d476895feab006cbe3b818d11b97ca
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62873950"
---
# <a name="idebugfunctionobjectevaluate"></a>IDebugFunctionObject::Evaluate
Appelle la fonction et retourne la valeur obtenue en tant qu’objet.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Evaluate( 
   IDebugObject** ppParams,
   DWORD          dwParams,
   DWORD          dwTimeout,
   IDebugObject** ppResult
);
```

```csharp
int Evaluate(
   IDebugObject[]   ppParams,
   IntPtr           dwParams,
   uint             dwTimeout,
   out IDebugObject ppResult
);
```

#### <a name="parameters"></a>Paramètres
 `ppParams`

 [in] Un tableau de [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objets représentant les paramètres d’entrée. Chacun de ces paramètres a été créé avec l’un de le `Create` méthodes dans le [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) interface.

 `dwParams`

 [in] Le nombre de paramètres dans le `ppParams` tableau.

 `dwTimeout`

 [in] Spécifie la durée maximale, en millisecondes, à attendre avant de retourner à partir de cette méthode. Utilisez `INFINITE` pour attendre indéfiniment.

 `ppResult`

 [out] Retourne un [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) représentant la valeur de la fonction en tant qu’objet.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne S_OK ; Sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 Cette méthode configure et exécute un appel à la fonction représentée par le [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) objet.

## <a name="see-also"></a>Voir aussi
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)