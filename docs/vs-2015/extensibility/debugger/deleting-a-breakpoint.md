---
title: Suppression d’un point d’arrêt | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- breakpoints, deleting
- debugging [Debugging SDK], deleting breakpoints
ms.assetid: 75a046cc-d20a-4c79-ad2d-1f18426ac5d0
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8b20ac5b76dfcd24e0dbed5fbc08720c33d88fdd
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49254083"
---
# <a name="deleting-a-breakpoint"></a>Suppression d’un point d’arrêt
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

La section suivante décrit le processus lors de la suppression d’un point d’arrêt en attente :  
  
## <a name="deletion-process"></a>Processus de suppression  
 Le Gestionnaire de session de débogage (SDM) appelle le [IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md) méthode pour supprimer le point d’arrêt en attente et les points d’arrêt liés liée à partir de celui-ci.  
  
> [!NOTE]
>  Un seul point d’arrêt lié peut également être supprimée par un appel à [IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Événements d’appel du débogueur](../../extensibility/debugger/calling-debugger-events.md)

