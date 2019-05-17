---
title: 'Tutoriel 1 : Créer une visionneuse d’images | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 3071d6df-2b2f-4e95-ab68-bef727323136
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c382ff2a16e47f52a33e5c6728f0c57d57e4315b
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65703050"
---
# <a name="tutorial-1-create-a-picture-viewer"></a>Tutoriel 1 : Créer une visionneuse d’images
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans ce didacticiel, vous générez un programme qui charge une image à partir d'un fichier et l'affiche dans une fenêtre. Vous apprenez à faire glisser des contrôles (par exemple, des boutons et des zones d'image) sur votre formulaire, définir leurs propriétés et utiliser des conteneurs pour redimensionner facilement le formulaire. Vous commencez également à écrire du code. Vous apprenez à :  
  
- Créer un nouveau projet.  
  
- Tester (déboguer) une application.  
  
- Ajouter des contrôles de base, comme des cases à cocher et des boutons, à un formulaire.  
  
- Positionner des contrôles sur un formulaire à l'aide de dispositions.  
  
- Ajouter des boîtes de dialogue **Ouvrir un fichier** et **Couleur** à un formulaire.  
  
- Écrire du code à l'aide d'IntelliSense et d'extraits de code.  
  
- Écrire des méthodes de gestionnaire d'événements.  
  
  Lorsque vous aurez terminé, votre programme ressemblera à l'image suivante.  
  
  ![Image créée dans ce didacticiel](../ide/media/express-pictureviewerdone.png "Express_PictureViewerDone")  
  Image créée dans ce didacticiel  
  
  Pour télécharger une version complète de l’exemple, consultez la rubrique [Exemple complet de visionneuse d’images du didacticiel](http://code.msdn.microsoft.com/Complete-Picture-Viewer-7d91d3a8).  
  
  ![lien vers la vidéo](../data-tools/media/playvideo.gif "PlayVideo")pour obtenir une version vidéo de cette rubrique, consultez [procédure : Créer une visionneuse d’images en Visual Basic ? ](http://go.microsoft.com/fwlink/?LinkId=205207) ou [How Do I: Créer une visionneuse d’images dans C#? ](http://go.microsoft.com/fwlink/?LinkId=205198).  
  
> [!NOTE]
> Ces vidéos utilisent une version antérieure de Visual Studio et présentent donc de légères différences quant à certaines commandes de menu et autres éléments d’interface utilisateur. Toutefois, les concepts et les procédures fonctionnent de façon similaire dans la version actuelle de Visual Studio. Visual C# et Visual Basic sont tous deux traités dans ce didacticiel. Ne tenez compte que des informations spécifiques au langage de programmation que vous utilisez.  
>   
> Pour consulter le code pour Visual Basic, choisissez l’onglet **VB** en haut des blocs de code. Pour visualiser le code pour Visual C#, choisissez l’onglet **C#**. Si vous êtes intéressé par Visual C++, consultez [Bien démarrer](../misc/getting-started-with-visual-cpp-in-visual-studio-2015.md) et [Didacticiel du langage C++](http://www.cplusplus.com/doc/tutorial/).  
>   
> Si vous souhaitez savoir comment écrire des applications Visual C# ou Visual Basic pour le Windows Store, consultez [Créer votre première application du Windows Store en C# ou Visual Basic](https://msdn.microsoft.com/library/windows/apps/hh974581.aspx). Pour plus d’informations sur la création d’applications JavaScript pour le Windows Store, consultez [Créer votre première application du Windows Store en JavaScript](https://msdn.microsoft.com/library/windows/apps/br211385.aspx).  
  
## <a name="related-topics"></a>Rubriques connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Étape 1 : Créer un projet Application Windows Forms](../ide/step-1-create-a-windows-forms-application-project.md)|Commencez par créer un projet d’application Windows Forms.|  
|[Étape 2 : Exécuter votre programme](../ide/step-2-run-your-program.md)|Exécutez le programme d’application Windows Forms que vous avez créé dans l’étape précédente.|  
|[Étape 3 : Définir les propriétés de votre formulaire](../ide/step-3-set-your-form-properties.md)|Modifiez l’apparence de votre formulaire à l’aide de la fenêtre **Propriétés**.|  
|[Étape 4 : Composer votre formulaire avec un contrôle TableLayoutPanel](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md)|Ajoutez un contrôle `TableLayoutPanel` à votre formulaire.|  
|[Étape 5 : Ajouter des contrôles à votre formulaire](../ide/step-5-add-controls-to-your-form.md)|Ajoutez des contrôles à votre formulaire (notamment des contrôles `PictureBox` et `CheckBox`). Ajoutez des boutons à votre formulaire.|  
|[Étape 6 : Nommer vos contrôles Button](../ide/step-6-name-your-button-controls.md)|Renommez vos boutons en leur donnant des noms plus explicites.|  
|[Étape 7 : Ajouter des composants de boîte de dialogue à votre formulaire](../ide/step-7-add-dialog-components-to-your-form.md)|Ajoutez un composant **OpenFileDialog** et un composant **ColorDialog** à votre formulaire.|  
|[Étape 8 : Écrire du code pour le gestionnaire d’événements du bouton Afficher une image](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md)|Écrivez du code à l'aide de l'outil IntelliSense.|  
|[Étape 9 : Passer en revue, commenter et tester votre code](../ide/step-9-review-comment-and-test-your-code.md)|Vérifiez et testez votre code. Ajoutez autant de commentaires que nécessaire.|  
|[Étape 10 : Écrire du code pour des boutons supplémentaires et une case à cocher](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md)|Écrivez du code à l'aide d'IntelliSense pour faire fonctionner d'autres boutons et une case à cocher.|  
|[Étape 11 : Exécuter votre programme et tester d’autres fonctionnalités](../ide/step-11-run-your-program-and-try-other-features.md)|Exécutez votre programme et définissez la couleur d'arrière-plan. Essayez d'autres fonctionnalités, telles que la modification des couleurs, des polices et des bordures.|
