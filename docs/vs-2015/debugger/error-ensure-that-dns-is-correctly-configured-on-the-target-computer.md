---
title: 'Erreur : Assurez-vous que le DNS est correctement configuré sur l’ordinateur cible | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.callback_dns_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 2d364caf-73af-4186-bf9b-af186331cbe8
caps.latest.revision: 9
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 35c258a018bec8bd38f8b43690c18b37ee9d6c39
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75851932"
---
# <a name="error-ensure-that-dns-is-correctly-configured-on-the-target-computer"></a>Erreur : Assurez-vous que DNS est correctement configuré sur l'ordinateur cible
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Si vous essayez d'effectuer un débogage distant, vous risquez de recevoir ce message d'erreur :  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Ensure that DNS is correctly configured on the target computer.  
```  
  
 Cette erreur se produit lorsque l'ordinateur cible ne peut pas résoudre le nom de l'ordinateur hôte du débogueur Visual Studio. Vérifiez les paramètres DNS sur l'ordinateur cible.  
  
- Pour plus d’informations sur l’affichage de votre paramètre de DNS dans Windows 8.1, Vista, Windows 7, Windows Server 2012, Windows Server 2008 ou Windows Server 2008 R2, procédez comme suit : sur le menu **Démarrer**, choisissez **Aide et support**, puis recherchez **Changer les paramètres TCP/IP**.  
  
- Pour plus d’informations, accédez au [site Web Microsoft Windows](https://windows.microsoft.com/) et recherchez **modifier les paramètres TCP/IP**.  
  
  Si vous ne pouvez pas résoudre le problème DNS, vous pouvez essayer d'exécuter le débogueur distant sous un compte différent. Cette erreur se produit uniquement lorsque vous exécutez le débogueur distant sous le compte système local ou le compte de service réseau. Si vous exécutez le débogueur distant sous un autre compte, il peut utiliser l'authentification NTLM, qui ne nécessite pas de DNS. . Pour la procédure, consultez [erreur : le service débogueur distant Visual Studio sur l’ordinateur cible ne peut pas se reconnecter à cet ordinateur](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).
