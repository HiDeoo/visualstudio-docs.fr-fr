---
title: Extension de projets SharePoint | Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6bc92d65ed179c7f2cb2f569a7d254a025887845
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635603"
---
# <a name="extend-sharepoint-projects"></a>Étendre des projets SharePoint
  Créer une extension de projet lorsque vous souhaitez personnaliser les fonctionnalités au niveau du projet des projets SharePoint. Par exemple, vous pouvez ajouter des propriétés de projet personnalisé, ou répondre aux événements au niveau du projet qui sont déclenchés lorsque l’utilisateur développe une solution SharePoint dans Visual Studio.

## <a name="create-project-extensions"></a>Créer des extensions de projet
 Pour étendre un élément de projet, créez un assembly d’extension Visual Studio qui implémente le <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> interface. Pour plus d'informations, voir [Procédure : Créer une extension de projet SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).

 Lorsque vous créez une extension de projet, vous pouvez également ajouter les fonctionnalités suivantes pour les projets SharePoint :

- Ajouter un élément de menu contextuel. L’élément de menu s’affiche lorsque vous ouvrez le menu contextuel pour un nœud de projet SharePoint dans **l’Explorateur de solutions** en double-cliquant sur le nœud ou sélectionnez-le puis en choisissant le **MAJ** +  **F10** clés. Pour plus d'informations, voir [Procédure : Ajouter un élément de menu contextuel à des projets SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md).

- Ajouter une propriété personnalisée. La propriété apparaît dans le **propriétés** fenêtre lorsque vous choisissez un projet SharePoint dans **l’Explorateur de solutions**. Pour plus d'informations, voir [Procédure : Ajouter une propriété à des projets SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md).

  Pour une procédure pas à pas qui montre comment créer, déployer et tester une extension de projet, consultez [procédure pas à pas : Créer une extension de projet SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md).

## <a name="understand-the-relationship-between-project-extensions-and-project-instances"></a>Comprendre la relation entre les extensions de projet et des instances de projet
 Lorsque vous créez une extension de projet, l’extension de charge tout type de projet SharePoint est ouvert dans [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] comprend plusieurs modèles de projet SharePoint, tels que les définitions de listes, les types de contenu et les récepteurs d’événements. Toutefois, il n'est qu’un seul type de projet SharePoint. Les types de projets qui s’affichent dans le **nouveau projet** boîte de dialogue sont uniquement des modèles qui regroupent un ou plusieurs éléments de projet SharePoint. Étant donné qu’un seul type de projet SharePoint, les extensions créées pour un projet s’appliquent à tous les projets SharePoint. Vous ne pouvez pas, par exemple, créer une extension qui s’applique uniquement à un **Type de contenu** projet.

 Pour accéder à une instance de projet spécifique, gérez l’un de la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents> événements de la *projectService* paramètre dans votre implémentation de la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> (méthode). Par exemple, pour déterminer quand un projet SharePoint est ajouté à une solution, gérer la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectAdded> événement. Pour plus d'informations, voir [Procédure : Créer une extension de projet SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).

## <a name="see-also"></a>Voir aussi
- [Guide pratique pour Créer une extension de projet SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md)
- [Guide pratique pour Ajouter un élément de menu contextuel à des projets SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)
- [Guide pratique pour Ajouter une propriété à des projets SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)
- [Procédure pas à pas : Créer une extension de projet SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-project-extension.md)
- [Définir les types d’éléments de projet SharePoint personnalisés](../sharepoint/defining-custom-sharepoint-project-item-types.md)
- [Étendre des éléments de projet SharePoint](../sharepoint/extending-sharepoint-project-items.md)
- [Étendre le déploiement et empaquetage de SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)
- [Étendre le système de projet SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)
