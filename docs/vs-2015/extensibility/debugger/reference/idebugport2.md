---
title: IDebugPort2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPort2
helpviewer_keywords:
- IDebugPort2 interface
ms.assetid: 8fd87f05-a950-4d14-b925-98be29d4facc
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c9227e2e05499feac628a5b90fc6e3d2a4399992
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68188563"
---
# <a name="idebugport2"></a>IDebugPort2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette interface représente un port de débogage sur un ordinateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPort2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes pour les implémenteurs  
 Un fournisseur de port personnalisé implémente cette interface pour représenter un port de débogage sur un ordinateur.  
  
 Si le port prend en charge l’envoi d’événements de port, il doit également implémenter l' <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> interface pour prendre en charge une <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> interface qui fournit à son tour l’interface [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) .  
  
## <a name="notes-for-callers"></a>Notes pour les appelants  
 Les appels à [GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md) ou [addport](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) retournent cette interface, représentant le port demandé.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le tableau suivant présente les méthodes de `IDebugPort2` .  
  
|Méthode|Description|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugport2-getportname.md)|Retourne le nom du port.|  
|[GetPortId](../../../extensibility/debugger/reference/idebugport2-getportid.md)|Retourne l’identificateur de port.|  
|[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)|Retourne la requête utilisée pour créer un port (si disponible).|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)|Retourne le fournisseur de port pour ce port.|  
|[GetProcess,](../../../extensibility/debugger/reference/idebugport2-getprocess.md)|Retourne une interface au processus en fonction de l’identificateur du processus.|  
|[EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)|Énumère tous les processus en cours d’exécution sur un port.|  
  
## <a name="remarks"></a>Notes  
 Le port local permet d’accéder à tous les processus et programmes en cours d’exécution sur l’ordinateur local. D’autres ports peuvent représenter une connexion de câble série à un appareil Windows CE ou une connexion réseau à un ordinateur non-DCOM. L' `IDebugPort2` interface permet de rechercher le nom et l’identificateur d’un port, d’énumérer tous les processus en cours d’exécution sur le port et de fournir des fonctionnalités de lancement et de fin des processus sur le port.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg. h  
  
 Espace de noms : Microsoft. VisualStudio. Debugger. Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces principales](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)
