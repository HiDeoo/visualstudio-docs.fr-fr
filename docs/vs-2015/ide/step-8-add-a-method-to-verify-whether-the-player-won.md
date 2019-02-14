---
title: 'Étape 8 : Ajoutez une méthode pour vérifier si le joueur a gagné | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 6e317f6e-ba4c-4306-8924-300b0c2f65c6
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 18f234f5b283c20db730b241d6dd73c3524f430e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54792778"
---
# <a name="step-8-add-a-method-to-verify-whether-the-player-won"></a>Étape 8 : ajouter une méthode pour vérifier si le joueur a gagné
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous avez créé un jeu divertissant, mais il a besoin d'un élément supplémentaire pour être complet. Le jeu doit se terminer en cas de victoire du joueur : vous devez donc ajouter une méthode `CheckForWinner()` pour vérifier si le joueur a gagné.  
  
### <a name="to-add-a-method-to-verify-whether-the-player-won"></a>Pour ajouter une méthode afin de vérifier si le joueur a gagné  
  
1.  Ajoutez une méthode `CheckForWinner()` en bas de votre code, sous le gestionnaire d'événements `timer1_Tick()`, comme illustré dans le code suivant.  
  
     [!code-csharp[VbExpressTutorial4Step8#10](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step8/cs/form1.cs#10)]
     [!code-vb[VbExpressTutorial4Step8#10](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step8/vb/form1.vb#10)]  
  
     La méthode utilise une autre boucle `foreach` en Visual C# ou `For Each` en Visual Basic pour parcourir chaque contrôle Label dans le TableLayoutPanel. Elle utilise l'opérateur d'égalité (`==` en Visual C# et `=` en Visual Basic) pour analyser la couleur de l'icône de chaque contrôle Label et vérifier si elle correspond à celle de l'arrière-plan. Si les couleurs correspondent, l'icône reste invisible et le joueur n'a pas associé toutes les icônes restantes. Dans ce cas, le programme utilise une instruction `return` pour ignorer le reste de la méthode. Si la boucle parcourt tous les contrôles Label sans exécuter l'instruction `return`, cela signifie que toutes les icônes du formulaire ont été associées. Le programme affiche un MessageBox pour féliciter le joueur d'avoir gagné, puis appelle la méthode `Close()` du formulaire pour arrêter le jeu.  
  
2.  Ensuite, appelez la nouvelle méthode `CheckForWinner()` via le gestionnaire d'événements Click du contrôle Label. Veillez à ce que votre programme vérifie si le joueur a gagné après avoir affiché la seconde icône choisie par le joueur. Recherchez la ligne où vous définissez la couleur de la seconde icône choisie, puis appelez la méthode `CheckForWinner()` juste après, comme cela est illustré dans le code suivant.  
  
     [!code-csharp[VbExpressTutorial4Step8#11](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step8/cs/form1.cs#11)]
     [!code-vb[VbExpressTutorial4Step8#11](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step8/vb/form1.vb#11)]  
  
3.  Enregistrez et exécutez le programme. Jouez au jeu et associez toutes les icônes. Lorsque vous gagnez, le programme affiche un MessageBox de félicitations (comme illustré à la figure suivante), puis ferme la boîte de message.  
  
     ![Jeu de combinaisons avec MessageBox](../ide/media/express-tut4step8.png "Express_Tut4Step8")  
Jeu de combinaisons avec MessageBox  
  
### <a name="to-continue-or-review"></a>Pour continuer ou examiner  
  
-   Pour passer à l’étape suivante du didacticiel, consultez [Étape 9 : tester d’autres fonctionnalités](../ide/step-9-try-other-features.md).  
  
-   Pour revenir à l’étape précédente du didacticiel, consultez [Étape 7 : garder les paires visibles](../ide/step-7-keep-pairs-visible.md).
