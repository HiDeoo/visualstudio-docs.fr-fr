---
title: 'Étape 1 : Créer un projet Application Windows Forms'
ms.date: 01/26/2019
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 16ac2422-e720-4e3a-b511-bc2a54201a86
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bbd6fb3733b95a92057b626f79db62698435b7c2
ms.sourcegitcommit: 447f2174bdecdd471d8a8e11c19554977db620a0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/28/2019
ms.locfileid: "55089251"
---
# <a name="step-1-create-a-windows-forms-application-project"></a>Étape 1 : Créer un projet Application Windows Forms

Lorsque vous créez une visionneuse d’images, la première étape consiste à créer un projet d’application Windows Forms.

 ![lien vers la vidéo](../data-tools/media/playvideo.gif)Pour obtenir une version vidéo de cette rubrique, consultez [Turoriel 1 : Créer une visionneuse d’images en Visual Basic – vidéo 1](http://go.microsoft.com/fwlink/?LinkId=205209) ou [Tutoriel 1 : Créer une visionneuse d'images en C# - Vidéo 1](http://go.microsoft.com/fwlink/?LinkId=205199). Ces vidéos utilisent une version antérieure de Visual Studio et présentent donc de légères différences quant à certaines commandes de menu et autres éléments d’interface utilisateur. Toutefois, les concepts et les procédures fonctionnent de façon similaire dans la version actuelle de Visual Studio.

## <a name="to-create-a-windows-forms-application-project"></a>Pour créer un projet Application Windows Forms

1. Dans la barre de menus, choisissez **Fichier** > **Nouveau** > **Projet**. La boîte de dialogue doit se présenter comme suit.

     ![Nouveau projet, boîte de dialogue](../ide/media/newprojectdialogcallouts.png)<br/>
*Boîte de dialogue **Nouveau projet***

2. Choisissez **Visual C#** ou **Visual Basic** dans la partie gauche de la boîte de dialogue **Nouveau projet**.

3. Dans la liste des modèles, choisissez **Application Windows Forms (.NET Framework)**. Nommez le nouveau formulaire **PictureViewer**, puis sélectionnez le bouton **OK**.

    >[!NOTE]
    >Si vous ne voyez pas le modèle **Application Windows Forms (.NET Framework)**, utilisez Visual Studio Installer pour installer la charge de travail **Développement .NET Desktop**.<br/><br/>![Charge de travail de développement .NET Desktop dans Visual Studio Installer](../ide/media/dot-net-desktop-dev-workload.png)<br/><br/> Pour plus d’informations, consultez la page [Installer Visual Studio 2017](../install/install-visual-studio.md).

     Visual Studio crée une solution pour votre programme. Une solution joue le rôle de conteneur pour tous les projets et fichiers requis par votre programme. Ces termes seront expliqués plus en détail dans les prochaines étapes de ce didacticiel.

4. L'illustration suivante montre ce que vous devez maintenant voir dans l'interface de Visual Studio.

    > [!NOTE]
    > Votre disposition de fenêtre peut ne pas se présenter exactement comme dans cette illustration. La disposition exacte de la fenêtre dépend de la version de Visual Studio, du langage de programmation que vous utilisez et d'autres facteurs. Toutefois, vous devez vérifier que les trois fenêtres apparaissent.

     ![Fenêtre IDE](../ide/media/express_ideoverview_visio.png)<br/>*Fenêtre de l’**IDE***

     L’interface contient trois fenêtres : une fenêtre principale, l’**Explorateur de solutions** et la fenêtre **Propriétés**.

     Si l’une de ces fenêtres est manquante, restaurez la disposition de fenêtre par défaut en sélectionnant dans la barre de menus **Fenêtre** > **Rétablir la disposition de fenêtre**. Vous pouvez également afficher les fenêtres à l'aide des commandes de menu. Dans la barre de menus, choisissez **Affichage** > **Fenêtre Propriétés** ou **Explorateur de solutions**. Si d’autres fenêtres sont ouvertes, fermez-les en choisissant le bouton **Fermer** (x) dans l’angle supérieur droit.

5. L'illustration montre les fenêtres suivantes (dans le sens des aiguilles d'une montre, à partir de l'angle supérieur gauche) :

    - **Fenêtre principale** Dans cette fenêtre, vous effectuez la majeure partie de votre travail, notamment l’utilisation des formulaires et la modification du code. Dans l'illustration, la fenêtre affiche un formulaire dans l'**éditeur de formulaires**. En haut de la fenêtre, les onglets **Page de démarrage** et **Form1.cs [Design]** s’affichent. (En Visual Basic, le nom d'un onglet se termine par *.vb* au lieu de *.cs*.)

    - **Fenêtre Explorateur de solutions** Dans cette fenêtre, vous pouvez afficher tous les éléments de votre solution et y accéder. Si vous sélectionnez un fichier, le contenu de la fenêtre **Propriétés** est modifié. Si vous ouvrez un fichier de code (qui se termine par *.cs* en Visual C# et par *.vb* en Visual Basic), le fichier de code ou un concepteur pour le fichier de code s'affiche. Un concepteur est une surface visuelle à laquelle vous pouvez ajouter des contrôles tels que des boutons et des listes. Pour les formulaires Visual Studio, le concepteur est appelé **Concepteur Windows Forms**.

    - **Fenêtre Propriétés** Elle vous permet de modifier les propriétés des éléments que vous choisissez dans les autres fenêtres. Par exemple, si vous sélectionnez Form1, vous pouvez modifier son titre en définissant la propriété **Text**, et vous pouvez modifier la couleur d’arrière-plan en définissant la propriété **Backcolor**.

    > [!NOTE]
    > La première ligne de l’**Explorateur de solutions** affiche **Solution « PictureViewer » (1 projet)**, ce qui signifie que Visual Studio a créé une solution pour vous. Une solution peut contenir plusieurs projets, mais, pour le moment, vous utiliserez des solutions contenant un seul projet.

6. Dans la barre de menus, sélectionnez **Fichier** > **Enregistrer tout**.

     Vous pouvez aussi sélectionner le bouton **Enregistrer tout**, présenté dans l’illustration suivante, dans la barre d’outils.

     ![Enregistrer tout, bouton de barre d’outils](../ide/media/express_iconsaveall.png)<br/>
*Bouton de barre d’outils **Enregistrer tout***

     Visual Studio renseigne automatiquement le nom du dossier et le nom du projet, puis crée le projet dans votre dossier de projets.

## <a name="to-continue-or-review"></a>Pour continuer ou examiner

- Pour passer à l’étape suivante du tutoriel, consultez [Étape 2 : Exécuter votre programme](../ide/step-2-run-your-program.md).

- Pour revenir à la rubrique de vue d’ensemble, consultez [Tutoriel 1 : Créer une visionneuse d’images](../ide/tutorial-1-create-a-picture-viewer.md).

## <a name="see-also"></a>Voir aussi

- [Création d’un Windows Form](/dotnet/framework/winforms/creating-a-new-windows-form/)