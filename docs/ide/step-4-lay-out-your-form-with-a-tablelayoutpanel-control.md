---
title: 'Étape 4 : Composer votre formulaire avec un contrôle TableLayoutPanel'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 61acde79-e115-4bad-bb06-1fbe37717a3e
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5f60d39cb14bfb471e677a8c231091e97d3016a6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53821338"
---
# <a name="step-4-lay-out-your-form-with-a-tablelayoutpanel-control"></a>Étape 4 : Composer votre formulaire avec un contrôle TableLayoutPanel
Dans cette étape, vous allez ajouter un contrôle <xref:System.Windows.Forms.TableLayoutPanel> à votre formulaire. Le contrôle TableLayoutPanel permet d'aligner correctement les contrôles du formulaire que vous ajouterez ultérieurement.

 ![lien vers la vidéo](../data-tools/media/playvideo.gif)Pour obtenir une version vidéo de cette rubrique, consultez [Tutoriel 1 : Créer une visionneuse d’images en Visual Basic – vidéo 2](http://go.microsoft.com/fwlink/?LinkId=205211) ou [Tutoriel 1 : Créer une visionneuse d’images en C# - Vidéo 2](http://go.microsoft.com/fwlink/?LinkId=205200). Ces vidéos utilisent une version antérieure de Visual Studio et présentent donc de légères différences quant à certaines commandes de menu et autres éléments d’interface utilisateur. Toutefois, les concepts et les procédures fonctionnent de façon similaire dans la version actuelle de Visual Studio.

## <a name="to-lay-out-your-form-with-a-tablelayoutpanel-control"></a>Pour composer votre formulaire avec un contrôle TableLayoutPanel

1.  Sur le côté gauche de l’IDE Visual Studio, localisez l’onglet **Boîte à outils**. Choisissez l’onglet **Boîte à outils** et la **boîte à outils** s’affiche. (Vous pouvez également sélectionner **Affichage** > **Boîte à outils** dans la barre de menus.)

2.  Sélectionnez le petit symbole de triangle en regard du groupe **Conteneurs** pour l’ouvrir, comme indiqué dans l’image suivante.

     ![Groupe de conteneurs](../ide/media/express_toolbox.png)
Groupe de **conteneurs**

3.  Vous pouvez ajouter des contrôles comme des boutons, des cases à cocher et des étiquettes à votre formulaire. Double-cliquez sur le contrôle TableLayoutPanel dans la **Boîte à outils**. Vous pouvez également faire glisser le contrôle de la Boîte à outils vers le formulaire. L'IDE ajoute alors un contrôle TableLayoutPanel à votre formulaire, comme indiqué dans l'image suivante.

     ![Contrôle TableLayoutPanel](../ide/media/express_formtablelayout.png)
Contrôle **TableLayoutPanel**

    > [!NOTE]
    >  Après avoir ajouté votre contrôle TableLayoutPanel, si une fenêtre intitulée **Tâches TableLayoutPanel** s’affiche à l’intérieur de votre formulaire, cliquez n’importe où dans le formulaire pour la fermer. Vous en apprendrez davantage sur cette fenêtre dans les prochaines étapes de ce didacticiel.

     Notez que la **Boîte à outils** se développe pour recouvrir votre formulaire lorsque vous sélectionnez son onglet, et se referme lorsque vous effectuez une sélection en dehors de celle-ci. Il s'agit de la fonctionnalité Masquer automatiquement de l'IDE. Vous pouvez l'activer ou la désactiver pour chaque fenêtre en cliquant sur l'icône de la punaise dans l'angle supérieur droit de la fenêtre (et ainsi choisir de masquer la fenêtre automatiquement ou de la garder à l'écran). L'icône de la punaise apparaît comme suit.

     ![Icône Punaise](../ide/media/express_pushpintoolbox.png)
Icône **Punaise**

4.  Veillez à ce que TableLayoutPanel soit sélectionné lorsque vous le choisissez. Vous pouvez vérifier quel contrôle est sélectionné en examinant la liste déroulante en haut de la fenêtre **Propriétés**, comme indiqué dans l’image suivante.

     ![Fenêtre Propriétés affichant le contrôle TableLayoutPanel](../ide/media/express_controlspropwin.png)
Fenêtre **Propriétés** affichant le contrôle **TableLayoutPanel**

5.  Dans la barre d’outils de la fenêtre **Propriétés**, choisissez le bouton **Ordre alphabétique**. La liste des propriétés de la fenêtre **Propriétés** s’affiche alors dans l’ordre alphabétique, ce qui facilite la localisation des propriétés dans ce didacticiel.

