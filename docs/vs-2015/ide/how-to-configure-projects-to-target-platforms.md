---
title: Guide pratique pour configurer des projets afin de cibler des plateformes | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- project settings [Visual Studio], targeting platforms
- platforms, targeting specific CPUs
- project properties [Visual Studio], targeting platforms
- projects [Visual Studio], targeting platforms
- 64-bit [Visual Studio]
- 64-bit programming [Visual Studio]
- CPUs, targeting specific
- 64-bit applications [Visual Studio]
ms.assetid: 845302fc-273d-4f81-820a-7296ce91bd76
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e6ba899fd1b17fa5a82c64d5c5e44e67f0d5eb97
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72668190"
---
# <a name="how-to-configure-projects-to-target-platforms"></a>Guide pratique pour configurer des projets afin de cibler des plateformes
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] vous permet de configurer vos applications pour cibler différentes plateformes (y compris des plateformes 64 bits). Pour plus d’informations sur la prise en charge de la plateforme 64 bits dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , consultez [applications 64 bits](https://msdn.microsoft.com/library/fd4026bc-2c3d-4b27-86dc-ec5e96018181).

## <a name="targeting-platforms-with-the-configuration-manager"></a>Ciblage de plateformes avec le Gestionnaire de configurations
 Le **Gestionnaire de configurations** vous permet d’ajouter rapidement une nouvelle plateforme à cibler avec votre projet. Si vous sélectionnez l'une des plateformes incluses avec [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], les propriétés de votre projet sont modifiées afin de générer votre projet pour la plateforme sélectionnée.

#### <a name="to-configure-a-project-to-target-a-64-bit-platform"></a>Pour configurer un projet pour cibler une plateforme 64 bits

1. Dans la barre de menus, choisissez **Générer**, puis **Gestionnaire de configurations**.

2. Dans la liste **Plateforme de la solution active**, choisissez une plateforme 64 bits pour la solution à cibler, puis choisissez le bouton **Fermer**.

   1. Si la plateforme voulue ne s’affiche pas dans la liste **Plateforme de la solution active**, choisissez **Nouveau**.

        La boîte de dialogue **Nouvelle plateforme de solution** s’affiche.

   2. Dans la liste **Tapez ou sélectionnez la nouvelle plateforme**, choisissez **x64**.

       > [!NOTE]
       > Si vous affectez un nouveau nom à votre configuration, vous devrez peut-être modifier les paramètres dans le **Concepteur de projet** pour cibler la plateforme correcte.

   3. Si vous souhaitez copier les paramètres d’une configuration de plateforme actuelle, choisissez-la, puis choisissez le bouton **OK**.

   Les propriétés de tous les projets qui ciblent la plateforme 64 bits sont mises à jour et la prochaine génération du projet est optimisée pour les plateformes 64 bits.

## <a name="targeting-platforms-in-the-project-designer"></a>Ciblage de plateformes dans le Concepteur de projets
 Le Concepteur de projets permet également de cibler différentes plateformes avec votre projet. Si la sélection de l’une des plateformes incluses dans la liste affichée dans la boîte de dialogue **Nouvelle plateforme de solution** ne fonctionne pas pour votre solution, vous pouvez créer un nom de configuration personnalisée, puis en modifier les paramètres dans le **Concepteur de projet** pour cibler la plateforme appropriée.

 L’exécution de cette tâche varie suivant le langage de programmation que vous utilisez. Pour plus d’informations, consultez les liens suivants :

- Pour les projets [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], consultez [/platform (Visual Basic)](https://msdn.microsoft.com/library/f9bc61e6-e854-4ae1-87b9-d6244de23fd1).

- Pour les [!INCLUDE[csprcs](../includes/csprcs-md.md)] projets, consultez [Générer, page du concepteur de projets (C#)](../ide/reference/build-page-project-designer-csharp.md).

- Pour les [!INCLUDE[vcprvc](../includes/vcprvc-md.md)] projets, consultez [/clr (compilation pour le Common Language Runtime)](https://msdn.microsoft.com/library/fec5a8c0-40ec-484c-a213-8dec918c1d6c).

## <a name="see-also"></a>Voir aussi
 [Fonctionnement des plateformes de génération](../ide/understanding-build-platforms.md) [/Platform (options du compilateur C#)](https://msdn.microsoft.com/library/c290ff5e-47f4-4a85-9bb3-9c2525b0be04) [64-bits applications](https://msdn.microsoft.com/library/fd4026bc-2c3d-4b27-86dc-ec5e96018181) [Visual Studio IDE 64 bits support](../ide/visual-studio-ide-64-bit-support.md)
