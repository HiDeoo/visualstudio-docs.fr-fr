---
title: Les affectations de Port du débogueur distant | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 238bb4ec-bb00-4c2b-986e-18ac278f3959
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e44169c436eb3a164a418413341c1689b37a649f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47501327"
---
# <a name="remote-debugger-port-assignments"></a>Affectations de port du débogueur distant
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [Remote Debugger Port Assignments](https://docs.microsoft.com/visualstudio/debugger/remote-debugger-port-assignments).  
  
Le débogueur distant de Visual Studio peut s’exécuter comme une application ou un service en arrière-plan. Quand il est exécuté comme une application, il utilise un port qui est affecté par défaut comme suit :  
  
-   Visual Studio 2015 : 4020  
  
-   Visual Studio 2013 : 4018  
  
-   Visual Studio 2012 : 4016  
  
 En d’autres termes, le numéro de port attribué au débogueur distant est incrémenté de 2 pour chaque version. Vous pouvez définir un numéro de port différent si vous le souhaitez. Nous expliquerons comment définir des numéros de port dans une section ultérieure.  
  
## <a name="the-remote-debugger-port-on-32-bit-operating-systems"></a>Port du débogueur distant sur les systèmes d’exploitation 32 bits  
 Le port TCP 4020 (dans Visual Studio 2015) est le port principal, qui est requis pour tous les scénarios. Vous pouvez le configurer à partir de la ligne de commande ou de la fenêtre du débogueur distant.  
  
 Dans la fenêtre du débogueur distant, cliquez sur **Outils/Options**, puis définissez le numéro de port TCP/IP.  
  
 Sur la ligne de commande, démarrez le débogueur distant avec la **port d’insertion/** basculer : **msvsmon /port \<le numéro de port >**.  
  
 Tous les commutateurs de ligne de commande du débogueur distant sont disponibles dans l’aide du débogage distant (appuyez sur **F1** ou cliquez sur **Aide/Utilisation** dans la fenêtre du débogueur distant).  
  
## <a name="the-remote-debugger-port-on-64-bit-operating-systems"></a>Port du débogueur distant sur les systèmes d’exploitation 64 bits  
 Quand la version 64 bits du débogueur distant démarre, elle utilise le port 4020 par défaut.  Si vous déboguez un processus 32 bits, la version 64 bits du débogueur distant démarre une version 32 bits du débogueur distant sur le port 4021. Si vous exécutez le débogueur distant 32 bits, il utilise le port 4020 et 4021 n’est pas utilisé.  
  
 Ce port est configurable à partir de la ligne de commande : **Msvsmon /wow64port \<le numéro de port >**.  
  
## <a name="the-discovery-port"></a>Port de détection  
 UDP 3702 est utilisé pour rechercher des instances en cours d’exécution du débogueur distant sur le réseau (par exemple, la boîte de dialogue **Rechercher** dans la boîte de dialogue **Attacher au processus** ). Il est utilisé uniquement pour la découverte d’un ordinateur exécutant le débogueur distant ; il est facultatif si vous disposez d’une autre façon de connaître le nom ou l’adresse IP de l’ordinateur cible. Comme il s’agit d’un port standard pour la détection, le numéro de port ne peut pas être configuré.  
  
 Si vous ne souhaitez pas activer la détection, vous pouvez démarrer msvsmon à partir de la ligne de commande avec la détection désactivée :  **Msvsmon /nodiscovery**.  
  
## <a name="remote-debugger-ports-on-azure"></a>Port du débogueur distant sur Azure  
 Les ports suivants sont utilisés par le débogueur distant sur Azure. Les ports sur le service cloud sont mappés aux ports sur la machine virtuelle individuelle. Tous les ports sont TCP.  
  
||||  
|-|-|-|  
|**Connexion**|**Port sur le service cloud**|**Port sur la machine virtuelle**|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector|30400|30398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarder|31400|31398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.FileUpload|32400|32398|  
  
## <a name="see-also"></a>Voir aussi  
 [Débogage à distance](../debugger/remote-debugging.md)



