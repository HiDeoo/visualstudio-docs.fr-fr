---
title: 'Erreur : vous n’êtes pas autorisé à inspecter l’identité du processus&#39;s | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 6233d060-85b8-42be-ae5f-bde7e1d0f241
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d66eacb1b7f5205ea430d7154f67d05bdd047a74
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68157521"
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>Erreur : vous n’êtes pas autorisé à inspecter l’identité du processus&#39;s
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous n'êtes pas autorisé à inspecter l'identité du processus. Cela peut être dû à la configuration de votre système.  
  
 Le débogueur n'a pas pu inspecter l'identité du processus, qui contient des informations nécessaires au débogage. La cause la plus probable est la désactivation des services Terminal Server. Les services Terminal Server sont activés par défaut. Pour les réactiver, procédez comme suit.  
  
### <a name="to-enable-terminal-services"></a>Pour activer les services Terminal Server  
  
1. Cliquez sur **Démarrer** , puis sur **panneau de configuration**.  
  
2. Dans le panneau de configuration, choisissez **basculer vers l’affichage classique**, si nécessaire, puis double-cliquez sur **Outils d’administration**.  
  
3. Dans la fenêtre **Outils d’administration**, double-cliquez sur **Gestion de l’ordinateur**.  
  
4. Dans la fenêtre Gestion de l’ordinateur, développez le nœud **Services et applications**.  
  
5. Sous **Services et applications**, cliquez sur **Services**.  
  
     Une liste de services apparaît dans le volet droit.  
  
6. Dans la liste **Services**, cliquez avec le bouton droit sur **Services Terminal Server**, puis choisissez **Propriétés**.  
  
7. Dans la fenêtre **Propriétés des services Terminal Server** , accédez à l’onglet **général** et définissez **type de démarrage** sur **Manuel**.  
  
8. Cliquez sur **OK**.  
  
9. Redémarrez l’ordinateur.  
  
     Cette procédure n'active pas automatiquement le Bureau à distance. Pour activer le Bureau à distance sur votre ordinateur, effectuez la procédure supplémentaire suivante.  
  
### <a name="to-enable-remote-desktop"></a>Pour activer le Bureau à distance  
  
1. Cliquez sur **Démarrer**, puis cliquez avec le bouton droit sur **Poste de travail**.  
  
2. Choisissez **Propriétés**.  
  
     La fenêtre **Propriétés système** s’affiche.  
  
3. Cliquez sur **Distant**.  
  
4. Sous **Bureau à distance**, sélectionnez **Autoriser les utilisateurs à se connecter à distance à cet ordinateur**.  
  
5. Cliquez sur **OK**.  
  
## <a name="see-also"></a>Voir aussi  
 [Erreurs de débogage distant et dépannage](../debugger/remote-debugging-errors-and-troubleshooting.md)
