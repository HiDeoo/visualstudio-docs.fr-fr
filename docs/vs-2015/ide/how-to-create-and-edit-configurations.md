---
title: Guide pratique pour créer et modifier des configurations | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- solution build configurations, editing
- build configurations, creating
- solution build configurations, creating
- build configurations, editing
- builds [Visual Studio], setting up
- property pages
- Configuration Manager
- project build configurations, creating
- project build configurations, editing
ms.assetid: 19be121c-148e-4ece-bbfc-d20b08cfc3f7
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d5f5d8bb92b80942a95528a0b2e4c7e64bbfafc8
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72668140"
---
# <a name="how-to-create-and-edit-configurations"></a>Guide pratique pour créer et modifier des configurations
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez créer plusieurs configurations de build pour une solution. Par exemple, vous pouvez configurer une build de débogage que vos testeurs peuvent utiliser pour rechercher et résoudre des problèmes. Vous pouvez également configurer différents types de builds que vous pouvez distribuer à des clients différents.

 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]

## <a name="creating-build-configurations"></a>Création de configurations de build
 Vous pouvez utiliser la boîte de dialogue **Gestionnaire de configurations** pour sélectionner ou modifier des configurations de build existantes, ou en créer de nouvelles.

#### <a name="to-open-the-configuration-manager-dialog-box"></a>Pour ouvrir la boîte de dialogue Gestionnaire de configurations

- Dans l’**Explorateur de solutions**, ouvrez le menu contextuel de la solution, puis choisissez **Gestionnaire de configurations**.

  > [!NOTE]
  > Si la commande **Gestionnaire de configurations** n’apparaît pas dans le menu contextuel, regardez sous le menu **Générer**, dans la barre de menus. Si elle n’y figure pas non plus, dans la barre de menus, choisissez **Outils**, **Options**, puis dans le volet gauche de la boîte de dialogue **Options**, développez **Projets et solutions**, **Général**, et dans le volet droit, cochez la case **Afficher les configurations de build avancées**.

   Dans la boîte de dialogue **Gestionnaire de configurations**, vous pouvez utiliser la liste déroulante **Configuration de la solution active** pour sélectionner une configuration de build à l’échelle de la solution, modifier une configuration existante ou créer une nouvelle configuration. Vous pouvez utiliser la liste déroulante **Plateforme de la solution active** pour sélectionner la plateforme ciblée par la configuration, modifier une plateforme existante ou ajouter une nouvelle plateforme. Le volet **Contextes des projets** répertorie les projets de la solution. Pour chaque projet, vous pouvez sélectionner une plateforme et une configuration spécifiques au projet, modifier celles existantes, ou créer une nouvelle configuration et ajouter une nouvelle plateforme. Vous pouvez également cocher les cases qui indiquent si chaque projet est inclus lorsque vous utilisez la configuration à l’échelle de la solution pour générer ou déployer la solution.

  Après avoir installé les configurations de votre choix, vous pouvez définir les propriétés de projet appropriées pour ces configurations.

#### <a name="to-set-properties-based-on-configurations"></a>Pour définir des propriétés sur la base de configurations

- Dans l’ **Explorateur de solutions**, ouvrez le menu contextuel d’un projet et choisissez **Propriétés**.

     La fenêtre **Pages de propriétés** apparaît.

     Vous pouvez définir des propriétés pour vos configurations. Par exemple, pour une configuration Release, vous pouvez spécifier d’optimiser le code lorsque la solution est générée et, pour une configuration Debug, vous pouvez spécifier d’inclure le symbole de compilation conditionnelle `DEBUG`. Pour plus d’informations sur les paramètres des pages de propriétés, consultez [Présentation du Concepteur de projets](https://msdn.microsoft.com/898dd854-c98d-430c-ba1b-a913ce3c73d7).

## <a name="creating-and-modifying-project-configurations"></a>Création et modification des configurations de projet

#### <a name="to-create-a-project-configuration"></a>Pour créer une configuration de projet

1. Ouvrez la boîte de dialogue **Gestionnaire de configurations**.

2. Sélectionnez un projet dans la colonne **Projet**.

3. Dans la liste déroulante **Configuration** de ce projet, choisissez **Nouveau**.

     La boîte de dialogue **Nouvelle configuration de projet** apparaît.

4. Dans la zone **Nom**, entrez un nom pour la nouvelle configuration.

5. Pour utiliser les paramètres de propriété d’une configuration de projet existante, dans la liste déroulante **Copier les paramètres à partir de**, choisissez une configuration.

6. Pour créer une configuration à l’échelle de la solution au même moment, cochez la case **Créer une nouvelle configuration de solution**.

#### <a name="to-rename-a-project-configuration"></a>Pour renommer une configuration de projet

1. Ouvrez la boîte de dialogue **Gestionnaire de configurations**.

2. Dans la colonne **Projet**, sélectionnez le projet dont vous souhaitez renommer la configuration de projet.

3. Dans la liste déroulante **Configuration** de ce projet, choisissez **Modifier**.

     La boîte de dialogue **Modifier les configurations de projet** apparaît.

4. Sélectionnez le nom de la configuration de projet à modifier.

5. Sélectionnez **Renommer**, puis entrez un nouveau nom.

## <a name="creating-and-modifying-solution-wide-build-configurations"></a>Création et modification de configurations de build à l’échelle de la solution

#### <a name="to-create-a-solution-wide-build-configuration"></a>Pour créer une configuration de build à l’échelle de la solution

1. Ouvrez la boîte de dialogue **Gestionnaire de configurations**.

2. Dans la liste déroulante **Configuration de la solution active**, choisissez **Nouveau**.

     La boîte de dialogue **Nouvelle configuration de solution** apparaît.

3. Dans la zone de texte **Nom**, entrez un nom pour la nouvelle configuration.

4. Pour utiliser les paramètres d’une configuration de solution existante, dans la liste déroulante **Copier les paramètres à partir de**, choisissez une configuration.

5. Si vous souhaitez créer des configurations de projet au même moment, cochez la case **Créer des configurations de projet**.

#### <a name="to-rename-a-solution-wide-build-configuration"></a>Pour renommer une configuration de build à l’échelle de la solution

1. Ouvrez la boîte de dialogue **Gestionnaire de configurations**.

2. Dans la liste déroulante **Configuration de la solution active**, choisissez **Modifier**.

     La boîte de dialogue **Modifier les configurations de solutions** apparaît.

3. Sélectionnez le nom de la configuration de solution à modifier.

4. Sélectionnez **Renommer**, puis entrez un nouveau nom.

#### <a name="to-modify-a-solution-wide-build-configuration"></a>Pour modifier une configuration de build à l’échelle de la solution

1. Ouvrez la boîte de dialogue **Gestionnaire de configurations**.

2. Dans la liste déroulante **Configuration de la solution active**, sélectionnez la configuration de votre choix.

3. Dans le volet **contextes des projets** , pour chaque projet, sélectionnez la **configuration** et la **plateforme** de votre choix, puis indiquez si vous souhaitez la **générer** et si vous voulez la **déployer** .

## <a name="see-also"></a>Voir aussi
 [Compréhension des configurations de build](../ide/understanding-build-configurations.md) [génération et nettoyage des projets et des solutions dans Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md) [bec Comment : modifier les propriétés et les paramètres de configuration](https://msdn.microsoft.com/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) d’un projet
