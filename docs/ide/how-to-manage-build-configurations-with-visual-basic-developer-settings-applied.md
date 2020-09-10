---
title: Gérer des configurations de build avec les paramètres développeur Visual Basic
titleSuffix: ''
ms.date: 11/21/2018
ms.technology: vs-ide-compile
ms.topic: how-to
helpviewer_keywords:
- advanced build configurations
- building with Visual Basic developer settings (Visual Studio)
- debug builds
- release builds
ms.assetid: eaea6e0b-6c61-4869-8d63-d372c745a23c
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b3feaf36cb250339bd94e0d80a152a8104e75680
ms.sourcegitcommit: 2a201c93ed526b0f7e5848657500f1111b08ac2a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2020
ms.locfileid: "89743233"
---
# <a name="how-to-manage-build-configurations-with-visual-basic-developer-settings-applied"></a>Guide pratique pour gérer des configurations de build en appliquant les paramètres du développeur Visual Basic

Par défaut, toutes les options de configuration de build avancées sont masquées lorsque les paramètres de développeur Visual Basic sont appliqués. Cet article explique comment activer manuellement ces paramètres de build.

## <a name="enable-advanced-build-configurations"></a>Activer les configurations de build avancées

Par défaut, les paramètres de développeur Visual Basic masquent l’option permettant d’ouvrir la boîte de dialogue **Gestionnaire de configuration** et les listes **Configuration** et **Plateforme** dans le [ Concepteur de projets](../ide/reference/application-page-project-designer-visual-basic.md).

1. Dans le menu **Outils** , cliquez sur **Options**.

2. Développez **Projets et solutions** et cliquez sur **Général**.

    > [!NOTE]
    > Le nœud **Général** est visible même si l’option **Afficher tous les paramètres** est désactivée. Si vous souhaitez afficher toutes les options disponibles, cliquez sur **Afficher tous les paramètres**.

3. Cliquez sur **Afficher les configurations de build avancées**.

4. Cliquez sur **OK**.

     Le **Gestionnaire de configuration** est maintenant disponible dans le menu **Build**. De plus, les listes **Configuration** et **Plateforme** sont visibles dans le **Concepteur de projet**.

## <a name="see-also"></a>Voir aussi

- [Présentation des configurations de build](../ide/understanding-build-configurations.md)
- [Compiler et générer](../ide/compiling-and-building-in-visual-studio.md)
- [Paramètres d’environnement](../ide/environment-settings.md)
