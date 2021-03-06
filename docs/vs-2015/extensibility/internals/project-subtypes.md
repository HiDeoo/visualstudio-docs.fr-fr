---
title: Sous-types de projet | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], subtypes
- project subtypes [Visual Studio SDK]
ms.assetid: d235b47b-cf11-4d47-a63f-e33d9d16105d
caps.latest.revision: 21
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 5ad1e105d43c40782b13d8799b20626e57363c2f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "90839322"
---
# <a name="project-subtypes"></a>Sous-types de projets
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Les sous-types de projet vous permettent de personnaliser ou de parfumer le comportement des systèmes de projet de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] . Les personnalisations incluent l’enregistrement de données supplémentaires dans le fichier projet, l’ajout ou le filtrage d’éléments dans la boîte de dialogue **Ajouter un nouvel élément** , le contrôle de la façon dont les assemblys sont débogués et déployés et l’extension de la boîte de dialogue **pages de propriétés** du projet. Les VSPackages implémentent des sous-types de projet à l’aide de l’agrégation COM.  
  
> [!NOTE]
> Le système de projet Visual C++ ne prend pas en charge les sous-types de projet. [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] elle-même utilise des sous-types de projet pour implémenter SQL Server et des projets Smart Device.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Conception de sous-types de projets](../../extensibility/internals/project-subtypes-design.md)  
 Décrit le concept de sous-types de projet.  
  
 [Séquence d’initialisation des sous-types de projets](../../extensibility/internals/initialization-sequence-of-project-subtypes.md)  
 Décrit la séquence d’initialisation de sous-type de projet de programmation par [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] environnement.  
  
 [Propriétés et méthodes étendues par les sous-types de projets](../../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)  
 Fournit des descriptions détaillées des fonctionnalités et des méthodes les plus fréquemment étendues à l’aide de sous-types de projet.  
  
 [Données persistantes dans le fichier projet MSBuild](../../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)  
 Décrit comment rendre des données persistantes dans un fichier projet et comment utiliser <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> pour gérer les données dans le fichier projet à travers les niveaux d’agrégation de sous-type de projet.  
  
 [Interface utilisateur des propriétés du projet](../../extensibility/internals/project-property-user-interface.md)  
 Décrit comment les sous-types de projet peuvent modifier la boîte de dialogue **pages de propriétés** du projet.  
  
 [Extension du modèle d’objet du projet de base](../../extensibility/internals/extending-the-object-model-of-the-base-project.md)  
 Fournit des informations sur la façon dont les sous-types de projet peuvent utiliser des extendeurs Automation pour étendre le modèle objet Automation.  
  
 [Contribution à la boîte de dialogue Ajouter un élément](../../extensibility/internals/contributing-to-the-add-new-item-dialog-box.md)  
 Décrit comment ajouter des éléments à la boîte de dialogue **Ajouter un nouvel élément** .  
  
 [Enregistrement de données dans les fichiers de projet](../../extensibility/saving-data-in-project-files.md)  
 Explique comment un sous-type de projet peut enregistrer et récupérer des données spécifiques au sous-type dans le fichier projet à l’aide de Managed package Framework (MPF).  
  
 [Gestion de déploiement spécialisé](../../extensibility/internals/handling-specialized-deployment.md)  
 Explique comment les sous-types de projet peuvent fournir un comportement de déploiement spécialisé en implémentant l' <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> interface.  
  
 [Ajout et suppression de pages de propriétés](../../extensibility/adding-and-removing-property-pages.md)  
 Décrit l’ajout et la suppression de pages de propriétés dans le concepteur de projets.  
  
## <a name="related-sections"></a>Sections connexes  
 [Types de projets](../../extensibility/internals/project-types.md)  
 Fournit des liens vers des rubriques détaillant les [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] projets.
