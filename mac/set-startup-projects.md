---
title: Définir plusieurs projets de démarrage
description: Cet article explique comment définir plusieurs projets à démarrer au moment de l’exécution ou du débogage d’une solution.
author: sayedihashimi
ms.author: sayedha
ms.date: 12/13/2019
ms.topic: how-to
ms.prod: visual-studio-mac
ms.assetid: fd354fff-ce6b-4505-a815-84a2311e39ba
ms.openlocfilehash: e0e1af97ec91af4105d1934a431f9aabc6562793
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85950106"
---
# <a name="set-multiple-startup-projects"></a>Définir plusieurs projets de démarrage

Visual Studio pour Mac vous permet de spécifier le mode de démarrage de plusieurs projets quand vous déboguez ou exécutez votre solution.

## <a name="to-set-multiple-startup-projects"></a>Pour définir plusieurs projets de démarrage

1. Dans le Panneau Solutions, sélectionnez la solution (nœud supérieur).

2. Cliquez avec le bouton droit sur le nœud de la solution, puis sélectionnez **Définir comme projet de démarrage** :

   ![Sélectionnez l’ensemble de projets de démarrage](media/startup-proj-ctx-menu.png)

3. La boîte de dialogue **Créer une configuration d’exécution de solution** s’ouvre. Cette boîte de dialogue vous permet de créer une configuration d’exécution de solution nommée pour votre solution. Vous pouvez utiliser le nom de votre choix. Le nom par défaut est `Multiple Projects`.

   ![Boîte de dialogue Créer une configuration d’exécution de solution](media/create-sln-run-config.png)

4. Sélectionnez **Créer une configuration d’exécution**. La boîte de dialogue **Options de la solution** s’ouvre avec la nouvelle configuration d’exécution de solution sélectionnée :

   ![Boîte de dialogue Options de la solution](media/sln-options-run-config-multi-projects.png)

5. Sélectionnez les projets à démarrer quand vous déboguez ou exécutez votre application à partir de Visual Studio pour Mac :

   ![Boîte de dialogue Options de la solution avec les projets sélectionnés](media/sln-options-run-config-multi-projects-configured.png)

6. Sélectionnez **OK**. La nouvelle configuration d’exécution de solution est définie comme configuration d’exécution active :

   ![Solution avec plusieurs projets configurés pour démarrer en mode débogage ou s’exécuter](media/startup-project-configured.png)

   Vous pouvez voir que deux projets sont configurés pour démarrer, car les deux projets sont en **gras** dans le panneau Solution. Dans la barre d’outils, la nouvelle configuration d’exécution est définie en tant que configuration d’exécution de solution actuelle.

## <a name="next-steps"></a>Étapes suivantes

- [Compilation et génération dans Visual Studio pour Mac](compiling-and-building.md)
- [Présentation des configurations de build](configurations.md)
