---
title: 'Avertissement de sécurité : L’attachement à un processus appartenant à un utilisateur non approuvé peut être dangereux. Si les informations suivantes semblent suspectes ou si vous avez des doutes, n’attachez pas ce processus | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.attachsecuritywarning
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 52246c1e-a371-40a0-b756-a435cc51876f
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1c200ec88180b7ee71913c7047f5fc8afb848274
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49221700"
---
# <a name="security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process"></a>Avertissement de sécurité : L’attachement à un processus appartenant à un utilisateur non approuvé peut être dangereux. Si les informations suivantes semblent suspectes ou si vous avez des doutes, ne faites pas d’attachement à ce processus
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette boîte de dialogue d'avertissement s'affiche lorsque vous effectuez un attachement à un processus qui contient un code de niveau de confiance partiel ou qui appartient à un utilisateur non fiable, juste avant l'attachement. Un processus non fiable qui contient un code malveillant a la possibilité d'endommager l'ordinateur qui effectue le débogage. Si vous avez raison méfier du processus, vous devez cliquer sur **Annuler** pour empêcher le débogage.  
  
 Pour supprimer cet avertissement lors du débogage d’un scénario légitime, fermez Visual Studio et définissez la valeur de cette clé de Registre sur 1 : `HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\<version>\Debugger\DisableAttachSecurityWarning`, puis redémarrez Visual Studio. Après avoir terminé le débogage du scénario, réinitialisez la valeur à 0, et redémarrez Visual Studio.  
  
 Outre vous-même, les « utilisateurs de confiance » comprennent un ensemble d'utilisateurs standard qui sont généralement définis sur des ordinateurs sur lesquels le .NET Framework est installé, comme `aspnet`, `localsystem`, `networkservice` et `localservice`.  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 Name  
 Nom de l'assembly à déboguer  
  
 Utilisateur  
 Utilisateur actuel  
  
 Attach  
 Cliquez pour poursuivre le débogage après attachement  
  
 Ne pas attacher  
 Ne pas attacher au processus  
  
## <a name="see-also"></a>Voir aussi  
 [Attacher au processus en cours d’exécution](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Sécurité du débogueur](../debugger/debugger-security.md)



