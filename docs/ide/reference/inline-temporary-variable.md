---
title: Remplacer une variable temporaire par sa valeur dans Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: fb6fc6888e33b2cc0d210e9cb1e1aababe304f2a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49916762"
---
# <a name="inline-a-temporary-variable-refactoring"></a>Inclure une variable temporaire (refactorisation)

Cette refactorisation s’applique à :

- C#

- Visual Basic

**Quoi :** vous permet de supprimer une variable temporaire et de la remplacer par sa valeur.

**Quand :** l’utilisation de la variable temporaire complique la lecture du code.

**Pourquoi :** la suppression d’une variable temporaire peut faciliter la lecture du code.

## <a name="how-to"></a>Procédure

1. Mettez en surbrillance ou placez le curseur dans la variable temporaire à inclure :

   - C# :

       ![Code mis en surbrillance (C#)](media/inline-highlight-cs.png)

   - Visual Basic :

       ![Code mis en surbrillance (Visual Basic)](media/inline-highlight-vb.png)

2. Effectuez ensuite l'une des opérations suivantes :

   - **Clavier**
      - Appuyez sur **Ctrl**+**.** pour afficher le menu **Actions rapides et refactorisations**.
   - **Souris**
      - Cliquez avec le bouton droit sur le code et sélectionnez le menu **Actions rapides et refactorisations**.

3. Sélectionnez **Inclure une variable temporaire** dans la fenêtre contextuelle d’aperçu.

   La variable est supprimée et ses utilisations sont remplacées par la valeur de la variable.

   - C# :

      ![Résultat de l’action Inclure (C#)](media/inline-result-cs.png)

   - Visual Basic :

      ![Résultat de l’action Inclure (Visual Basic)](media/inline-result-vb.png)

## <a name="see-also"></a>Voir aussi

- [Refactorisation](../refactoring-in-visual-studio.md)