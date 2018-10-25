---
title: Guide pratique pour exclure des projets d’une build | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17a837ca-5db9-46cd-b5a7-b14ad1d2c47d
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6419d2aa216f625aaf82087f0dc8f453e0d0d475
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49941839"
---
# <a name="how-to-exclude-projects-from-a-build"></a>Guide pratique pour exclure des projets d'une build
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez générer une solution sans générer tous les projets qu'elle contient. Par exemple, vous pouvez exclure un projet qui interrompt la génération. Vous pouvez ensuite générer le projet, une fois les problèmes identifiés et résolus.  
  
 Vous pouvez exclure un projet en adoptant les approches suivantes :  
  
- Suppression temporaire du projet de la configuration de solution active.  
  
- Création d'une configuration de solution qui n'inclut pas le projet.  
  
  Pour plus d’informations, consultez [Présentation des configurations de build](../ide/understanding-build-configurations.md).  
  
### <a name="to-temporarily-remove-a-project-from-the-active-solution-configuration"></a>Pour supprimer temporairement un projet de la configuration de solution active  
  
1.  Dans la barre de menus, choisissez **Générer**, puis **Gestionnaire de configurations**.  
  
2.  Dans le tableau **Contextes des projets**, localisez le projet que vous souhaitez exclure de la génération.  
  
3.  Dans la colonne **Build** pour le projet, décochez la case.  
  
4.  Choisissez le bouton **Fermer**, puis régénérez la solution.  
  
### <a name="to-create-a-solution-configuration-that-excludes-a-project"></a>Pour créer une configuration de solution qui exclut un projet  
  
1.  Dans la barre de menus, choisissez **Générer**, puis **Gestionnaire de configurations**.  
  
2.  Dans la liste **Configuration de la solution active**, choisissez **\<Nouveau>**.  
  
3.  Dans la zone **Nom**, entrez un nom pour la configuration de solution.  
  
4.  Dans la liste **Copier les paramètres à partir de**, choisissez la configuration de solution sur laquelle vous souhaitez baser la nouvelle configuration (par exemple, **Déboguer**), puis choisissez le bouton **OK**.  
  
5.  Dans la boîte de dialogue **Gestionnaire de configurations**, décochez la case dans la colonne **Build** pour le projet que vous souhaitez exclure, puis choisissez le bouton **Fermer**.  
  
6.  Dans la barre d’outils **Standard**, vérifiez que la nouvelle configuration de solution est la configuration active dans la zone **Configurations de solutions**.  
  
7.  Dans la barre de menus, choisissez **Générer**, **Régénérer la solution**.  
  
## <a name="see-also"></a>Voir aussi  
 [Présentation des configurations de build](../ide/understanding-build-configurations.md)   
 [Guide pratique pour créer et modifier des configurations](../ide/how-to-create-and-edit-configurations.md)   
 [Guide pratique pour créer plusieurs configurations simultanément](../ide/how-to-build-multiple-configurations-simultaneously.md)



