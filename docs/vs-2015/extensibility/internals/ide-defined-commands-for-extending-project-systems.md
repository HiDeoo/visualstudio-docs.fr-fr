---
title: Commandes définies par l’IDE pour l’extension des systèmes de projet | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, project systems
- project systems, environment-defined commands
ms.assetid: 0e33b8e9-16fa-4400-a941-e92d56120e7e
caps.latest.revision: 20
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3b5de061449844b87d60d7a700b1e1c22e1e1282
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68195039"
---
# <a name="ide-defined-commands-for-extending-project-systems"></a>Commandes définies par l’IDE pour l’extension des systèmes de projet
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Lorsque vous souhaitez étendre des systèmes de projet, vous pouvez utiliser des commandes et des groupes de commandes fournis par l' [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE.  
  
 Les sections suivantes répertorient les éléments de commande qui sont particulièrement utiles pour l’extension des systèmes de projet.  
  
## <a name="command-menus"></a>Menus de commande  
 Le tableau suivant présente les menus de commande qui sont des emplacements utiles pour placer des commandes de haut niveau qui appellent un extendeur de projet.  
  
|Menu commande|Description|  
|------------------|-----------------|  
|IDM_VS_MENU_PROJECT|Menu de niveau supérieur du **projet** .|  
|IDM_VS_TOOL_PROJWIN|Barre d’outils **Explorateur de solutions** .|  
  
## <a name="shortcut-menus"></a>Menus contextuels  
 Le tableau suivant présente les menus contextuels qui s’appliquent lorsqu’un seul nœud est sélectionné dans le **Explorateur de solutions**, ou lorsqu’il y a plusieurs sélections homogènes dans le **Explorateur de solutions**, ce qui est le cas lorsque tous les nœuds sélectionnés sont du même type.  
  
|Menu contextuel|Description|  
|-------------------|-----------------|  
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_PROJNODE>|S’applique lorsque le nœud du projet est sélectionné.|  
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_ITEMNODE>|S’applique lorsqu’un fichier est sélectionné.|  
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_FOLDERNODE>|S’applique lorsqu’un dossier est sélectionné.|  
|IDM_VS_CTXT_WEBREFFOLDER|S’applique lorsque le dossier de référence Web est sélectionné.|  
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_REFERENCEROOT>|S’applique lorsque le nœud racine des références appelé « références » est sélectionné.|  
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_REFERENCE>|S’applique lorsque les nœuds de référence sont sélectionnés ; Cela inclut uniquement les références d’assembly, COM et de projet. N’inclut pas les références Web.|  
  
 Le tableau suivant répertorie les menus contextuels qui s’appliquent lorsque la sélection dans le **Explorateur de solutions** s’étend sur plusieurs hiérarchies.  
  
|Menu contextuel|Description|  
|-------------------|-----------------|  
|IDM_VS_CTXT_XPROJ_SLNPROJ|S’applique lorsque la sélection actuelle contient le nœud de la solution et les nœuds du projet racine.|  
|IDM_VS_CTXT_XPROJ_SLNITEM|S’applique lorsque la sélection actuelle contient le nœud de la solution et les éléments de projet.|  
|IDM_VS_CTXT_XPROJ_MULTIPROJ|S’applique lorsque la sélection actuelle se compose de plusieurs nœuds de projet racine uniquement.|  
|IDM_VS_CTXT_XPROJ_PROJITEM|S’applique lorsque la sélection actuelle contient une combinaison de nœuds de projet racine et d’éléments de projet. En outre, la sélection peut contenir le nœud de la solution.|  
|IDM_VS_CTXT_XPROJ_MULTIITEM|S’applique lorsque la sélection actuelle contient des éléments de projet de plusieurs projets de la solution, ou lorsque des éléments de différents types sont sélectionnés dans le même projet.|  
  
## <a name="command-groups"></a>Groupes de commandes  
 Le tableau suivant répertorie les groupes de commandes que vous pouvez utiliser lorsque vous étendez des projets, et que vous pouvez accéder via le <xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_PROJNODE> menu contextuel.  
  
|Groupe de commandes|Description|  
|-------------------|-----------------|  
|IDG_VS_CTXT_PROJECT_BUILD|Commandes pour la génération, la régénération et le déploiement du projet.|  
|IDG_VS_CTXT_COMPILELINK|Commandes pour la compilation et la liaison du projet.|  
|IDG_VS_CTXT_PROJECT_CONFIG|Commandes qui définissent la configuration du projet et l’ordre de génération.|  
|IDG_VS_CTXT_PROJECT_ADD|Commandes qui ajoutent des éléments au projet.|  
|IDG_VS_CTXT_PROJECT_START|Commandes qui définissent le projet de démarrage associé à la touche F5.|  
|IDG_VS_CTXT_PROJECT_SAVE|Commandes pour enregistrer les éléments de projet.|  
|IDG_VS_CTXT_PROJECT_DEBUG|Commandes pour le débogage.|  
|IDG_VS_CTXT_PROJECT_SCC|Commandes pour le contrôle de code source.|  
|IDG_VS_CTXT_PROJECT_TRANSFER|Commandes pour les opérations couper, copier et coller.|  
|IDG_VS_CTXT_PROJECT_PROPERTIES|Commandes qui permettent d’accéder à la boîte de dialogue **Propriétés du projet** .|  
  
## <a name="see-also"></a>Voir aussi  
 [Comment les VSPackages ajoutent des éléments d’interface utilisateur](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [MenuCommands et OleMenuCommands](../../misc/menucommands-vs-olemenucommands.md)   
 [Création de groupes de boutons réutilisables](../../extensibility/creating-reusable-groups-of-buttons.md)