6.  Le sélecteur de contrôles est une liste déroulante située en haut de la fenêtre **Propriétés**. Dans cet exemple, il indique qu’un contrôle appelé `tableLayoutPanel1` est sélectionné. Vous pouvez sélectionner des contrôles en choisissant une zone dans le **Concepteur Windows Forms** ou en utilisant le sélecteur de contrôles. À présent que TableLayoutPanel est sélectionné, recherchez la propriété **Dock** et sélectionnez-la **.** Sa valeur doit être **Aucun**. Notez qu’une flèche de déroulement s’affiche en regard de la valeur. Cliquez sur la flèche, puis sélectionnez le bouton **Remplissage** (le grand bouton au milieu), comme indiqué dans l’image suivante.

     ![Fenêtre Propriétés avec Remplissage sélectionné](../ide/media/express_docktable.png)
Fenêtre **Propriétés** avec **Remplissage** sélectionné

     Dans Visual Studio, le terme *ancrage* signifie qu’une fenêtre est attachée à une autre fenêtre ou zone dans l’IDE. Par exemple, la fenêtre **Propriétés** peut être désancrée, c’est-à-dire détachée et flottante dans Visual Studio, ou elle peut être ancrée dans l’**Explorateur de solutions**.

7.  Une fois que vous avez affecté la valeur **Fill** à la propriété **Dock** du TableLayoutPanel, le panneau remplit tout le formulaire. Si vous redimensionnez à nouveau le formulaire, le TableLayoutPanel reste ancré et se redimensionne automatiquement pour s'adapter aux nouvelles dimensions.

    > [!NOTE]
    >  Un TableLayoutPanel fonctionne comme une table dans Microsoft Office Word : il comporte des lignes et des colonnes, et une cellule peut s’étendre sur plusieurs lignes et colonnes. Chaque cellule ne peut contenir qu'un seul contrôle (comme un bouton, une case à cocher ou une étiquette). Votre TableLayoutPanel aura un contrôle <xref:System.Windows.Forms.PictureBox> sur toute sa ligne du haut, un contrôle <xref:System.Windows.Forms.CheckBox> dans sa cellule en bas à gauche, et quatre contrôles <xref:System.Windows.Forms.Button> dans sa cellule en bas à droite.

8.  Actuellement, le TableLayoutPanel est composé de deux lignes et colonnes de taille égale. Vous devez les redimensionner pour que la ligne du haut et la colonne de droite soient beaucoup plus grandes. Dans le **Concepteur Windows Forms**, sélectionnez le TableLayoutPanel. Dans l'angle supérieur droit, il y a un petit bouton en forme de triangle noir, comme celui illustré ci-dessous.

     ![Bouton Triangle](../ide/media/express_iconblacktriangle.gif)
Bouton **Triangle**

     Ce bouton indique que le contrôle dispose de tâches vous permettant de définir ses propriétés automatiquement.

9. Sélectionnez le triangle pour afficher la liste des tâches du contrôle, comme indiqué dans l’image suivante.

     ![Tâches TableLayoutPanel](../ide/media/express_tablepanel.png)
Tâches **TableLayoutPanel**

10. Sélectionnez la tâche **Modifier les lignes et les colonnes** pour afficher la fenêtre **Styles de ligne et de colonne**. Sélectionnez **Column1** et affectez-lui la valeur 15 pour cent en vérifiant que le bouton **Pourcentage** est sélectionné et en entrant **15** dans la zone **Pourcentage**. (Il s’agit d’un contrôle <xref:System.Windows.Forms.NumericUpDown>, que vous utiliserez dans un prochain didacticiel.) Sélectionnez **Colonne2** et affectez-lui la valeur 85 pour cent. Ne sélectionnez pas encore le bouton **OK**, sinon la fenêtre se fermera. (Mais si vous le faites, vous pouvez la rouvrir à l’aide de la liste des tâches.)

     ![Styles des lignes et des colonnes TableLayoutPanel](../ide/media/vs_tablelayoutpanel_setup.png)
Styles des lignes et des colonnes **TableLayoutPanel**

11. Dans la liste déroulante **Afficher** en haut de la fenêtre, sélectionnez **Lignes**. Affectez les valeurs 90 pour cent à **Ligne1** et 10 pour cent à **Ligne2**.

12. Sélectionnez le bouton **OK** . Votre TableLayoutPanel doit maintenant avoir une grande ligne en haut, une petite ligne en bas, une petite colonne à gauche et une grande colonne à droite. Vous pouvez redimensionner les lignes et les colonnes de TableLayoutPanel en choisissant **tableLayoutPanel1** dans le formulaire, puis en faisant glisser ses bordures de ligne et de colonne.

     ![Form1 avec TableLayoutPanel redimensionné](../ide/media/vs_formafterlayoutpanel.png)
**Form1** avec **TableLayoutPanel** redimensionné

## <a name="to-continue-or-review"></a>Pour continuer ou examiner

-   Pour passer à l’étape suivante du tutoriel, consultez [Étape 5 : Ajouter des contrôles à votre formulaire](../ide/step-5-add-controls-to-your-form.md).

-   Pour revenir à l’étape précédente du tutoriel, consultez [Étape 3 : définir les propriétés de votre formulaire](../ide/step-3-set-your-form-properties.md).
