---
title: IDebugBinder::Bind | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugBinder::Bind
helpviewer_keywords:
- IDebugBinder::Bind method
ms.assetid: 15a11ad7-0fcc-4e80-ae34-8a7dd7bae3c3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a1210b84a52aa15d3c8e1bb73bc58d1fbe48a19d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49920350"
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
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)