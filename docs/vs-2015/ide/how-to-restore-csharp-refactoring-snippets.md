---
title: Guide pratique pour restaurer les extraits de code de refactorisation C# | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- unsafe expansion
- expansions, unsafe
ms.assetid: 12114273-7f2f-43d0-abcb-2d4711a3a68d
caps.latest.revision: 24
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6ae3f1d74a482192d3782aaa87baa816694abcf4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72670788"
---
# <a name="how-to-restore-c-refactoring-snippets"></a>Comment : restaurer les extraits de code de refactorisation C#
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Les opérations de refactorisation C# reposent sur des extraits de code disponibles dans le répertoire suivant :

 *Répertoire d’installation*\Microsoft Visual Studio 14.0\VC#\Snippets\\*ID de langue*\Refactoring

 Si ce répertoire Refactoring, ou tous les fichiers de ce répertoire, sont supprimés ou endommagés, il se peut que les opérations de refactorisation C# ne fonctionnent pas dans l'environnement IDE. Les procédures suivantes peuvent vous aider à restaurer les extraits de code de refactorisation C#.

### <a name="to-verify-c-refactoring-snippets-are-available-through-the-code-snippet-manager"></a>Pour vérifier la disponibilité des extraits de code de refactorisation C# au moyen du Gestionnaire des extraits de code

1. Dans le menu **Outils**, sélectionnez **Gestionnaire des extraits de code**.

2. Dans la boîte de dialogue **Gestionnaire des extraits de code**, sélectionnez **Visual C#** dans la liste déroulante **Langage**.

     Un dossier **Refactoring** doit apparaître dans la liste en arborescence des dossiers.

### <a name="to-restore-refactoring-see-comment-in-code-snippet-manager"></a>Pour restaurer la refactorisation, consultez le commentaire dans le Gestionnaire des extraits de code

1. Si le dossier **Refactoring** n’apparaît pas dans la liste en arborescence des dossiers du Gestionnaire des extraits de code, utilisez cette procédure pour rajouter des extraits de code de refactorisation dans le Gestionnaire des extraits de code.

2. Dans le menu **Outils**, sélectionnez **Gestionnaire des extraits de code**.

3. Dans la boîte de dialogue **Gestionnaire des extraits de code**, sélectionnez **Visual C#** dans la liste déroulante **Langage**.

4. Cliquez sur **Add**. La boîte de dialogue **Répertoire des extraits de code**, qui vous aide à localiser et spécifier le répertoire à rajouter dans le Gestionnaire des extraits de code, s’affiche.

5. Localisez le dossier **Refactoring**, dont le chemin est :

     *Répertoire d’installation*\Microsoft Visual Studio 14.0\VC#\Snippets\\*ID de langue*\Refactoring

     Le chemin d’accès réel est semblable au suivant pour une installation par défaut :

     C:\Program Files\Microsoft Visual Studio 14.0\VC#\Snippets\1033\Refactoring.

6. Cliquez sur **Ouvrir** dans la boîte de dialogue **Répertoire des extraits de code**, puis cliquez sur **OK** dans le Gestionnaire des extraits de code.

## <a name="see-also"></a>Voir aussi
 Extraits de code [Visual c#](../ide/visual-csharp-code-snippets.md) [refactorisation (C#), extraits de](../csharp-ide/refactoring-csharp.md) [code](../ide/code-snippets.md)
