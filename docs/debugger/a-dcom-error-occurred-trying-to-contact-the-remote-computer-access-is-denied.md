---
title: Une erreur DCOM s’est produite lors de la tentative de contact de l’ordinateur distant. Accès refusé. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.remote.dcom_access_denied
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, DCOM error
- remote DCOM access denied error
- DCOM, access errors
ms.assetid: 9d7dfc1b-9fe0-4f54-9c50-9c0e0f8358c5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 193c93e7c29d3ea9fa13c08c9d77e4e88026d814
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49900512"
---
# <a name="a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied"></a>Une erreur DCOM s’est produite lors de la tentative de contact de l’ordinateur distant. Accès refusé.
Le débogage distant utilise DCOM pour les communications entre l’ordinateur hôte et l’ordinateur distant dans les situations suivantes :  
  
- Le débogueur est défini sur **Mode de compatibilité natif** ou **Mode de compatibilité managé** est archivé le **Outils > Options > débogage** page  
  
- Vous déboguez du code C++ managé (C++/CLI).  
  
- Dans Visual Studio 2013, lorsque **Activer Modifier & Continuer native** est archivé le **Outils > Options > débogage** page  
  
- Quelques scénarios de débogage tiers  
  
  Cette erreur se produit lorsque le processus Visual Studio ne peut pas s'authentifier (ou que les informations d'identification fournies ont été considérées inappropriées) lors du processus du débogueur distant sur DCOM. Une ou plusieurs des solutions suivantes peuvent résoudre le problème :  
  
- Désactivez  **Mode de compatibilité natif** et **Mode de compatibilité managé**.  
  
- Dans Visual Studio 2013, désactivez **Activer Modifier &amp; Continuer natif**.  
  
- Redémarrez les deux ordinateurs.  
  
- Si le débogage distant requiert la saisie des informations d'identification, activez l'option pour enregistrer les informations d'identification.  
  
## <a name="see-also"></a>Voir aussi  
 [Erreurs de débogage distant et dépannage](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)