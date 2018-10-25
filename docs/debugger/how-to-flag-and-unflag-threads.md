---
title: 'Comment : ajouter et supprimer les indicateurs des Threads | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- treads, switching [debugging]
ms.assetid: 952d579d-6911-413e-b3e5-54e7e797e70c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 09d26c87867e071b7dafce80d95e4bc46cb88bb8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49891373"
---
# <a name="how-to-flag-and-unflag-threads"></a>Comment : ajouter et supprimer les indicateurs des threads
Vous pouvez signaler un thread auquel vous souhaitez accorder une attention particulière en le marquant avec une icône dans le **Threads**, **piles parallèles** (vue de thread), **espion parallèle**et  **Threads GPU** windows. Cette icône vous aide, ainsi que d'autres, à distinguer les threads avec indicateur des autres threads.  
  
Threads avec indicateur bénéficient d’un traitement spécial dans le **Thread** liste sur le **emplacement de débogage** barre d’outils et dans les autres fenêtres de débogage multithreads. Vous pouvez afficher tous les threads ou uniquement les threads avec indicateur dans le **Thread** liste ou dans les autres fenêtres.
  
### <a name="to-flag-or-unflag-a-thread"></a>Pour marquer ou supprimer l'indicateur d'un thread 
  
- Dans le **Threads** ou **espion parallèle** fenêtre, recherchez le thread qui vous intéresse et cliquez sur l’icône d’indicateur pour activer ou désactiver l’indicateur. 
- Dans le **piles parallèles** fenêtre, avec le bouton droit sur un thread ou un groupe de threads et sélectionnez **indicateur / <thread>**  ou **supprimer l’indicateur / <thread>** .
  
### <a name="to-unflag-all-threads"></a>Pour supprimer tous les indicateurs de thread  
  
-   Dans le **Threads** fenêtre, avec le bouton droit n’importe quel thread, puis cliquez sur **supprimer l’indicateur de tous les Threads**.
-   Dans le **espion parallèle** fenêtre, sélectionnez tous les threads avec indicateur, puis avec le bouton droit et sélectionnez **supprimer l’indicateur**.  
  
### <a name="to-display-only-flagged-threads"></a>Pour afficher seulement les threads avec indicateur  
  
-   Choisissez le **afficher les Threads avec indicateur uniquement** bouton dans une des fenêtres de débogage multithreads.  
  
### <a name="to-flag-just-my-code"></a>Pour signaler Uniquement mon code  
  
1.  Dans la barre d’outils en haut de la **Threads** fenêtre, cliquez sur l’icône d’indicateur.  
  
2.  Dans la liste déroulante, cliquez sur **signaler uniquement mon Code**.  
  
### <a name="to-flag-threads-that-are-associated-with-selected-modules"></a>Pour signaler des threads associés aux modules sélectionnés  
  
1.  Dans la barre d’outils de la **Threads** fenêtre, cliquez sur l’icône d’indicateur.  
  
2.  Dans la liste déroulante, cliquez sur **signaler la sélection de Module personnalisé**.  
  
3.  Dans le **sélectionner les Modules** boîte de dialogue, sélectionnez les modules que vous souhaitez.  
  
4.  (Facultatif) Dans le **recherche** , tapez une chaîne à rechercher des modules spécifiques.  
  
5.  Cliquez sur **OK**.  
  
## <a name="see-also"></a>Voir aussi  
 [Déboguer les Applications multithread](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Commencer le débogage d’applications multithread](../debugger/get-started-debugging-multithreaded-apps.md)  
 [Procédure pas à pas : Débogage d’applications multithread à l’aide de la fenêtre Threads](../debugger/how-to-use-the-threads-window.md)