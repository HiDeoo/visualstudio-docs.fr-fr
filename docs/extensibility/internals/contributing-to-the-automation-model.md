---
title: Contribution au modèle Automation | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK]
ms.assetid: 44de482d-93c8-41a4-843c-cefda995a03e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d660edc740229c3e91b99e1f59eb37b4e9312098
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80709268"
---
# <a name="contribute-to-the-automation-model"></a>Contribuer au modèle Automation
Visual Studio fournit un ensemble d’interfaces d’automatisation pour la personnalisation de l’environnement. Le modèle Automation est le modèle objet qui permet aux utilisateurs finaux de créer des compléments et des extensions Visual Studio.

 En outre, il convient, en tant que développeur VSPackage, de contribuer au modèle Automation. en procédant ainsi, vous permettez aux utilisateurs finaux de votre VSPackage de créer des compléments et de fournir en général une expérience de modèle utilisateur cohérente lorsqu’ils utilisent votre VSPackage dans [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] .

 Pour rendre l’expérience de l’utilisateur final cohérente, vous pouvez suivre un ensemble d’instructions lors de la conception de votre VSPackage afin que le modèle Automation pour votre VSPackage suive les idées dans [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] .

## <a name="in-this-section"></a>Contenu de cette section
- [Vue d’ensemble du modèle Automation](../../extensibility/internals/automation-model-overview.md)

 Définit le modèle Automation en tant que groupes d’objets connexes qui contrôlent les facettes principales de l’environnement commun. Cet ensemble d’objets est représenté dans un diagramme du modèle Automation.

- [Fournir une automatisation pour les VSPackages](../../extensibility/internals/providing-automation-for-vspackages.md)

 Décrit les deux principales façons de fournir une automatisation pour votre VSPackage.

- [Exposer des objets de projet](../../extensibility/internals/exposing-project-objects.md)

 Fournit des instructions pas à pas pour la création d’objets spécifiques au VSPackage.

- [Modélisation de projet](../../extensibility/internals/project-modeling.md)

 Explique les objets de projet standard qui sont requis pour créer l’automatisation pour votre nouveau type de projet et illustre le chemin d’accès de l’Automation de projet. Cette rubrique fournit également des listes de déclarations et d’implémentation pour les classes.

- [Exposer des événements](../../extensibility/internals/exposing-events-in-the-visual-studio-sdk.md)

 Fournit des instructions pas à pas pour la création d’événements pour votre modèle Automation.

- [Prise en charge d’Automation pour les pages d’options](../../extensibility/internals/automation-support-for-options-pages.md)

 Décrit comment retourner un objet Automation pour les propriétés de prise en charge de la boîte de dialogue **options** personnalisées d’un VSPackage dans le menu **outil** en étendant l' `DTE.Properties` objet.

- [Fournir l’automatisation pour le code](../../extensibility/internals/providing-automation-for-code.md)

 Explique que la création d’un modèle Automation pour votre code n’est pas obligatoire. Toutefois, un lien est fourni dans cette rubrique qui fournit des informations pertinentes dans les modèles de code.

- [Comment : fournir une automatisation pour Windows](../../extensibility/internals/how-to-provide-automation-for-windows.md)

 Explique que l’automatisation est une bonne idée quand vous souhaitez rendre des objets Automation disponibles dans une fenêtre, et que l’environnement ne fournit pas déjà un objet Automation prêt à l’emploi. Traite de l’automatisation pour les fenêtres outil et les fenêtres de document.

- [Utiliser le modèle Automation](../../extensibility/internals/using-the-automation-model.md)

 Fournit deux exemples de code qui montrent comment un consommateur Automation obtient les objets Automation de projet initiaux.

- [Automatisation pour la configuration et les objets SelectedItem](../../extensibility/internals/automation-for-configuration-and-selecteditem-objects.md)

 Fournit des informations sur l’automatisation pour les objets Configuration et SelectedItems.

## <a name="reference"></a>Référence
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> Fournit un exemple de code qui montre comment un VSPackage participe au modèle objet d’automatisation DTE. Répertorie les paramètres, les valeurs de retour et les notes sélectionnées.
