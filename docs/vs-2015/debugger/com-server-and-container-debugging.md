---
title: Serveur COM et le débogage de conteneur | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.com
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- ActiveX control container debugging [Visual Studio]
- debugging ActiveX controls
- COM servers, debugging
- ActiveX controls, debugging
- COM [Visual Studio], debugging
ms.assetid: b7ce8696-ebb8-4354-a767-f76b8ada4ac1
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 531c485f50a4a775ca2933c40f5ff74ca9c43717
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47503690"
---
# <a name="com-server-and-container-debugging"></a>Débogage de serveurs et de conteneurs COM
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [serveur COM et le débogage de conteneur](https://docs.microsoft.com/visualstudio/debugger/com-server-and-container-debugging).  
  
Les applications COM effectuent des tâches en dehors du contrôle direct du programmeur. La communication entre les DLL, la fréquence d'utilisation des objets et les opérations du Presse-papiers sont quelques exemples pour lesquels un comportement inattendu peut se produire. Lorsque cela se produit, la première chose à faire est de trouver la source du problème.  
  
 Le débogueur Visual Studio prend en charge le pas à pas dans les conteneurs et les serveurs. Cela inclut la possibilité d'explorer pas à pas les appels de procédure à distance (RPC, Remote Procedure Calls).  
  
##  <a name="BKMK_COMServerandContainerintheSameSolution"></a> Débogage d’un serveur COM et un conteneur dans la même Solution  
 Vous pouvez déboguer un serveur et un conteneur COM en utilisant deux projets contenus dans la même solution. Définissez les points d'arrêt appropriés dans chaque projet et commencez le débogage. Lorsque le conteneur fait un appel au serveur qui rencontre un point d'arrêt, le conteneur attend que le code du serveur soit retourné (c'est-à-dire, jusqu'à ce que le débogage soit terminé).  
  
 Le débogage d'un conteneur COM est identique au débogage d'un programme standard. La seule différence se produit lorsque vous déboguez un événement qui génère un rappel (par exemple, le glissement de données sur l'application conteneur). Dans ce cas, vous devez définir un point d'arrêt dans la fonction de rappel.  
  
##  <a name="BKMK_ServerApplicationWithoutContainerInformation"></a> Débogage d’une Application serveur sans informations sur le conteneur  
 Si vous ne disposez pas d'informations de débogage pour votre application conteneur ou si vous ne voulez pas les utiliser, le débogage de l'application serveur se passe en trois étapes :  
  
1.  Commencez le débogage du serveur comme pour une application normale.  
  
2.  Définissez les points d'arrêt voulus.  
  
3.  Démarrez l'application conteneur.  
  
##  <a name="BKMK_DebuggingaServerandDomainIsolationSDIApplication"></a> Débogage d’une Application Server and Domain Isolation (SDI)  
 Si vous déboguez une application serveur SDI, vous devez spécifier `/Embedding` ou `/Automation` dans le **arguments de ligne de commande** propriété dans le *projet* boîte de dialogue Pages de propriétés pour C/C++, c#, ou Projets Visual Basic.  
  
 Avec ces arguments de la ligne de commande, le débogueur peut lancer l’application serveur comme si elle était lancée d’un conteneur. Le démarrage du conteneur à partir du Gestionnaire de programmes ou du Gestionnaire de fichiers entraîne l'utilisation par le conteneur de l'instance du serveur démarrée dans le débogueur.  
  
 Pour accéder à la *projet* boîte de dialogue Pages de propriétés, cliquez sur votre projet dans l’Explorateur de solutions, puis choisissez Propriétés dans le menu contextuel. Pour trouver la propriété Arguments de la ligne de commande, développez la catégorie Propriétés de configuration, puis cliquez sur la page Débogage.  
  
## <a name="see-also"></a>Voir aussi  
 [Débogage COM et ActiveX](../debugger/com-and-activex-debugging.md)



