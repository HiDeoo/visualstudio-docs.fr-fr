---
title: IDebugMemoryContext2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugMemoryContext2
helpviewer_keywords:
- IDebugMemoryContext2 interface
ms.assetid: 3a544c8b-11dc-46bb-8549-261e4ac5bbc4
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6f5a0533e2f7ce50dce7ccdf1285e4ab28a4b7a4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68146353"
---
# <a name="idebugmemorycontext2"></a>IDebugMemoryContext2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette interface représente une position dans l’espace d’adressage de l’ordinateur qui exécute le programme en cours de débogage.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugMemoryContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes pour les implémenteurs  
 Le moteur DE débogage (DE) implémente cette interface pour représenter une adresse en mémoire.  
  
## <a name="notes-for-callers"></a>Notes pour les appelants  
 Un appel à [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) ou [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md) retourne cette interface. En outre, les appels à [Add](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md) et [Subtract](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md) retournent de nouvelles copies de cette interface après l’application de l’opération arithmétique appropriée.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le tableau suivant présente les méthodes de `IDebugMemoryContext2` .  
  
|Méthode|Description|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugmemorycontext2-getname.md)|Obtient le nom affichable par l’utilisateur pour ce contexte.|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)|Obtient des informations qui décrivent ce contexte.|  
|[Ajouter](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)|Ajoute une valeur spécifiée à l’adresse du contexte actuel pour créer un nouveau contexte.|  
|[Soustraire](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)|Soustrait une valeur spécifiée de l’adresse du contexte actuel pour créer un nouveau contexte.|  
|[Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)|Compare deux contextes de la manière indiquée par les indicateurs de comparaison.|  
  
## <a name="remarks"></a>Notes  
 La fenêtre de **mémoire** de Visual Studio appelle [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) pour obtenir l' `IDebugMemoryContext2` interface qui contient l’expression évaluée utilisée pour l’adresse mémoire. Ce contexte est ensuite transmis à [readatum](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) et [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md) pour spécifier l’adresse à lire ou à écrire.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg. h  
  
 Espace de noms : Microsoft. VisualStudio. Debugger. Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces principales](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)   
 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)   
 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)
