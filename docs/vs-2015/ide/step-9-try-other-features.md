---
title: 'Étape 9 : Essayez d’autres fonctionnalités | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 1b0c5c80-e5a6-4f69-a4a4-0e89a82d4de0
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c8a701715c0adff479fa29dbe9c9b28287031dfd
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63428300"
---
# <a name="step-9-try-other-features"></a>Étape 9 : Tester d’autres fonctionnalités
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour découvrir d'autres fonctionnalités, essayez de modifier les icônes et les couleurs, d'ajouter une horloge de jeu et d'ajouter des sons. Pour augmenter la difficulté du jeu, essayez d'agrandir la taille du plateau et d'ajuster la minuterie.  
  
 Pour télécharger une version complète de l’exemple, consultez [Exemple complet de didacticiel de création d’un jeu de combinaisons](http://code.msdn.microsoft.com/Complete-Matching-Game-4cffddba).  
  
### <a name="to-try-other-features"></a>Pour essayer d’autres fonctionnalités  
  
- Remplacez les icônes et les couleurs par d'autres de votre choix.  
  
    > [!TIP]
    > Examinez la propriété [Forecolor](http://msdn.microsoft.com/library/system.windows.forms.control.forecolor%28v=vs.110%29.aspx) du contrôle Label.  
  
- Ajoutez une horloge de jeu qui relèvera le temps requis par le joueur pour gagner.  
  
    > [!TIP]
    > Pour cela, vous pouvez ajouter un contrôle Label pour afficher sur le formulaire le temps écoulé au-dessus du TableLayoutPanel et ajouter une autre horloge au formulaire pour relever le temps. Utilisez le code pour démarrer l'horloge lorsque le joueur commence à jouer et arrêter l'horloge lorsque la dernière paire est indiquée.  
  
- Ajoutez un son lorsque le joueur trouve une paire identique, un autre lorsqu'il sélectionne deux icônes différentes et un troisième lorsque le programme masque à nouveau les icônes.  
  
    > [!TIP]
    > Pour émettre des sons, vous pouvez utiliser l'espace de noms System.media. Pour plus d’informations, consultez [Lire des sons dans une application Windows Forms (C# .NET)](http://youtu.be/qOh4ooHg1UU) ou [Comment lire de l’audio dans Visual Basic](http://youtu.be/-4oPDeQrtMs).  
  
- Augmentez la difficulté du jeu en agrandissant la taille du plateau.  
  
    > [!TIP]
    > Vous ne devez pas seulement ajouter des lignes et des colonnes au TableLayoutPanel – vous devez également considérer le nombre d'icônes que vous créez.  
  
- Augmentez la difficulté du jeu en masquant la première icône si le joueur réagit trop lentement et ne choisit pas la deuxième icône dans un délai imparti.  
  
### <a name="to-continue-or-review"></a>Pour continuer ou examiner  
  
- Si vous êtes bloqué ou avez des questions liées à la programmation, essayez de publier votre question sur l'un des forums MSDN. Consultez le [Forum Visual Basic](http://social.msdn.microsoft.com/Forums/home?forum=vbgeneral) et [Forum Visual C#](http://social.msdn.microsoft.com/Forums/home?forum=csharpgeneral).  
  
- Des ressources vidéo d'apprentissage efficaces et gratuites sont à votre disposition. Pour en savoir plus sur la programmation en Visual Basic, consultez [notions de base Visual Basic : Développement pour grands débutants](http://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners). Pour en savoir plus sur la programmation dans Visual C#, consultez [ C# notions de base : Développement pour grands débutants](http://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners).  
  
- Pour revenir à l’étape précédente du tutoriel, consultez [Étape 8 : Ajoutez une méthode pour vérifier si le joueur a gagné](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md).
