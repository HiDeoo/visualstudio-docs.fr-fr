---
title: Création de Pages pour SharePoint | Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, master pages
- SharePoint development in Visual Studio, page layouts
- SharePoint development in Visual Studio, content pages
- master pages[SharePoint development in Visual Studio], designing
- content pages[SharePoint development in Visual Studio], designing
- page layouts[SharePoint development in Visual Studio], designing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f58af55b18d7cd6341b779d71da2994875c98a62
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62419883"
---
# <a name="create-pages-for-sharepoint"></a>Créer des pages pour SharePoint
  Vous pouvez créer des pages d’application, les pages de site, les pages maîtres et les mises en page pour un site SharePoint.

 Vous pouvez créer des pages d’application à l’aide d’un modèle dans Visual Studio. Créer des pages de site, les pages maîtres et les mises en page, à l’aide de SharePoint Designer. Ensuite, vous pouvez importer ces pages dans Visual Studio pour les utiliser dans un projet SharePoint.

 Vous pouvez également modifier l’apparence et le comportement des pages à l’aide de feuilles de style en cascade, ECMAScript et thèmes.

## <a name="types-of-sharepoint-pages"></a>Types de pages de SharePoint
 Le tableau suivant décrit les quatre principaux types de pages qui contient un site SharePoint.

|Type de page|Description|
|---------------|-----------------|
|Pages d’application|Créer une page d’application si vous souhaitez que la page contienne du code personnalisé ou si vous souhaitez que la page à partager entre plusieurs sites. Sinon, une page de site peut être le meilleur choix.|
|Pages de site|Créer une page de site si vous souhaitez effectuer l’une des tâches suivantes :<br /><br /> -Ajouter la page à une bibliothèque SharePoint.<br />-Activer la page pour les fonctionnalités d’hôte telles que la dynamique des composants WebPart et des Zones de composants WebPart.<br />-Autoriser les utilisateurs à personnaliser la page à l’aide de SharePoint Designer.<br /><br /> Ne créez pas une page de site si vous souhaitez que la page contienne du code personnalisé. Bien que vous pouvez ajouter du code personnalisé à une page de site, le code s’arrête lorsque l’utilisateur personnalise la page à l’aide de SharePoint Designer.|
|Pages maîtres|Créer une page maître, si vous souhaitez définir une structure commune pour les pages de site et les pages d’application.|
|Mises en page|Mises en page sont spécifiques à [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] et vous permettent de définir plus précisément une structure commune pour les pages de site et les pages d’application.|

 Pour une vue d’ensemble de chaque type de page, consultez [bloc de construction : Pages et l’Interface utilisateur](http://go.microsoft.com/fwlink/?LinkID=182095), et [mises en Page et Pages maîtres](http://go.microsoft.com/fwlink/?LinkID=182096).

## <a name="create-application-pages"></a>Créer des pages d’application
 Vous pouvez créer des pages d’application dans Visual Studio en ajoutant un **Page Application** élément à un projet SharePoint. Vous pouvez ajouter des contrôles à la page et ensuite gérer les événements de contrôle en ajoutant du code.

 Vous pouvez définir des points d’arrêt dans le fichier de code de la page, démarrez le débogueur et tester la page sur un site SharePoint local sans effectuer des étapes de configuration supplémentaires. Pour plus d’informations, consultez [création de Pages d’Application pour SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).

## <a name="create-site-pages-master-pages-and-page-layouts"></a>Créer des pages de site, les pages maîtres et les mises en page
 Vous pouvez créer des pages de site, les pages maîtres et les mises en page à l’aide de SharePoint Designer. Ensuite, vous pouvez importer ces pages dans Visual Studio. Importez vos pages si vous souhaitez tirer parti du déploiement ou de fonctionnalités de contrôle de code source qui sont disponibles dans Visual Studio. Pour plus d’informations, consultez [l’importation d’éléments à partir d’un SharePoint Site existant](../sharepoint/importing-items-from-an-existing-sharepoint-site.md).

 Comme il est difficile de modifier ces pages après leur importation, vous devez concevoir ces pages avant de les importer.

## <a name="create-cascading-style-sheets-ecmascript-and-themes"></a>Créer des feuilles de style en cascade, ECMAScript et thèmes
 Visual Studio ne fournit pas de modèles pour le développement des feuilles de Style en cascade (CSS), ECMAScript (JavaScript, JScript) ou les fichiers de thème pour les sites SharePoint. Vous pouvez créer ces fichiers à l’aide des instructions disponibles dans le SDK de SharePoint ou à l’aide des outils tels que SharePoint Designer.

 Vous pouvez ajouter ces fichiers à votre solution directement, ou vous pouvez les importer. Dans les deux cas, vous devez créer les dossiers mappés appropriés pour chaque élément que vous ajoutez. Pour plus d’informations sur la création d’un dossier mappé, consultez [Comment : ajouter et supprimer des dossiers mappés](../sharepoint/how-to-add-and-remove-mapped-folders.md).

 Pour plus d’informations sur la création de feuilles de Style en cascade, consultez [Cascading Style Sheets l’utilisation des classes dans SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkID=182098). Pour plus d’informations sur la création de fichiers JavaScript et JScript pour une solution SharePoint, consultez [paramètre d’une Page ASPX de base pour ECMAScript](http://go.microsoft.com/fwlink/?LinkID=182099). Pour plus d’informations sur les thèmes, consultez [bloc de construction : Pages et l’Interface utilisateur](http://go.microsoft.com/fwlink/?LinkID=182095).

## <a name="related-topics"></a>Rubriques connexes

|Titre|Description|
|-----------|-----------------|
|[Créer des pages d’application pour SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)|Décrit comment ajouter des pages d’applications : *.aspx* contenu est fusionné avec une page maître SharePoint.|
|[Guide pratique pour Créer une page d’application](../sharepoint/how-to-create-an-application-page.md)|Vous montre comment créer des pages ASP.NET qui s’exécutent sur un site SharePoint.|
|[Procédure pas à pas : Créer une page d’application SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)|Vous montre comment concevoir et déboguer une page Web ASP.NET pour un site SharePoint.|
