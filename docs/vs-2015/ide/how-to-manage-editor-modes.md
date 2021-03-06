---
title: Guide pratique pour gérer les modes de l’éditeur | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- word wrap
- views, virtual space
- line numbers, displaying
- virtual space mode
- line numbers
- Code Editor, view and display options
- full screen mode
- Code Editor, modes
- views, splitting
- views, word wrapping
- fonts and size
- views, creating new windows
- views, line numbers
- views, changing mode
- views, outlining
ms.assetid: 1fb48027-d870-439f-8b72-4a0321390748
caps.latest.revision: 24
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a188e90d3feeb903eb8b4efceb91eb53cac3bdce
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72651846"
---
# <a name="how-to-manage-editor-modes"></a>Guide pratique pour gérer les modes de l'éditeur
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez afficher l’éditeur de code Visual Studio dans différents modes d’affichage.

> [!NOTE]
> Les boîtes de dialogue et les commandes de menu affichées peuvent différer de celles décrites dans l'Aide selon les paramètres actifs ou le mode d'édition. Pour modifier vos paramètres, choisissez **Paramètres d'importation et d'exportation** dans le menu **Outils** . Pour plus d’informations, consultez [Personnalisation des paramètres de développement dans Visual Studio](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).

## <a name="enabling-full-screen-mode"></a>Activation du mode Plein écran
 Vous pouvez choisir de masquer toutes les fenêtres outil et d’afficher uniquement les fenêtres de document en activant le mode **plein écran** .

#### <a name="to-enable-full-screen-mode"></a>Pour activer le mode Plein écran

- Appuyez sur Alt+Maj+Entrée pour entrer en mode **Plein écran** ou le quitter.

     \- ou -

- Exécutez la commande `View.Fullscreen` dans la fenêtre **Commande**.

## <a name="enabling-virtual-space-mode"></a>Activation du mode Espace virtuel
 En mode **Espace virtuel**, des espaces sont insérés à la fin de chaque ligne de code. Sélectionnez cette option pour placer des commentaires en un point précis, proche de votre code.

#### <a name="to-enable-virtual-space-mode"></a>Pour activer le mode Espace virtuel

1. Sélectionnez **Options** dans le menu **Outils**.

2. Développez le dossier **Éditeur de texte** et choisissez **Tous les langages** pour définir cette option globalement, ou choisissez un dossier de langage spécifique. (Par exemple, pour activer les numéros de ligne uniquement dans Visual Basic, choisissez les options De base, Éditeur de texte.)

3. Sélectionnez les options **Général**, puis, sous **Paramètres**, sélectionnez **Activer l’espace virtuel**.

    > [!NOTE]
    > **Espace virtuel** est activé dans le mode **Sélectionner les colonnes**. Lorsque le mode **Espace virtuel** n’est pas activé, le point d’insertion passe de la fin d’une ligne directement au premier caractère de la suivante.

## <a name="see-also"></a>Voir aussi
 [Personnalisation de l’éditeur](../ide/customizing-the-editor.md) [Comment : organiser et ancrer](../misc/how-to-arrange-and-dock-windows.md) les [polices et couleurs Windows, environnement, boîte de dialogue Options](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)
