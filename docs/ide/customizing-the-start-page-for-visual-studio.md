---
title: Installer une page de démarrage personnalisée ou modifier l’élément de démarrage
ms.date: 02/01/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start Page
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d3514effbe9b8affd870e46746b308216a80de33
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53864788"
---
# <a name="customize-the-start-page-for-visual-studio"></a>Personnaliser la page de démarrage de Visual Studio

Vous pouvez personnaliser l’expérience de démarrage de Visual Studio de plusieurs façons, par exemple en affichant la boîte de dialogue **Ouvrir un projet** ou en ouvrant la solution chargée en dernier. Vous pouvez également afficher une page de démarrage personnalisée, qui est une page WAML WPF (Windows Presentation Foundation) qui s'exécute dans une fenêtre d'outil et peut exécuter des commandes internes à Visual Studio.

## <a name="to-change-the-startup-item"></a>Pour modifier l’élément de démarrage

1. Dans la barre de menus, choisissez **Outils** > **Options**.

1. Développez **Environnement**, puis choisissez **Démarrage**.

1. Dans la liste **Au démarrage**, choisissez l’élément à afficher au démarrage de Visual Studio.

## <a name="to-show-a-custom-start-page"></a>Pour afficher une page de démarrage personnalisée

Vous pouvez [créer votre propre page de démarrage personnalisée](../extensibility/creating-a-custom-start-page.md) à l’aide du Kit SDK Visual Studio ou vous pouvez en utiliser une déjà créée par un autre utilisateur. Vous pouvez, par exemples, trouver des pages de démarrage personnalisées dans la [Place de marché Visual Studio](https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=&subCategory=Start%20Pages&sortBy=Downloads).

Pour installer une page de démarrage personnalisée, ouvrez le fichier *.vsix*, ou effectuez un copier-coller des fichiers de la page de démarrage dans le dossier *%USERPROFILE%\Documents\Visual Studio 2017\StartPages* sur votre ordinateur.

### <a name="to-select-which-custom-start-page-to-display"></a>Pour sélectionner la page de démarrage personnalisée à afficher

1. Dans la barre de menus, choisissez **Outils** > **Options**.

1. Développez **Environnement**, puis choisissez **Démarrage**.

1. Dans la liste **Personnaliser la page de démarrage**, choisissez la page que vous souhaitez.

> [!NOTE]
> Si une erreur dans une page de démarrage personnalisée provoque le blocage de Visual Studio, vous pouvez démarrer Visual Studio en mode sans erreur, puis le configurer pour utiliser la page de démarrage par défaut. Consultez [/SafeMode (devenv.exe)](../ide/reference/safemode-devenv-exe.md).

## <a name="see-also"></a>Voir aussi

- [Personnaliser l’IDE Visual Studio](../ide/personalizing-the-visual-studio-ide.md)