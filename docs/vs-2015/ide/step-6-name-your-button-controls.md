---
title: 'Étape 6 : affecter un nom à vos contrôles bouton | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 56b3baa3-651e-4ad4-8942-e334c5c57158
caps.latest.revision: 31
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 4d4d703dbe28776cd93c7a438fc457d9f50ac4f7
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75851126"
---
# <a name="step-6-name-your-button-controls"></a>Étape 6 : affecter un nom à vos contrôles bouton
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Votre formulaire ne contient qu’un seul PictureBox. Lorsque vous l’avez ajouté, l’IDE l’a nommé automatiquement **pictureBox1**. Il n’existe qu’un seul CheckBox, appelé **checkBox1**. Vous écrirez bientôt du code qui fera référence à CheckBox et PictureBox. Étant donné qu’il n’existe qu’un seul de ces deux contrôles, vous comprendrez ce que signifie **pictureBox1** ou **checkBox1** dans votre code.

> [!NOTE]
> En Visual Basic, le nom des contrôles commence par défaut par une lettre majuscule, autrement dit **PictureBox1**, **CheckBox1**et ainsi de suite.

 Il existe quatre boutons dans votre formulaire, et l’IDE les a nommés **button1**, **button2**, **button3**et **button4**. Leurs noms actuels ne vous permettent pas de savoir s’il s’agit du bouton **Fermer** ou du bouton **Afficher une image** . C’est pourquoi il est utile de donner à vos contrôles bouton des noms plus informatifs.

 ![lien vers la vidéo](../data-tools/media/playvideo.gif "PlayVideo") Pour obtenir une version vidéo de cette rubrique, consultez [didacticiel 1 : créer une visionneuse d’images dans Visual Basic-vidéo 3](https://msdn.microsoft.com/vbasic/gg315354.aspx) ou [didacticiel 1 : créer une visionneuse d’images en C#-vidéo 3](https://msdn.microsoft.com/vcsharp/gg278411.aspx). Ces vidéos utilisent une version antérieure de Visual Studio et présentent donc de légères différences quant à certaines commandes de menu et autres éléments d’interface utilisateur. Toutefois, les concepts et les procédures fonctionnent de façon similaire dans la version actuelle de Visual Studio.

### <a name="to-name-your-button-controls"></a>Pour nommer vos contrôles bouton

1. Dans le formulaire, choisissez le bouton **Fermer** . (Si tous les boutons sont encore sélectionnés, appuyez sur la touche ÉCHAP pour annuler la sélection.) Faites défiler la fenêtre **Propriétés** jusqu’à ce que la propriété **(Name)** s’affiche. (La propriété **(Name)** se trouve vers le haut lorsque les propriétés sont classées par ordre alphabétique.) Remplacez le nom par **CloseButton**, comme indiqué dans l’image suivante.

     ![Fenêtre Propriétés avec le nom closeButton](../ide/media/express-setnameproperty.png "Express_SetNameProperty") Fenêtre Propriétés avec le nom closeButton

    > [!NOTE]
    > Si vous essayez de modifier le nom de votre bouton en **closeButton** (autrement dit avec un espace entre les mots close et Button), l'IDE affiche un message d'erreur : « Valeur de propriété non valide ». Les espaces (et quelques autres caractères) ne sont pas autorisés dans les noms de contrôle.

2. Renommez les trois autres boutons en **backgroundButton**, **clearButton**et **showButton**. Vous pouvez vérifier les noms en sélectionnant la liste déroulante du sélecteur de contrôles dans la fenêtre **Propriétés** . Les nouveaux noms de boutons apparaissent.

3. Double-cliquez sur le bouton **Afficher une image** du formulaire. Vous pouvez également sélectionner le bouton **Afficher une image** sur le formulaire, puis appuyer sur la touche Entrée. Dans ce cas, l’IDE ouvre un onglet supplémentaire appelé **Form1.cs** (**Form1.vb** si vous utilisez Visual Basic) dans la fenêtre principale. Cet onglet affiche le fichier de code utilisé pour le formulaire, comme illustré dans l’image suivante.

     ![Onglet Form1.cs avec code Visual C&#35;](../ide/media/express-showbuttoncode.png "Express_ShowButtonCode") Onglet Form1.cs avec code Visual C#

4. Examinez attentivement cette partie du code. (Sélectionnez l’onglet **VB** ci-dessous si vous utilisez Visual Basic pour consulter la version Visual Basic du code.)

     [!code-csharp[VbExpressTutorial1Step6#1](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial1step6/cs/form1.cs#1)]
     [!code-vb[VbExpressTutorial1Step6#1](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial1step6/vb/form1.vb#1)]

     Vous regardez le code intitulé `showButton_Click()`. L’IDE l’a ajouté au code du formulaire lorsque vous avez ouvert le fichier de code du bouton **showButton** . Au moment de la conception, lorsque vous ouvrez le fichier de code d’un contrôle dans un formulaire, le code est généré pour le contrôle s’il n’existe pas déjà. Ce code (connu sous le nom de *méthode*) s’exécute lorsque vous exécutez votre programme et sélectionnez le contrôle (dans ce cas, le bouton **Afficher une image** ).

    > [!NOTE]
    > Dans ce didacticiel, tout ce qui se trouve entre les parenthèses () a été supprimé pour simplifier le code Visual Basic qui est généré automatiquement. Chaque fois que cette situation se produit, vous pouvez supprimer le même code. Votre programme fonctionnera quand même. Dans les autres didacticiels, le code généré automatiquement est simplifié autant que possible.

5. Sélectionnez à nouveau l’onglet Concepteur Windows Forms (**Form1.cs [Design]** en Visual C#, **Form1.vb [Design]** en Visual Basic), puis ouvrez le fichier de code du bouton **Effacer l’image** pour créer une méthode correspondante dans le code du formulaire. Répétez la même opération pour les deux boutons restants. Chaque fois, l’IDE ajoute une nouvelle méthode au fichier de code du formulaire.

6. Pour ajouter une méthode supplémentaire, ouvrez le fichier de code du contrôle CheckBox dans le Concepteur Windows Forms pour que l’IDE ajoute une méthode `checkBox1_CheckedChanged()` . Cette méthode est appelée chaque fois que l’utilisateur active ou désactive la case à cocher.

    > [!NOTE]
    > Lorsque vous travaillez sur un programme, vous basculez régulièrement entre l’éditeur de code et le Concepteur Windows Forms. L’IDE vous permet de naviguer facilement dans votre projet. Utilisez l’ **Explorateur de solutions** pour ouvrir le Concepteur Windows Forms en double-cliquant sur **Form1.cs** en Visual C# ou sur **Form1.vb** en Visual Basic, ou encore dans la barre de menus, choisissez **Affichage**, **Concepteur**.

     Les éléments suivants montrent le nouveau code qui est affiché dans l’éditeur de code.

     [!code-csharp[VbExpressTutorial1Step6#2](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial1step6/cs/form1.cs#2)]
     [!code-vb[VbExpressTutorial1Step6#2](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial1step6/vb/form1.vb#2)]

     Les cinq méthodes que vous avez ajoutées sont appelées *gestionnaires d’événements*, car votre programme les appelle chaque fois qu’un événement se produit (par exemple, lorsqu’un utilisateur sélectionne un bouton ou active une case à cocher).

     Lorsque vous affichez le code d’un contrôle dans l’IDE au moment de la conception, Visual Studio ajoute une méthode de gestionnaire d’événements pour le contrôle s’il n’en possède pas déjà une. Par exemple, lorsque vous double-cliquez sur un bouton, l’IDE ajoute un gestionnaire d’événements pour son événement Click (qui est appelé chaque fois que l’utilisateur choisit le bouton). Lorsque vous double-cliquez sur une case à cocher, l’IDE ajoute un gestionnaire d’événements pour son événement CheckedChanged (qui est appelé chaque fois que l’utilisateur active ou désactive la case).

     Une fois que vous avez ajouté un gestionnaire d’événements pour un contrôle, vous pouvez y revenir à tout moment en double-cliquant sur le contrôle via le Concepteur Windows Forms ou, dans la barre de menus, en choisissant **Afficher**, **Code**.

     Les noms sont importants lorsque vous générez des programmes, et vous pouvez nommer les méthodes (y compris les gestionnaires d’événements) comme vous le voulez. Lorsque vous ajoutez un gestionnaire d’événements avec l’IDE, il choisit un nom en fonction du nom du contrôle et de l’événement qui est géré. Par exemple, l’événement Click pour un bouton nommé **showButton** est appelé méthode du gestionnaire d’événements `showButton_Click()` . De même, des parenthèses ouvrantes et fermantes () sont généralement ajoutées après le nom de la méthode pour indiquer clairement qu’il s’agit de méthodes. Si vous décidez de modifier un nom de variable de code, cliquez avec le bouton droit sur la variable dans le code, puis choisissez **Refactoriser**, **Renommer**. Toutes les instances de cette variable dans le code sont renommées. Pour plus d’informations, consultez [refactorisation de changement de nom (C#)](../csharp-ide/rename-refactoring-csharp.md) ou [refactorisation et boîte de dialogue Renommer](https://msdn.microsoft.com/library/001d2d81-9bb6-4e8e-ae3a-20c0daaa3959) .

### <a name="to-continue-or-review"></a>Pour continuer ou examiner

- Pour passer à l’étape suivante du didacticiel, consultez [Étape 7 : ajouter des composants Dialog à votre formulaire](../ide/step-7-add-dialog-components-to-your-form.md).

- Pour revenir à l’étape précédente du didacticiel, consultez [Étape 5 : ajouter des contrôles à votre formulaire](../ide/step-5-add-controls-to-your-form.md).
