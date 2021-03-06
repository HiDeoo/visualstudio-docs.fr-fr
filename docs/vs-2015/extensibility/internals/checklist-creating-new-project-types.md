---
title: 'Liste de vérification : création de nouveaux types de projets | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], creating new types
- project types, checklist for creating
ms.assetid: 29eb9c3b-1933-4741-aa85-65a33f0825ba
caps.latest.revision: 24
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 02edc5925109a31eebfd98c90bd116fb86eef276
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "65697227"
---
# <a name="checklist-creating-new-project-types"></a>Checklist : création de types de projets
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous devez effectuer plusieurs tâches pour créer un nouveau type de projet. La liste de vérification suivante fournit un guide pour ces tâches.  
  
1. Concevez les fonctionnalités pour votre nouveau type de projet. Pour plus d’informations, consultez [décisions de conception de type de projet](../../extensibility/internals/project-type-design-decisions.md).  
  
2. Déterminez les éditeurs utilisés pour le code et d’autres éléments de projet. Vous pouvez utiliser les éditeurs de base ou standard, ou vous pouvez créer et utiliser des éditeurs spécifiques à un projet. Pour plus d’informations, consultez Création d’éditeurs [et de concepteurs personnalisés](../../extensibility/creating-custom-editors-and-designers.md) et [Comment : ouvrir des éditeurs spécifiques à un projet](../../extensibility/how-to-open-project-specific-editors.md).  
  
3. Déterminez le niveau de participation de vos éléments de projet dans la **affichage de classes** et dans l' **Explorateur d’objets**. Pour plus d’informations, consultez [prise en charge des outils de navigation de symboles](../../extensibility/internals/supporting-symbol-browsing-tools.md).  
  
4. Dérivez les nouvelles classes en fonction des décisions de conception que vous avez prises précédemment pour vos projets et éléments de projet.  
  
5. Écrivez le code pour les composants de type de projet suivants :  
  
    - La fabrique de projets, pour gérer la création de projets et l’ouverture de projets existants. Pour plus d’informations, consultez [création d’instances de projet à l’aide de fabriques de projets](../../extensibility/internals/creating-project-instances-by-using-project-factories.md).  
  
    - Gestion de la hiérarchie de projet et des commandes. Pour plus d’informations, consultez [not in Build : utilisation des classes de projet HierUtil7 pour implémenter un type de projet (C++)](https://msdn.microsoft.com/a5c16a09-94a2-46ef-87b5-35b815e2f346), [éléments d’un modèle de projet](../../extensibility/internals/elements-of-a-project-model.md), composants de [base du modèle de projet](../../extensibility/internals/project-model-core-components.md) et [MenuCommands vs. OleMenuCommands](../../misc/menucommands-vs-olemenucommands.md).  
  
    - Gestion des éléments de projet, y compris l’ajout de votre projet à la boîte de dialogue **nouveau projet** . Pour plus d’informations, consultez [Ajout de modèles de projet et d’élément de projet](../../extensibility/internals/adding-project-and-project-item-templates.md) et inscription de [modèles de projet et d’élément](../../extensibility/internals/registering-project-and-item-templates.md).  
  
    - Persistance de l’état du projet et des éléments individuels. Pour plus d’informations, consultez [ouverture et enregistrement d’éléments de projet](../../extensibility/internals/opening-and-saving-project-items.md). Pour la persistance des informations de solution, consultez [solutions](../../extensibility/internals/solutions-overview.md).  
  
    - Propriétés indépendantes de la configuration à afficher dans la Fenêtre Propriétés. Pour plus d’informations, consultez [extension des propriétés](../../extensibility/internals/extending-properties.md).  
  
    - Propriétés de configuration de projet telles qu’elles sont implémentées dans les pages de propriétés pour afficher les propriétés dépendantes de la configuration. Pour plus d’informations, consultez [gestion des options de configuration](../../extensibility/internals/managing-configuration-options.md).  
  
    - Énumération des sorties pour le déploiement. Pour plus d’informations, consultez [configuration du projet pour la sortie](../../extensibility/internals/project-configuration-for-output.md).  
  
    - Services de démarrage de projet. Pour plus d’informations, consultez [éléments d’un modèle de projet et des composants de base du modèle de](../../extensibility/internals/elements-of-a-project-model.md) [projet](../../extensibility/internals/project-model-core-components.md).  
  
    - Les objets, ou les classes dérivées de `IDispatch` , sont disponibles pour l’automatisation.  
  
    - Fichiers de table de commandes XML (. vsct). Pour plus d'informations, consultez [Visual Studio Command Table (.Vsct) Files](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
6. Testez, déboguez et démarrez votre type de projet.  
  
7. Affichez votre projet sous l’onglet **projet** de la boîte de dialogue **Ajouter une référence** en définissant `VARIANT_TRUE` comme valeur pour `VSHPROPID_ShowProjInSolutionPage` . Pour plus d’informations, consultez <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>.  
  
8. Créez le fichier Microsoft Installer (. msi) pour l’installation de vos VSPackages. Pour plus d’informations, consultez [installation de VSPackages avec Windows Installer](../../extensibility/internals/installing-vspackages-with-windows-installer.md), [inscription d’un type de projet](../../extensibility/internals/registering-a-project-type.md)et [VSPackages](../../extensibility/internals/vspackages.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Hiérarchies dans Visual Studio](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [Quand créer des types de projet](../../extensibility/internals/when-to-create-project-types.md)   
 [Création de types de projets](../../extensibility/internals/creating-project-types.md)
