---
title: IDebugInterceptExceptionCompleteEvent2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugInterceptExceptionCompleteEvent2
helpviewer_keywords:
- IDebugInterceptExceptionCompleteEvent2
ms.assetid: 8ebc256b-5428-4ed6-a505-6aedc8242b8e
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c54a39072b2e214af3f057ba4fb0d3b450eceb4d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58952336"
---
# <a name="idebuginterceptexceptioncompleteevent2"></a>IDebugInterceptExceptionCompleteEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette interface est envoyée par le moteur de débogage (dé) pour le Gestionnaire de session de débogage (SDM) lorsque le dé a terminé la gestion d’un événement intercepté.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugInterceptExceptionCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Le D’implémente cette interface pour signaler que le traitement d’une exception interceptée a été effectué. Le [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) interface doit être implémentée sur le même objet que cette interface. Utilise le SDM [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) pour accéder à la `IDebugEvent2` interface.  
  
## <a name="notes-for-callers"></a>Notes de publication pour les appelants  
 Le DE crée et envoie cet objet d’événement pour signaler l’achèvement d’une exception interceptée. L’événement est envoyé à l’aide de la [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) fonction de rappel qui est fournie par le SDM lorsqu’il est attaché au programme en cours de débogage.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le `IDebugInterceptExceptionCompleteEvent2` interface implémente les méthodes suivantes.  
  
|Méthode|Description|  
|------------|-----------------|  
|[GetInterceptCookie](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2-getinterceptcookie.md)|Retourne la valeur unique associée à l’exception gérée.|  
  
## <a name="remarks"></a>Notes  
 Cet événement ne sera envoyé par [InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md) lorsque cette méthode est terminée avec succès gère une exception interceptée.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg.h  
  
 Espace de noms : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces principales](../../../extensibility/debugger/reference/core-interfaces.md)   
 [InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)
