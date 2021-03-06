---
title: Package de débogage | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: dda8b1ac6eaa2cd5352d441600ae720c3aac321c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68181294"
---
# <a name="debug-package"></a>Déboguer le package
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Le package de débogage s’exécute dans le shell Visual Studio et gère toute l’interface utilisateur. Il consomme les interfaces de débogage de Visual Studio et communique avec le gestionnaire de débogage de session (SDM).  
  
 Arrêter les événements envoyés via le commutateur SDM le débogueur du mode exécution au mode arrêt et changer le focus du programme où l’arrêt s’est produit. Le package de débogage effectue le suivi du frame de pile et du thread à partir des informations qui lui sont envoyées par les événements.  
  
 Le package de débogage n’a pas de dépendances d’environnement de langage ou d’exécution. Il n’est pas nécessaire d’implémenter ou de modifier le package de débogage.  
  
 Le package de débogage est implémenté par vsdebug.dll.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestionnaire de débogage de session](../../extensibility/debugger/session-debug-manager.md)   
 [Frames de pile](../../extensibility/debugger/stack-frames.md)   
 [Thèmes](../../extensibility/debugger/threads.md)   
 [Composants du débogueur](../../extensibility/debugger/debugger-components.md)
