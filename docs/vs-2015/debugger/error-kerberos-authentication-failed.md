---
title: 'Erreur : échec de l’authentification Kerberos | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.callback_kerberos_auth_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: c18053f9-9074-4bc3-a8bf-13e4acbea921
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b5e85bc7a5bac87692448aab393056fa1db5edbd
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "62535632"
---
# <a name="error-kerberos-authentication-failed"></a>Erreur : L'authentification Kerberos a échoué
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Lorsque vous essayez d'effectuer un débogage distant, le message d'erreur suivant peut s'afficher :  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Kerberos auythentication failed.  
```  
  
 Cette erreur se produit lorsque Visual Studio Remote Debugging Monitor est exécuté sous le compte Système local ou Service réseau. Sous l'un de ces comptes, le débogueur distant doit établir une connexion d'authentification Kerberos pour communiquer avec l'ordinateur hôte du débogueur Visual Studio.  
  
 L'authentification Kerberos n'est pas disponible dans les conditions suivantes :  
  
- L'ordinateur cible ou l'ordinateur hôte du débogueur est situé sur un groupe de travail, au lieu d'un domaine.  
  
   \- ou -  
  
- Kerberos a été désactivé sur le contrôleur de domaine.  
  
  Si l'authentification Kerberos n'est pas disponible, modifiez le compte utilisé pour exécuter Visual Studio Remote Debugging Monitor. Pour la procédure, consultez [erreur : le service débogueur distant Visual Studio sur l’ordinateur cible ne peut pas se reconnecter à cet ordinateur](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).  
  
  Si ce message s'affiche encore alors que les deux ordinateurs sont connectés au même domaine, vérifiez que le DNS sur l'ordinateur cible résout correctement le nom de l'ordinateur hôte du débogueur. Consultez la procédure suivante.  
  
### <a name="to-verify-that-dns-on-the-target-computer-is-correctly-resolving-the-debugger-host-computer-name"></a>Pour vérifier que le DNS sur l'ordinateur cible résout correctement le nom de l'ordinateur hôte du débogueur  
  
1. Sur l’ordinateur cible, ouvrez le menu **Démarrer**, pointez sur **Accessoires**, puis cliquez sur **Invite de commandes**.  
  
2. Dans la fenêtre d' **invite de commandes** , tapez :  
  
    ```  
    ping <debugger_host_computer_name>  
    ```  
  
3. La première ligne de la réponse `ping` affiche le nom complet et l'adresse IP renvoyés par le DNS pour l'ordinateur spécifié.  
  
4. Sur l’ordinateur hôte du débogueur, ouvrez une fenêtre **Invite de commandes** et exécutez `ipconfig`.  
  
5. Comparez les valeurs d'adresse IP.  
  
## <a name="see-also"></a>Voir aussi  
 [Erreurs de débogage distant et dépannage](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Débogage à distance](../debugger/remote-debugging.md)
