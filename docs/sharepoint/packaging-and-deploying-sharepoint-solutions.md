---
title: Empaquetage et déploiement de Solutions SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- packaging [SharePoint development in Visual Studio]
- deploying [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, packaging and deploying
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6c5993f09581faf6e3cedb4c71598ea26b16b699
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49863267"
---
# <a name="package-and-deploy-sharepoint-solutions"></a>Empaqueter et déployer des solutions SharePoint
  En règle générale, une solution SharePoint est déployée sur un serveur SharePoint à l’aide d’un fichier de package (.wsp) de solution. Vous pouvez utiliser Visual Studio pour organiser vos éléments de projet SharePoint en fonctionnalités et pour créer un package pour déployer vos fonctionnalités SharePoint.  
  
 Cette rubrique fournit les informations suivantes :  
  
-   [Création de fonctionnalités et des Packages](#Creating)  
  
-   [Fonctionnalité et empaquetage de prise en charge de l’outil](#Tools)  
  
-   [Déploiement de Solutions SharePoint](#Deploying)  
  
-   [Déploiement de fichiers dans les Solutions SharePoint](#DeployingFiles)  
  
## <a name="create-features-and-packages"></a>Créer des fonctionnalités et des packages
 Vous pouvez utiliser Visual Studio pour regrouper des éléments SharePoint connexes dans un *fonctionnalité*. Par exemple, une fonctionnalité pour une définition de liste de Contacts peut inclure l’instance de liste et la définition de liste. Vous pouvez combiner ces deux éléments dans une fonctionnalité unique à des fins de déploiement. Pour plus d’informations sur les fonctionnalités, consultez [bloc de construction : fonctionnalités](http://go.microsoft.com/fwlink/?LinkID=169183).  
  
 Ensuite, vous pouvez créer un package de solution SharePoint (*.wsp*) pour les regrouper plusieurs fonctionnalités, site définitions, des assemblys et autres fichiers dans un package unique, qui stocke les fichiers dans le format requis par SharePoint pour déployer les fichiers à le serveur. Pour plus d’informations, consultez [bloc de construction : Solutions](http://go.microsoft.com/fwlink/?LinkID=169186).  
  
## <a name="feature-and-packaging-tool-support"></a>Prise en charge des outils de packaging et de fonctionnalité
 Vous pouvez utiliser les outils de développement SharePoint dans Visual Studio pour rapidement organiser vos fichiers SharePoint en fonctionnalités et les packages de solution pour simplifier le déploiement. Vous pouvez utiliser les outils suivants pour configurer le package de solution et de fonctionnalité.  
  
-   Concepteur de fonctionnalités et le Concepteur de packages.  
  
-   Explorateur de package, une fenêtre outil.  
  
-   Explorateur de solutions.  
  
### <a name="feature-designer-and-package-designer"></a>Concepteur de fonctionnalités et le Concepteur de packages
 Vous pouvez créer des fonctionnalités, définir des étendues et marquer les autres fonctionnalités en tant que dépendances à l’aide du Concepteur de fonctionnalités. Le concepteur affiche également le fichier XML final qui décrit chaque fonctionnalité. Pour plus d’informations, consultez [fonctionnalités SharePoint créer](../sharepoint/creating-sharepoint-features.md).  
  
 Appliquer la fonctionnalité à un site Web spécifique ou un groupe de sites Web en définissant son *étendue* dans le Concepteur de fonctionnalités. Si une fonctionnalité est activée pour un site Web individuel, la fonctionnalité fonctionne uniquement dans un site Web donné. Si une fonctionnalité est activée pour une collection de sites, les éléments dans la fonctionnalité s’appliquent à la collection de l’ensemble du site. Pour plus d’informations, consultez [étendue de l’élément](http://go.microsoft.com/fwlink/?LinkID=169189).  
  
 Si votre fonctionnalité repose sur d’autres fonctionnalités, vous pouvez définir un *dépendance d’activation des fonctionnalités* pour marquer les fonctionnalités dépendantes avant de rendre votre fonctionnalité disponible. Une dépendance d’activation de fonctionnalité vérifie si les fonctionnalités dépendantes sont déjà activées pour cette étendue. Pour plus d’informations, consultez [dépendances d’Activation et étendue](http://go.microsoft.com/fwlink/?LinkID=169190).  
  
 Dans le Concepteur de packages, vous pouvez regrouper des éléments de SharePoint dans un package de solution unique et configurer s’il faut réinitialiser le serveur Web pendant le déploiement. Pour définir le type de serveur de déploiement, utilisez le **propriétés** fenêtre. Le concepteur génère également le fichier XML qui décrit le contenu du package. Pour plus d’informations, consultez [packages de solution SharePoint créer](../sharepoint/creating-sharepoint-solution-packages.md).  
  
 Au cours du déploiement, le service Internet Information Services (IIS) est arrêté pour copier les fichiers de solution sur le serveur SharePoint. À l’aide du Concepteur de packages dans Visual Studio, vous pouvez sélectionner si le serveur Web doit être redémarré. Pour configurer si la solution est déployée sur un serveur Web frontal ou un serveur d’applications, utilisez la **propriétés** fenêtre. Pour plus d’informations, consultez [élément de Solution (Solution)](http://go.microsoft.com/fwlink/?LinkID=169191).  
  
### <a name="packaging-explorer"></a>Explorateur de package  
 Pour compléter le Concepteur de fonctionnalités et le Concepteur de packages, vous pouvez utiliser l’Explorateur de package pour regrouper vos fichiers SharePoint en fonctionnalités et packages. En outre, vous pouvez voir la vue hiérarchique du projet SharePoint package, fonctionnalités, des fichiers et des éléments. L’Explorateur de package est une fenêtre outil que vous pouvez utiliser pour effectuer les tâches suivantes :  
  
- Ouvrir des fichiers et des éléments de projet SharePoint.  
  
- Faites glisser les éléments de projet SharePoint à partir d’une fonctionnalité à un autre.  
  
- Faites glisser les éléments de projet SharePoint et des fonctionnalités à partir d’un package à un autre.  
  
- Ajouter une nouvelle fonctionnalité à un package.  
  
- Ouvrir un concepteur de fonctionnalités ou de packages.  
  
- Valider les fonctionnalités et les packages.  
  
  Les outils de développement SharePoint dans Visual Studio ont des règles de validation pour garantir que le package de solution est correctement formé. En outre, les règles de vérifient que le *.wsp* fichier solution peut être déployé et activé sur un serveur SharePoint. Pour plus d’informations sur le schéma XML pour les fonctionnalités, consultez [schémas](http://go.microsoft.com/fwlink/?LinkID=169192).  
  
  Vous pouvez ajouter des règles de validation de package et de fonctionnalité personnalisée pour le système de projet SharePoint. Pour plus d’informations, consultez [Comment : créer des règles de validation pour les solutions SharePoint fonctionnalité personnalisée et un package](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).  
  
  Pour plus d’informations sur l’Explorateur de package, consultez [Comment : ajouter et supprimer des fonctionnalités et des éléments dans un Package à l’aide de l’Explorateur de package](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer.md).  
  
### <a name="solution-explorer"></a>Explorateur de solutions
 Vous pouvez utiliser l’Explorateur de solutions pour parcourir et ouvrir les fichiers du projet SharePoint. Utilisez le menu contextuel dans l’Explorateur de solutions pour ajouter des fonctionnalités, des récepteurs d’événements et les ressources de fonctionnalité. En outre, vous pouvez ouvrir le Concepteur de fonctionnalités et les concepteurs de Package pour configurer les fonctionnalités et les packages pour le déploiement.  
  
## <a name="deploy-sharepoint-solutions"></a>Déployer des solutions SharePoint
 Une fois que vous personnalisez les fonctionnalités et le package dans Visual Studio, vous pouvez créer un *.wsp* fichier à déployer sur des serveurs SharePoint. Vous pouvez utiliser Visual Studio pour déboguer et tester le. *wsp* uniquement sur le serveur SharePoint sur l’ordinateur de développement. Pour plus d’informations sur la façon de déployer vos solutions SharePoint sur un serveur SharePoint distant, consultez [déploiement d’une Solution](http://go.microsoft.com/fwlink/?LinkID=169194).  
  
 Vous pouvez également personnaliser les étapes de déploiement sur l’ordinateur de développement. Pour plus d’informations, consultez [déployer, publier et mettre à niveau de packages de solution SharePoint](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md).  
  
## <a name="deploy-files-in-sharepoint-solutions"></a>Déployer des fichiers dans les solutions SharePoint
 En règle générale, lorsque vous ajoutez un élément de projet SharePoint à votre solution SharePoint, tous les fichiers requis sont inclus. Les fichiers qui peuvent être compilés (fichiers de code) sont intégrées à l’assembly de sortie de la solution. Toutefois, vous devrez également ajouter des fichiers non compilables, par exemple, *.xml*, *.txt*, ou des fichiers de ressources, à un projet SharePoint. Ces fichiers ne sont pas créés automatiquement dans votre solution. Pour vous assurer qu’ils sont empaquetés, ajoutez les fichiers dans un dossier mappé ou à un élément de projet SharePoint.  
  
 Fichiers ajoutés aux dossiers mappés sont automatiquement copiés dans la ruche SharePoint lorsque la solution est déployée. Fichiers ajoutés à un élément de projet SharePoint sont déployés à l’emplacement spécifié dans le **emplacement de déploiement** propriété pour chaque fichier, ce qui est partiellement défini selon la **Type de déploiement** propriété. Par défaut, le **Type de déploiement** valeur de propriété est **NoDeployment**, ce qui signifie que le fichier n’est pas déployé avec la solution. Vous devez définir une autre valeur pour la propriété à inclure le fichier dans le package.  
  
 Par exemple, pour ajouter un *.xml* de fichier à un projet SharePoint, effectuez l’une des actions suivantes :  
  
- Ajouter un dossier mappé de « Dispositions » SharePoint à votre projet. Cette opération crée dans **l’Explorateur de solutions** un dossier nommé **dispositions** qui comporte un sous-dossier pour le projet. Ajouter le *.xml* fichier dans le nouveau sous-dossier. Par défaut, le fichier est déployé dans le système de fichiers SharePoint sous *... \TEMPLATE\LAYOUTS\\\<nom du dossier >*. Pour plus d’informations sur l’ajout de dossiers mappés, consultez [Comment : ajouter et supprimer des dossiers mappés](../sharepoint/how-to-add-and-remove-mapped-folders.md).  
  
- Ajouter le *.xml* de fichiers dans le dossier d’un élément de projet SharePoint et modifiez le **Type de déploiement** propriété de la *.xml* à partir de fichiers **NoDeployment**  à un autre paramètre comme **RootFile** ou **ElementFile**. Approprié **Type de déploiement** paramètre varie selon le fichier et le projet. Pour plus d’informations sur la **Type de déploiement** paramètres de propriété, consultez [SharePoint de développer des solutions](../sharepoint/developing-sharepoint-solutions.md).  
  
  Si un fichier ajouté ne s’applique pas à un projet spécifique dans la solution, vous pouvez ajouter un projet SharePoint vide à votre solution et puis ajoutez les fichiers supplémentaires à ce dernier. Une autre solution pour le déploiement des fichiers sur SharePoint, en particulier pour la base de données de contenu, consiste à ajouter un module au projet, puis ajouter les fichiers au module. Pour plus d’informations, consultez [utiliser des modules pour inclure des fichiers dans la solution](../sharepoint/using-modules-to-include-files-in-the-solution.md).  
  
## <a name="see-also"></a>Voir aussi
 [Développer des solutions SharePoint](../sharepoint/developing-sharepoint-solutions.md)   
 [Générer et déboguer des solutions SharePoint](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
  
