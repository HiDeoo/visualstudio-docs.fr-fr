---
title: 'Comment : déboguer un Service WCF auto-hébergé | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, self-hosted service
- WCF, debugging
ms.assetid: 288922be-ba3f-411e-af50-bba39c9529cc
caps.latest.revision: 28
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ec8f1fee46a1df931842992df1daa38942ca07bc
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49182245"
---
# <a name="how-to-debug-a-self-hosted-wcf-service"></a>Comment : déboguer un service WCF auto-hébergé
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Un *service auto-hébergé* est un service WCF qui ne s’exécute pas à l’intérieur d’IIS, l’hôte de Service WCF, ou le [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] serveur de développement. Pour déboguer un service WCF auto-hébergé le plus simple consiste à configurer [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pour lancer le client et serveur lorsque vous choisissez **démarrer le débogage** sur le **déboguer** menu.  
  
 Si le service WCF est auto-hébergé dans un processus qui ne peut pas être lancé de cette manière, tel que service NT, vous ne pouvez pas utiliser cette méthode. Au lieu de cela, vous pouvez effectuer l’une des opérations suivantes :  
  
-   Attacher manuellement le débogueur au processus d’hébergement. Pour plus d’informations, consultez [attacher aux processus en cours d’exécution](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
     — ou —  
  
-   Démarrer le débogage du client et puis détaillé dans un appel au service. Cela nécessite que vous activez le débogage dans le fichier app.config. Pour plus d’informations, [Limitations du débogage WCF](../debugger/limitations-on-wcf-debugging.md).  
  
### <a name="to-start-both-client-and-host-from-visual-studio"></a>Pour démarrer les clients et hôtes à partir de Visual Studio  
  
1.  Créer un [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] solution qui contient à la fois les projets client et serveur.  
  
2.  Configurer la solution pour démarrer le processus client et serveur lorsque vous choisissez **Démarrer** sur le **déboguer** menu.  
  
    1.  Dans **l’Explorateur de solutions**, cliquez sur le nom de la solution.  
  
    2.  Cliquez sur **définir les projets de démarrage**.  
  
    3.  Dans le **Solution \<nom > Propriétés** boîte de dialogue, sélectionnez **plusieurs projets de démarrage**.  
  
    4.  Dans le **plusieurs projets de démarrage** grille, sur la ligne qui correspond au projet serveur, cliquez sur **Action** et choisissez **Démarrer**.  
  
    5.  Sur la ligne qui correspond au projet client, cliquez sur **Action** et choisissez **Démarrer**.  
  
    6.  Cliquez sur **OK**.  
  
## <a name="see-also"></a>Voir aussi  
 [Débogage de Services WCF](../debugger/debugging-wcf-services.md)   
 [Limitations du débogage WCF](../debugger/limitations-on-wcf-debugging.md)   
 [Guide pratique pour effectuer un pas à pas détaillé dans les services WCF](../debugger/how-to-step-into-wcf-services.md)



