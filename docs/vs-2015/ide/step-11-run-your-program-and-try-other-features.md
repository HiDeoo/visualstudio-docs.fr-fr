---
title: 'Étape 11 : exécuter votre programme et tester d’autres fonctionnalités | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 656614d0-4fe7-4a67-8edc-c10919377d09
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bff0467cfe9447b1cc7814d471f56ab323bb853d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75851577"
---
# <a name="step-11-run-your-program-and-try-other-features"></a>Étape 11 : exécuter votre programme et tester d'autres fonctionnalités
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Votre programme est terminé et prêt à fonctionner. Vous pouvez l'exécuter et définir la couleur d'arrière-plan du contrôle PictureBox. Pour découvrir d'autres fonctionnalités, essayez d'améliorer le programme en modifiant la couleur du formulaire, en personnalisant les boutons et la case à cocher, et en modifiant les propriétés du formulaire.

 ![lien vers la vidéo](../data-tools/media/playvideo.gif "PlayVideo") Pour obtenir une version vidéo de cette rubrique, consultez [didacticiel 1 : créer une visionneuse d’images dans Visual Basic-vidéo 5](https://msdn.microsoft.com/vbasic/gg315356.aspx) ou [didacticiel 1 : créer une visionneuse d’images en C#-vidéo 5](https://msdn.microsoft.com/vcsharp/gg278413.aspx). Ces vidéos utilisent une version antérieure de Visual Studio et présentent donc de légères différences quant à certaines commandes de menu et autres éléments d’interface utilisateur. Toutefois, les concepts et les procédures fonctionnent de façon similaire dans la version actuelle de Visual Studio.

### <a name="to-run-your-program-and-set-the-background-color"></a>Pour exécuter votre programme et définir la couleur d'arrière-plan.

1. Appuyez sur F5 ou, dans la barre de menus, choisissez **Déboguer**, **Démarrer le débogage**.

2. Avant d’ouvrir une image, choisissez le bouton **Définir la couleur d’arrière-plan**. La boîte de dialogue **Couleur** s’ouvre.

     ![Boîte de dialogue couleur](../ide/media/express-colordialog.png "Express_ColorDialog") Boîte de dialogue couleur

3. Choisissez une couleur pour définir la couleur d'arrière-plan du contrôle PictureBox. Examinez attentivement la méthode `backgroundButton_Click()` pour comprendre son fonctionnement.

    > [!NOTE]
    > Vous pouvez charger une image à partir d’Internet en collant son URL dans la boîte de dialogue **Ouvrir un fichier**. Essayez de trouver une image avec un arrière-plan transparent, pour que votre couleur d'arrière-plan soit visible.

4. Choisissez le bouton **Effacer l’image** pour vous assurer qu’elle s’efface. Quittez ensuite le programme en choisissant le bouton **Fermer**.

### <a name="to-try-other-features"></a>Pour essayer d’autres fonctionnalités

- Modifiez la couleur du formulaire et des boutons à l’aide de la propriété **BackColor**.

- Personnalisez vos boutons et votre case à cocher à l’aide des propriétés **Font** et **ForeColor**.

- Modifiez les propriétés**FormBorderStyle** et **ControlBox** de votre formulaire.

- Utilisez les propriétés **AcceptButton** et **CancelButton** de votre formulaire pour que les boutons soient automatiquement choisis quand l’utilisateur choisit la touche entrée ou ÉCHAP. Faire en sorte que le programme ouvre la boîte de dialogue **ouvrir un fichier** lorsque l’utilisateur choisit entrer et fermer la boîte de dialogue lorsque l’utilisateur choisit ÉCHAP.

### <a name="to-continue-or-review"></a>Pour continuer ou examiner

- Pour en savoir plus sur la programmation dans Visual Studio, consultez [concepts de programmation](https://msdn.microsoft.com/library/65c12cca-af4f-4017-886e-2dbc00a189d6).

- Pour en savoir plus sur Visual Basic, consultez [Développement d’applications avec Visual Basic](https://msdn.microsoft.com/library/1e1c0c81-6d95-4167-a98b-44b1efb6d25f).

- Pour en savoir plus sur Visual C#, consultez [Introduction au langage c# et à la .NET Framework](https://msdn.microsoft.com/library/0a2dff4e-cd84-42ff-8141-e89889b24081).

- Pour passer au didacticiel suivant, consultez [didacticiel 2 : créer un questionnaire mathématique chronométré](../ide/tutorial-2-create-a-timed-math-quiz.md).

- Pour revenir à l’étape précédente du didacticiel, consultez [étape 10 : écrire du code pour des boutons supplémentaires et une case à cocher](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).
