---
title: 'Étape 4 : ajouter un gestionnaire d’événements Click à chaque contrôle Label | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16bdbc7c-4129-411d-bace-f4a3e5375975
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 93ce8f97f32ac41c4724db3c4cc08389f052f1ef
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49923379"
---
# <a name="step-4-add-a-click-event-handler-to-each-label"></a>Étape 4 : ajouter un gestionnaire d'événements Click à chaque contrôle Label
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Le jeu de combinaisons fonctionne comme suit :  
  
1. Lorsqu'un joueur choisit l'une des cases avec une icône masquée, le programme révèle l'icône en lui conférant une couleur noire.  
  
2. Le joueur choisit ensuite une autre icône masquée.  
  
3. Si les deux icônes sélectionnées sont identiques, elles restent visibles. Dans le cas contraire, elles sont à nouveau masquées.  
  
   Pour que votre programme suive ces principes, vous devez ajouter un gestionnaire d'événements Click qui modifiera la couleur du contrôle Label choisi.  
  
### <a name="to-add-a-click-event-handler-to-each-label"></a>Pour ajouter un gestionnaire d'événements Click à chaque contrôle Label  
  
1.  Ouvrez le formulaire dans le Concepteur Windows Forms. Dans l'Explorateur de solutions, choisissez Form1.cs ou Form1.vb. Dans la barre de menus, choisissez **Affichage**, **Concepteur**.  
  
2.  Choisissez le premier contrôle Label pour le sélectionner. Ensuite, maintenez la touche Ctrl enfoncée tout en choisissant d'autres contrôles Label pour les sélectionner. Assurez-vous que chaque contrôle Label est sélectionné.  
  
3.  Choisissez le bouton **Événements** dans la barre d’outils de la fenêtre **Propriétés** pour afficher la page **Événements** dans la fenêtre **Propriétés**. Faites défiler l’écran vers le bas jusqu’à l’événement **Click**, puis entrez **label_Click** dans la zone, comme indiqué à la figure suivante.  
  
     ![Fenêtre Propriétés affichant l'événement Click](../ide/media/express-labelclick.png "Express_labelClick")  
Fenêtre Propriétés affichant l'événement Click  
  
4.  Appuyez sur Entrée. L'IDE ajoute un gestionnaire d'événements Click appelé `label_Click()` au code et le raccorde à chacun des contrôles Label sur le formulaire.  
  
5.  Remplissez le reste du code, comme suit :  
  
     [!code-csharp[VbExpressTutorial4Step2_3_4#4](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/cs/form1.cs#4)]
     [!code-vb[VbExpressTutorial4Step2_3_4#4](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step2_3_4/vb/form1.vb#4)]  
  
    > [!NOTE]
    >  Si vous effectuez un copier-coller du bloc de code `label_Click()` au lieu d'écrire le code manuellement, veillez à remplacer le code `label_Click()` existant. Sinon, vous obtiendrez au final un bloc de code en double.  
  
    > [!NOTE]
    >  Vous pouvez reconnaître `object sender` en haut du gestionnaire d’événements comme étant le même que celui utilisé dans le [Didacticiel 2 : créer un questionnaire mathématique chronométré](../ide/tutorial-2-create-a-timed-math-quiz.md). Comme vous avez raccordé plusieurs événements Click de contrôle Label à une seule méthode de gestionnaire d'événements, la même méthode est appelée quel que soit le contrôle Label choisi par l'utilisateur. La méthode de gestionnaire d’événements doit savoir quel contrôle Label a été choisi. Elle utilise donc le nom **sender** pour identifier le contrôle Label. La première ligne de la méthode indique au programme qu’il ne s’agit pas uniquement d’un objet générique, mais plus précisément d’un contrôle Label, et qu’il utilise le nom **clickedLabel** pour accéder aux propriétés et méthodes du contrôle Label.  
  
     Cette méthode vérifie d’abord si un objet **clickedLabel** a été correctement converti (cast) en contrôle Label. Dans le cas contraire, il a une valeur `null` (C#) ou `Nothing` (Visual Basic), et vous ne voudrez pas exécuter le reste du code dans la méthode. Ensuite, la méthode vérifie la couleur de texte du contrôle Label choisi en utilisant la propriété **ForeColor** de ce dernier. Si la couleur du texte du contrôle Label est noire, cela signifie que l'icône a déjà été choisie et la méthode est terminée. (C'est le rôle de l'instruction `return` : elle indique au programme d'arrêter l'exécution de la méthode.) Dans le cas contraire, l'icône n'a pas été choisie et le programme modifie la couleur du texte du contrôle Label pour la rendre noire.  
  
6.  Dans la barre de menus, choisissez **Fichier**, **Enregistrer tout** pour enregistrer votre progression, puis, dans la barre de menus, choisissez **Déboguer**, **Démarrer le débogage** pour exécuter votre programme. Un formulaire vierge doit s'afficher avec un arrière-plan bleu. Choisissez l'une des cellules du formulaire et l'une des icônes doit apparaître. Continuez à choisir des emplacements différents dans le formulaire. Chaque fois que vous choisissez une icône, elle doit s'afficher.  
  
### <a name="to-continue-or-review"></a>Pour continuer ou examiner  
  
-   Pour passer à l’étape suivante du didacticiel, consultez [Étape 5 : ajouter des références de contrôles Label](../ide/step-5-add-label-references.md).  
  
-   Pour revenir à l’étape précédente du didacticiel, consultez [Étape 3 : affecter une icône aléatoire à chaque contrôle Label](../ide/step-3-assign-a-random-icon-to-each-label.md).



