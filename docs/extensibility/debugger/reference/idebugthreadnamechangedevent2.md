---
title: IDebugThreadNameChangedEvent2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugThreadNameChangedEvent2
helpviewer_keywords:
- IDebugThreadNameChangedEvent2
ms.assetid: 34c1652e-f019-48ba-8b26-ace20f8a158c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bfba0f335860375a173ca440fe944ea22c87ac76
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55069991"
---
# <a name="idebugthreadnamechangedevent2"></a>IDebugThreadNameChangedEvent2
Cette interface est envoyée par le moteur de débogage (dé) pour le Gestionnaire de session de débogage (SDM) lorsque le nom d’un thread change dans le programme en cours de débogage.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugThreadNameChangedEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Le D’implémente cette interface pour les rapports qui les nom d’un thread a été modifié. Le [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) interface doit être implémentée sur le même objet que cette interface. Utilise le SDM [QueryInterface](/cpp/atl/queryinterface) pour accéder à la `IDebugEvent2` interface.  
  
## <a name="notes-for-callers"></a>Notes de publication pour les appelants  
 Le DE crée et envoie cet objet d’événement à signaler les nom d’un thread a été modifié. L’événement est envoyé à l’aide de la [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) fonction de rappel qui est fournie par le SDM lorsqu’il est attaché au programme en cours de débogage.  
  
## <a name="requirements"></a>Spécifications  
 En-tête : msdbg.h  
  
 Espace de noms : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces principales](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)