---
title: 'Étape 2 : Exécuter votre programme | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 9a8fe90e-c97b-4e98-b6c8-0c6b3962c49d
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 2ddec4c7327aa9799ae8a12a04b3940d690205cb
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75851571"
---
# <a name="step-2-run-your-program"></a>Étape 2 : exécuter votre programme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Lorsque vous avez créé une solution, vous avez en fait généré un programme qui fonctionne. Pour le moment, le programme offre peu de fonctionnalités : il affiche simplement une fenêtre vide avec la barre de titre **Form1**. Mais il fonctionne réellement, comme vous allez le découvrir.

 ![lien vers la vidéo](../data-tools/media/playvideo.gif "PlayVideo") Pour obtenir une version vidéo de cette rubrique, consultez [didacticiel 1 : créer une visionneuse d’images dans Visual Basic vidéo 1](https://msdn.microsoft.com/vbasic/gg315352.aspx) ou [didacticiel 1 : créer une visionneuse d’images en C#-vidéo 1](https://msdn.microsoft.com/vcsharp/gg278409.aspx). Ces vidéos utilisent une version antérieure de Visual Studio et présentent donc de légères différences quant à certaines commandes de menu et autres éléments d’interface utilisateur. Toutefois, les concepts et les procédures fonctionnent de façon similaire dans la version actuelle de Visual Studio.

### <a name="to-run-your-program"></a>Pour exécuter votre programme

1. Utilisez l'une des méthodes suivantes pour exécuter votre programme.

    - Choisissez la touche **F5**.

    - Dans la barre de menus, choisissez **Débogage**, puis **Démarrer le débogage**.

    - Dans la barre d’outils, choisissez le bouton **Démarrer le débogage**, qui se présente comme suit.

         ![Bouton Démarrer le débogage de la barre d’outils](../ide/media/express-icondebug.png "Express_IconDebug") Bouton Démarrer le débogage de la barre d’outils

2. Visual Studio exécute votre programme. Une fenêtre intitulée **Form1** s’affiche. Le schéma suivant montre le programme que vous venez de générer. Le programme est exécuté, et vous allez bientôt y faire des ajouts.

     ![Programme d’application Windows Form en cours d’exécution](../ide/media/express-firstrun.png "Express_FirstRun") Programme d’application Windows Form en cours d’exécution

3. Revenez à l'environnement de développement intégré (IDE) de Visual Studio et examinez la nouvelle barre d'outils. Des boutons supplémentaires apparaissent dans la barre d'outils lorsque vous exécutez un programme. Ces boutons vous permettent d'effectuer des opérations comme arrêter et démarrer votre programme, et vous aident à localiser les erreurs (bogues) possibles. Dans cet exemple, nous les utilisons pour démarrer et arrêter le programme.

     ![Barre d’outils de débogage](../ide/media/express-debugtoolbar.png "Express_DebugToolbar") Barre d’outils de débogage

4. Utilisez l'une des méthodes suivantes pour arrêter votre programme.

    - Dans la barre d’outils, choisissez le bouton **Arrêter le débogage**.

    - Dans la barre de menus, choisissez **Débogage**, **Arrêter le débogage**.

    - Dans l’angle supérieur de la fenêtre **Form1**, choisissez le bouton X.

    > [!NOTE]
    > Quand vous exécutez votre programme à partir de l’IDE, on parle de *débogage* , car vous le faites généralement pour rechercher et corriger les bogues (erreurs) dans le programme. Bien que ce programme soit petit et ne fasse pas encore grand chose, il n'en reste pas moins un programme. Vous suivez la même procédure pour exécuter et déboguer d'autres programmes. Pour en savoir plus sur le débogage, consultez [concepts de base du débogueur](../debugger/debugger-basics.md).

### <a name="to-continue-or-review"></a>Pour continuer ou examiner

- Pour passer à l’étape suivante du didacticiel, consultez [étape 3 : définir les propriétés de votre formulaire](../ide/step-3-set-your-form-properties.md).

- Pour revenir à l’étape précédente du didacticiel, consultez [étape 1 : créer un projet d’Application Windows Forms](../ide/step-1-create-a-windows-forms-application-project.md).
