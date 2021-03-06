---
title: Une erreur DCOM s’est produite lors de la tentative de contact de l’ordinateur distant. Accès refusé. | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.remote.dcom_access_denied
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, DCOM error
- remote DCOM access denied error
- DCOM, access errors
ms.assetid: 9d7dfc1b-9fe0-4f54-9c50-9c0e0f8358c5
caps.latest.revision: 30
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0157b1ade2c38a2c10920b9674d7c9a58ac036b2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68156532"
---
# <a name="a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied"></a>Une erreur DCOM s’est produite lors de la tentative de contact de l’ordinateur distant. Accès refusé.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Le débogage distant utilise DCOM pour les communications entre l’ordinateur hôte et l’ordinateur distant dans les situations suivantes :  
  
- Le débogueur est défini sur **mode de compatibilité natif** ou le **mode de compatibilité managé** est activé dans la page **Outils/Options/débogage**  
  
- Vous déboguez du code C++ managé (C++/CLI).  
  
- Dans Visual Studio 2013, lorsque l’option **activer modifier & continuer natif** est cochée dans la page **Outils/Options/débogage**  
  
- Quelques scénarios de débogage tiers  
  
  Cette erreur se produit lorsque le processus Visual Studio ne peut pas s'authentifier (ou que les informations d'identification fournies ont été considérées inappropriées) lors du processus du débogueur distant sur DCOM. Une ou plusieurs des solutions suivantes peuvent résoudre le problème :  
  
- Désactivez  **Mode de compatibilité natif** et **Mode de compatibilité managé**.  
  
- Dans Visual Studio 2013, désactivez **Activer Modifier &amp; Continuer natif**.  
  
- Redémarrez les deux ordinateurs.  
  
- Si le débogage distant requiert la saisie des informations d'identification, activez l'option pour enregistrer les informations d'identification.  
  
## <a name="see-also"></a>Voir aussi  
 [Erreurs de débogage distant et dépannage](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Débogage à distance](../debugger/remote-debugging.md)
