---
title: Période de synchronisation | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.synchronization
helpviewer_keywords:
- Concurrency Visualizer, Synchronization Time
ms.assetid: affa04cc-8bba-4848-9301-b19846d3c2cb
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76775ca0270b46c17506106640ba2d68e795049b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51755389"
---
# <a name="synchronization-time"></a>Durée de synchronisation
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ces segments de la chronologie sont associés à des périodes de blocage classées dans la catégorie Synchronisation. Quand un thread est marqué comme bloqué sur la synchronisation, cela implique une de ces situations :  
  
- L’exécution du thread peut avoir abouti à un appel à une API de synchronisation de threads connue, comme `EnterCriticalSection()` ou `WaitForSingleObject()`.  
  
- L’algorithme correspondant de l’API ne peut pas être entièrement exhaustif et par conséquent, certaines API qui peuvent être mappées à d’autres catégories peuvent également apparaître comme étant une synchronisation, car une trame dans la pile des appels a finalement atteint une primitive de blocage du noyau sous-jacent qui a été mappée à cette catégorie.  
  
  Pour comprendre la cause sous-jacente d’un événement de blocage de thread, examinez attentivement les piles des appels bloquants et les rapports de profil.  
  
## <a name="see-also"></a>Voir aussi  
 [vue Threads](../profiling/threads-view-parallel-performance.md)



