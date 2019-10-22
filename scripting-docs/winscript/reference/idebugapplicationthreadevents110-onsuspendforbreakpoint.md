---
title: 'IDebugApplicationThreadEvents110 :: OnSuspendForBreakPoint | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThreadEvents110::OnSuspendForBreakPoint
ms.assetid: 224245ac-2aa2-43ae-97ed-493afc3d0122
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b5d73d7769dd48889a75da63da64be1d2977a088
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573336"
---
# <a name="idebugapplicationthreadevents110onsuspendforbreakpoint"></a>IDebugApplicationThreadEvents110::OnSuspendForBreakPoint
Détermine si le thread a été complètement suspendu pour un point d’arrêt et n’a pas encore repris l’exécution normale.  
  
> [!IMPORTANT]
> L' [interface IDebugApplicationThreadEvents110](../../winscript/reference/idebugapplicationthreadevents110-interface.md) est implémentée par PDM v 11.0 et ultérieur. Trouvée dans activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT OnSuspendForBreakPoint( void );  
```  
  
#### <a name="parameters"></a>Paramètres  
 Cette méthode n’a aucun paramètre.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugApplicationThreadEvents110 Interface](../../winscript/reference/idebugapplicationthreadevents110-interface.md)