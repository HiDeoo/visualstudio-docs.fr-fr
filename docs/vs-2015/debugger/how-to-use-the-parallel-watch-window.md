---
title: 'Comment : utiliser la fenêtre Espion parallèle | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.parallelwatch
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, parallel watch window
ms.assetid: 28004d9b-420c-48f7-b80e-ab1519802558
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 734a55cb06ee46afc6fc3518d6dffe349690d3d7
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "65697491"
---
# <a name="how-to-use-the-parallel-watch-window"></a>Comment : utiliser la fenêtre Espion parallèle
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans la fenêtre Espion parallèle, vous pouvez simultanément afficher les valeurs qu'une expression contient sur plusieurs threads. Chaque ligne représente un thread s'exécutant dans une application, mais un thread peut être représenté dans plusieurs lignes. Plus spécifiquement, chaque ligne représente un appel de fonction dont la signature de la fonction correspond à la fonctionnalité sur le frame de pile actuel. Vous pouvez trier, réorganiser, supprimer et regrouper les éléments qui figurent dans les colonnes. Vous pouvez marquer ou supprimer l'indicateur, figer et libérer (reprendre) les threads. Les colonnes suivantes sont affichées dans la fenêtre **Espion parallèle** :  
  
- La colonne d'indicateur, où vous pouvez marquer un thread auquel vous souhaitez apporter une attention spéciale.  
  
- La colonne de frame, dans laquelle une flèche indique le frame sélectionné.  
  
- Une colonne configurable qui peut afficher l’ordinateur, le processus, la mosaïque, la tâche et le thread.  
  
  > [!TIP]
  > Vous devez ouvrir la fenêtre de **tâche parallèle** pour afficher les informations sur la tâche dans la fenêtre **Espion parallèle** .  
  
- **\<Add Watch>** Colonne dans laquelle vous pouvez entrer des expressions à surveiller.  
  
  [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-display-the-parallel-watch-window"></a>Pour afficher la fenêtre Espion parallèle  
  
1. Définissez un point d'arrêt dans le code.  
  
2. Dans la barre de menus, choisissez **Débogage**, puis **Démarrer le débogage**. Attendez que l'application atteigne le point d'arrêt.  
  
3. Dans la barre de menus, sélectionnez **Déboguer**, **Fenêtres**, **Espion parallèle**, puis sélectionnez une fenêtre Espion. Vous pouvez ouvrir quatre fenêtres maximum.  
  
### <a name="to-add-a-watch-expression"></a>Pour ajouter une expression espionne  
  
- Sélectionnez **\<Add Watch>** , puis spécifiez une expression espionne.  
  
### <a name="to-flag-or-unflag-a-thread"></a>Pour marquer ou supprimer l'indicateur d'un thread  
  
- Sélectionnez la colonne d’indicateur pour la ligne, ou ouvrez le menu contextuel du thread et choisissez **marquer ou supprimer** l' **indicateur**.  
  
### <a name="to-display-only-flagged-threads"></a>Pour afficher seulement les threads avec indicateur  
  
- Choisissez le bouton afficher uniquement les indicateurs dans l’angle supérieur gauche de la fenêtre **Espion parallèle** .  
  
### <a name="to-switch-frames"></a>Pour basculer vers les frames  
  
- Double-cliquez sur la colonne de frame. (Raccourci : sélectionnez la ligne et appuyez sur Entrée.)  
  
### <a name="to-sort-a-column"></a>Pour trier une colonne  
  
- Sélectionnez le titre de la colonne.  
  
### <a name="to-group-threads"></a>Pour regrouper des threads  
  
- Ouvrez le menu contextuel de la fenêtre Espion parallèle, choisissez **Grouper par**, puis l’élément de sous-menu approprié.  
  
### <a name="to-freeze-or-thaw-threads"></a>Pour figer ou libérer les threads  
  
- Ouvrez le menu contextuel de la ligne par défaut et choisissez **Figer** ou **Libérer**.  
  
### <a name="to-export-the-data-in-the-parallel-watch-window"></a>Pour exporter les données dans la fenêtre Espion parallèle  
  
- Cliquez sur le bouton **Ouvrir dans Excel**, puis sélectionnez **Ouvrir dans Excel** ou **Exporter au format CSV**.  
  
### <a name="to-filter-by-a-boolean-expression"></a>Pour filtrer en fonction d'une expression booléenne  
  
- Entrez une expression booléenne dans la zone **Filtrer par expression booléenne**. Le débogueur évalue l'expression de chaque contexte de thread. Seules les lignes avec la valeur `true` sont affichées.  
  
## <a name="see-also"></a>Voir aussi  
 [Déboguer des applications multithread](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Comment : utiliser la fenêtre threads GPU](../debugger/how-to-use-the-gpu-threads-window.md)   
 [Procédure pas à pas : débogage d’une application C++ AMP](https://msdn.microsoft.com/library/40e92ecc-f6ba-411c-960c-b3047b854fb5)
