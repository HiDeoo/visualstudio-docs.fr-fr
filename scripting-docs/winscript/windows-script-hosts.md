---
title: Hôtes Windows Script | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Windows Script Host, implementing hosts
ms.assetid: 9d5f6471-b318-40f3-be01-d9cd0b1cdd47
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 51053dec1f8362aa9eef80e4867d2f92a06454cb
ms.sourcegitcommit: 9a9c61ca115c22d33bb902153eb0853789c7be4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85835327"
---
# <a name="windows-script-hosts"></a>Windows Script Hosts
Quand vous implémentez un hôte Microsoft Windows Script, vous pouvez raisonnablement supposer qu’un moteur de script appelle uniquement l’interface [IActiveScriptSite](../winscript/reference/iactivescriptsite.md) dans le contexte du thread de base, et ce tant que l’hôte effectue les opérations suivantes :  
  
- Choisit un thread de base (généralement le thread qui contient la boucle de messages).  
  
- Instancie le moteur de script dans le thread de base.  
  
- Appelle les méthodes du moteur de script uniquement à partir du thread de base, sauf aux emplacements spécifiquement autorisés, comme avec [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) et [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md).  
  
- Appelle l’objet de répartition du moteur de script uniquement à partir du thread de base.  
  
- Garantit que la boucle de messages s’exécute dans le thread de base si un handle de fenêtre est fourni.  
  
- Garantit que les objets dans le modèle objet de l’hôte approvisionnent uniquement des événements dans le thread de base.  
  
  Ces règles sont suivies automatiquement par tous les hôtes à thread unique. Le modèle restreint décrit ci-dessus a été intentionnellement conçu de manière assez souple pour permettre à un hôte d’abandonner un script bloqué en appelant [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) à partir d’un autre thread (lancé par un gestionnaire Ctrl+Pause ou similaire) ou de dupliquer un script dans un nouveau thread en utilisant [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md).  
  
## <a name="remarks"></a>Remarques  
 Aucune de ces restrictions ne s’applique à un hôte qui choisit d’implémenter une interface [IActiveScriptSite](../winscript/reference/iactivescriptsite.md) à threads libres et un modèle objet à threads libres. Un tel hôte peut utiliser l’interface [IActiveScript](../winscript/reference/iactivescript.md) à partir de n’importe quel thread, sans restriction.  
  
## <a name="see-also"></a>Voir aussi  
 [Windows Script, interfaces](../winscript/windows-script-interfaces.md)