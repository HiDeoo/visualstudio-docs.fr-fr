---
title: Débogage de serveur et de conteneur COM | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
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
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 631b1d35a0878bfc362b03751f35909839c7da19
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68161556"
---
# <a name="com-server-and-container-debugging"></a>Débogage de serveurs et de conteneurs COM
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Les applications COM effectuent des tâches en dehors du contrôle direct du programmeur. La communication entre les DLL, la fréquence d'utilisation des objets et les opérations du Presse-papiers sont quelques exemples pour lesquels un comportement inattendu peut se produire. Lorsque cela se produit, la première chose à faire est de trouver la source du problème.  
  
 Le débogueur Visual Studio prend en charge le pas à pas dans les conteneurs et les serveurs. Cela inclut la possibilité d'explorer pas à pas les appels de procédure à distance (RPC, Remote Procedure Calls).  
  
## <a name="debugging-a-com-server-and-container-in-the-same-solution"></a><a name="BKMK_COMServerandContainerintheSameSolution"></a> Débogage d’un serveur COM et d’un conteneur dans la même solution  
 Vous pouvez déboguer un serveur et un conteneur COM en utilisant deux projets contenus dans la même solution. Définissez les points d'arrêt appropriés dans chaque projet et commencez le débogage. Lorsque le conteneur fait un appel au serveur qui rencontre un point d'arrêt, le conteneur attend que le code du serveur soit retourné (c'est-à-dire, jusqu'à ce que le débogage soit terminé).  
  
 Le débogage d'un conteneur COM est identique au débogage d'un programme standard. La seule différence se produit lorsque vous déboguez un événement qui génère un rappel (par exemple, le glissement de données sur l'application conteneur). Dans ce cas, vous devez définir un point d'arrêt dans la fonction de rappel.  
  
## <a name="debugging-a-server-application-without-container-information"></a><a name="BKMK_ServerApplicationWithoutContainerInformation"></a> Débogage d’une application serveur sans informations sur le conteneur  
 Si vous ne disposez pas d'informations de débogage pour votre application conteneur ou si vous ne voulez pas les utiliser, le débogage de l'application serveur se passe en trois étapes :  
  
1. Commencez le débogage du serveur comme pour une application normale.  
  
2. Définissez les points d'arrêt voulus.  
  
3. Démarrez l'application conteneur.  
  
## <a name="debugging-a-server-and-domain-isolation-sdi-application"></a><a name="BKMK_DebuggingaServerandDomainIsolationSDIApplication"></a> Débogage d’une application SDI (Server and Domain Isolation)  
 Si vous déboguez une application serveur SDI, vous devez spécifier `/Embedding` ou `/Automation` dans la propriété **Arguments de la ligne de commande** de la boîte de dialogue Pages de propriétés de *projet* pour les projets C/C++, C# ou Visual Basic.  
  
 Avec ces arguments de la ligne de commande, le débogueur peut lancer l'application serveur comme si elle était lancée d'un conteneur. Le démarrage du conteneur à partir du Gestionnaire de programmes ou du Gestionnaire de fichiers entraîne l'utilisation par le conteneur de l'instance du serveur démarrée dans le débogueur.  
  
 Pour accéder à la boîte de dialogue Pages de propriétés de *projet*, cliquez avec le bouton droit sur votre projet dans l’Explorateur de solutions, puis sélectionnez Propriétés dans le menu contextuel. Pour trouver la propriété Arguments de la ligne de commande, développez la catégorie Propriétés de configuration, puis cliquez sur la page Débogage.  
  
## <a name="see-also"></a>Voir aussi  
 [Débogage COM et ActiveX](../debugger/com-and-activex-debugging.md)
