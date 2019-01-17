---
title: Interface IDebugApplicationNodeEvents | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNodeEvents interface
ms.assetid: 02e0bb17-84ce-458b-bae6-608a9899e535
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0396ed90437a98c8ee398f3c3acb0aeb5ddc77e2
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348410"
---
# <a name="idebugapplicationnodeevents-interface"></a>IDebugApplicationNodeEvents, interface
Fournit l’interface d’événement pour l’interface `IDebugApplicationNode`.  
  
 Outre les méthodes héritées de `IUnknown`, le `IDebugApplicationNodeEvents` interface expose les méthodes suivantes.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
  
|Méthode|Description|  
|------------|-----------------|  
|[IDebugApplicationNodeEvents::onAddChild](../../winscript/reference/idebugapplicationnodeevents-onaddchild.md)|Gère l’événement lorsqu’un nœud enfant est ajouté à un objet de nœud d’application de débogage.|  
|[IDebugApplicationNodeEvents::onRemoveChild](../../winscript/reference/idebugapplicationnodeevents-onremovechild.md)|Gère l’événement lorsqu’un nœud enfant est supprimé à partir d’un objet de nœud d’application de débogage.|  
|[IDebugApplicationNodeEvents::onDetach](../../winscript/reference/idebugapplicationnodeevents-ondetach.md)|Gère un événement, ce qui signifie que l’objet de nœud d’application debug a été détachée d’un nœud parent.|  
|[IDebugApplicationNodeEvents::onAttach](../../winscript/reference/idebugapplicationnodeevents-onattach.md)|Gère un événement, ce qui signifie que l’objet de nœud d’application debug a été attaché à un nœud parent.|  
  
## <a name="see-also"></a>Voir aussi  
 [Interface IDebugApplicationNode](../../winscript/reference/idebugapplicationnode-interface.md)