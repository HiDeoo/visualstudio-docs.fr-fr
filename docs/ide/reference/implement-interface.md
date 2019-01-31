---
title: Implémenter une interface
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 82334ebb6dbcee17954baf0ddd793eb02c37ff43
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54928800"
---
# <a name="implement-an-interface-in-visual-studio"></a>Implémenter une interface dans Visual Studio

Cette génération de code s’applique à :

- C#

- Visual Basic

**Quoi :** Vous permet de générer immédiatement le code requis pour implémenter une interface.

**Quand :** Vous voulez hériter d’une interface.

**Pourquoi :** Vous pouvez implémenter manuellement tous les éléments d’une interface un par un, mais cette fonctionnalité générera automatiquement toutes les signatures de la méthode.

## <a name="how-to"></a>Procédure

1. Placez votre curseur sur la ligne présentant un trait rouge ondulé. Celui-ci indique que vous avez référencé une interface, mais que vous n’avez pas implémenté tous les membres nécessaires.

   - C# :

       ![Code C# mis en surbrillance](media/interface-highlight-cs.png)

   - Visual Basic :

       ![Code VB mis en surbrillance](media/interface-highlight-vb.png)

2. Effectuez ensuite l'une des opérations suivantes :

   - **Clavier**
      - Appuyez sur **Ctrl**+**.** pour afficher le menu **Actions rapides et refactorisations**.
   - **Souris**
      - Cliquez avec le bouton droit et sélectionnez le menu **Actions rapides et refactorisations**.
      - Placez le curseur sur la ligne ondulée rouge, puis cliquez sur l’icône ![Ampoule](media/bulb-cs.png) qui apparaît.
      - Cliquez sur le bouton ![Ampoule](media/bulb-cs.png) qui apparaît dans la marge de gauche si le curseur de texte se trouve déjà sur la ligne ondulée rouge.

3. Sélectionnez **Implémenter l’interface** à partir du menu déroulant.

   ![Implémenter l’interface (préversion)](media/interface-preview-cs.png)

   > [!TIP]
   > - Utilisez le lien **Aperçu des modifications** en bas de la fenêtre d’aperçu [pour voir tous les changements](../../ide/preview-changes.md) qui seront apportés avant d’effectuer votre sélection.
   > - Utilisez les liens **Document**, **Projet** et **Solution** en bas de la fenêtre d’aperçu pour créer les signatures de méthode appropriées sur plusieurs classes qui implémentent l’interface.

   Les signatures de la méthode de l’interface sont créées et prêtes à être implémentées.

   - C# :

       ![Résultat de l’implémentation de l’interface (C#)](media/interface-result-cs.png)

   - Visual Basic :

       ![Résultat de l’implémentation de l’interface (VB)](media/interface-result-vb.png)

   > [!TIP]
   > (C# uniquement) Utilisez l’option **Implémenter l’interface explicitement** pour faire précéder chaque méthode générée du nom de l’interface et éviter ainsi les conflits de noms.
   >
   > ![Résultat de l’action Implémenter l'interface explicitement](media/interface-explicitresult-cs.png);

## <a name="see-also"></a>Voir aussi

- [Génération de code](../code-generation-in-visual-studio.md)
- [Aperçu des modifications](../../ide/preview-changes.md)