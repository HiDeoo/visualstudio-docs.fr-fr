---
title: IDebugBreakpointUnboundEvent2::GetBreakpoint | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBreakpointUnboundEvent2::GetBreakpoint
helpviewer_keywords:
- IDebugBreakpointUnboundEvent2::GetBreakpoint
ms.assetid: ad73a207-b778-4dc5-b645-5ec668a63333
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f6c99a3ed47cfba2ffba04084acb9f8ed247cfee
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53954550"
---
# <a name="idebugbreakpointunboundevent2getbreakpoint"></a>IDebugBreakpointUnboundEvent2::GetBreakpoint
Obtient le point d’arrêt s’est détaché.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetBreakpoint(   
   IDebugBoundBreakpoint2** ppBP  
);  
```  
  
```csharp  
int GetBreakpoint(   
   out IDebugBoundBreakpoint2 ppBP  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `ppBP`  
 [out] Retourne un [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md) objet qui représente le point d’arrêt s’est détaché.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment implémenter cette méthode pour un **CBreakpointUnboundDebugEventBase** objet qui expose le [IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md) interface.  
  
```cpp  
STDMETHODIMP CBreakpointUnboundDebugEventBase::GetBreakpoint(  
    IDebugBoundBreakpoint2 **ppbp)  
{  
    HRESULT hRes = E_FAIL;  
  
    if ( ppbp )  
    {  
        if ( m_pbp )  
        {  
            IDebugBoundBreakpoint2 *pibp;  
  
            hRes = m_pbp->QueryInterface(IID_IDebugBoundBreakpoint2, (void **) & pibp);  
  
            if ( S_OK == hRes )  
                *ppbp = pibp;  
        }  
        else  
            hRes = E_FAIL;  
    }  
    else  
        hRes = E_INVALIDARG;  
  
    return ( hRes );  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)   
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)