---
title: IDebugMessageEvent2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugMessageEvent2
helpviewer_keywords:
- IDebugMessageEvent2 interface
ms.assetid: a9ff3d00-e9ac-4cd6-bda9-584a4815aff8
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e7bb6b014ef8aa662abd42ab2989d47f703880a4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "65685973"
---
# <a name="idebugmessageevent2"></a>IDebugMessageEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette interface est utilisée par le moteur de débogage (DE) pour envoyer un message à Visual Studio qui requiert une réponse de l’utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugMessageEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes pour les implémenteurs  
 Le DE implémente cette interface pour envoyer un message à Visual Studio qui requiert une réponse de l’utilisateur. L’interface [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) doit être implémentée sur le même objet que cette interface. Le SDM utilise [QueryInterface](https://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) pour accéder à l' `IDebugEvent2` interface.  
  
 L’implémentation de cette interface doit communiquer l’appel de [SetResponse](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md) de Visual Studio à l’de. Par exemple, cette opération peut être effectuée avec un message publié dans le thread DE gestion des messages de, ou l’objet qui implémente cette interface peut contenir une référence à l’de et rappeler à l’à l’aide de la réponse passée dans `IDebugMessageEvent2::SetResponse` .  
  
## <a name="notes-for-callers"></a>Notes pour les appelants  
 Le DE crée et envoie cet objet d’événement pour afficher un message à l’utilisateur qui requiert une réponse. L’événement est envoyé à l’aide de la fonction de rappel [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) fournie par le SDM lorsqu’il est attaché au programme en cours de débogage.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le tableau suivant présente les méthodes de `IDebugMessageEvent2` .  
  
|Méthode|Description|  
|------------|-----------------|  
|[GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)|Obtient le message à afficher.|  
|[SetResponse](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md)|Définit la réponse, le cas échéant, dans la boîte de message.|  
  
## <a name="remarks"></a>Notes  
 Le DE utilise cette interface s’il requiert une réponse spécifique de l’utilisateur pour un message particulier. Par exemple, si le message DE obtient un message « accès refusé » après une tentative d’attachement à distance à un programme, le DE envoie ce message particulier à Visual Studio dans un `IDebugMessageEvent2` événement avec le style de la boîte de message `MB_RETRYCANCEL` . Cela permet à l’utilisateur de réessayer ou d’annuler l’opération d’attachement.  
  
 Le DE spécifie comment ce message doit être traité en suivant les conventions de la fonction Win32 `MessageBox` (pour plus d’informations, consultez [AfxMessageBox](https://msdn.microsoft.com/library/d66d0328-cdcc-48f6-96a4-badf089099c8) ).  
  
 Utilisez l’interface [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) pour envoyer des messages à Visual Studio qui ne nécessitent pas de réponse de l’utilisateur.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg. h  
  
 Espace de noms : Microsoft. VisualStudio. Debugger. Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces principales](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)
