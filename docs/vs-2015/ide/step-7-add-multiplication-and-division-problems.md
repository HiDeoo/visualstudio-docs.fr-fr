---
title: 'Étape 7 : ajouter des problèmes de multiplication et de division | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: e638959e-f6a4-4eb4-b2e9-f63b7855cf8f
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: f7f7efb0acf6611346abe67a7a94e5c221919665
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72646978"
---
# <a name="step-7-add-multiplication-and-division-problems"></a>Étape 7 : ajouter des problèmes de multiplication et de division
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans la septième partie de ce didacticiel, vous allez ajouter des problèmes de multiplication et de division, mais vous commencerez par réfléchir à la manière d'effectuer cette modification. Pensez à la première étape, dans laquelle vous devez stocker des valeurs.

### <a name="to-add-multiplication-and-division-problems"></a>Pour ajouter des problèmes de multiplication et de division

1. Ajoutez quatre variables de type entier supplémentaires au formulaire.

     [!code-csharp[VbExpressTutorial3Step7#15](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#15)]
     [!code-vb[VbExpressTutorial3Step7#15](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#15)]

2. Comme vous l'avez fait auparavant, modifiez la méthode `StartTheQuiz()` pour renseigner les problèmes de multiplication et de division avec des nombres aléatoires.

     [!code-csharp[VbExpressTutorial3Step7#16](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#16)]
     [!code-vb[VbExpressTutorial3Step7#16](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#16)]

3. Modifiez la méthode `CheckTheAnswer()` afin qu'elle vérifie également les problèmes de multiplication et de division.

     [!code-csharp[VbExpressTutorial3Step7#17](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#17)]
     [!code-vb[VbExpressTutorial3Step7#17](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#17)]

     Vous ne pouvez pas entrer aisément les signes de multiplication (×) et de division (÷) à l'aide du clavier, si bien que Visual C# et Visual Basic acceptent un astérisque (*) pour la multiplication et une barre oblique (/) pour la division.

4. Modifiez la dernière partie du gestionnaire d'événements Tick du minuteur afin que la réponse correcte s'affiche une fois le délai écoulé.

     [!code-csharp[VbExpressTutorial3Step7#23](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#23)]
     [!code-vb[VbExpressTutorial3Step7#23](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#23)]

5. Enregistrez et exécutez votre programme.

     Les personnes interrogées doivent résoudre quatre problèmes pour terminer le questionnaire, comme le montre l'illustration ci-dessous.

     ![Questionnaire mathématique avec quatre problèmes](../ide/media/express-finishedquiz.png "Express_FinishedQuiz") Questionnaire mathématique avec quatre problèmes

### <a name="to-continue-or-review"></a>Pour continuer ou examiner

- Pour passer à l’étape suivante du didacticiel, consultez [étape 8 : personnaliser le quiz](../ide/step-8-customize-the-quiz.md).

- Pour revenir à l’étape précédente du didacticiel, consultez [étape 6 : ajouter un problème de soustraction](../ide/step-6-add-a-subtraction-problem.md).
