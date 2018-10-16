---
title: Concepteur d’activités flowchart | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Flowchart.UI
- System.Activities.Statements.FlowStep.UI
- System.Activities.Core.Presentation.FlowStart.UI
ms.assetid: d5af2276-5215-4138-880a-cf2b90bbf3a0
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 67bebeec9c2d88ba1912bc50b27e38f8278e7e3f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49226237"
---
# <a name="flowchart-activity-designer"></a>Concepteur d'activités d'organigramme
L'activité <xref:System.Activities.Statements.Flowchart> permet de créer des flux de travail qui définissent et gèrent des contrôles de flux complexes. <xref:System.Activities.Statements.Flowchart> peut être créé dans le code ou à l'aide de [!INCLUDE[wfd2](../includes/wfd2-md.md)]. Cette rubrique explique comment utiliser [!INCLUDE[wfd2](../includes/wfd2-md.md)]. Le concepteur d'activités de flux de travail [!INCLUDE[wfd1](../includes/wfd1-md.md)] permet aux développeurs de créer des flux de travail de façon naturelle.  
  
## <a name="the-flowchart-activity"></a>Activité Flowchart  
 <xref:System.Activities.Statements.Flowchart> spécifie une propriété <xref:System.Activities.Statements.Flowchart.StartNode%2A> unique exécutée lorsque le flux de travail démarre et utilise un réseau de propriétés <xref:System.Activities.Statements.Flowchart.Nodes%2A> liées pour créer des boucles arbitraires ou détourner le flux d'exécution ailleurs dans le flux de travail à un moment donné.  
  
### <a name="using-the-flowchart-activity-designer"></a>Utilisation du concepteur d'activités Flowchart  
 Le **organigramme** Concepteur d’activités peut être trouvé dans le **organigramme** catégorie de la **boîte à outils**, qui est accessible en cliquant sur le **boîte à outils**onglet sur le [!INCLUDE[wfd2](../includes/wfd2-md.md)] (ou bien, sélectionnez **barre d’outils** à partir de la **vue** menu ou CTRL + ALT + X.)  
  
 Le **organigramme** Concepteur d’activités peut être déplacé de la **boîte à outils** et déposé dans le [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface, là où concepteurs d’activités sont généralement placés, sous la forme d’une activité racine ou l’enfant d’une autre activité de flux de contrôle. Si le **organigramme** Concepteur d’activités est déposé sur une valeur vide [!INCLUDE[wfd2](../includes/wfd2-md.md)] aire de conception, il crée un <xref:System.Activities.Statements.Flowchart> activité, qui se présente dans une vue développée dans lequel est le nœud de départ qui lance l’exécution par défaut représenté sous la forme d’une boule verte. Si le **organigramme** Concepteur d’activités est déposé dans une autre activité de flux de contrôle, il s’affiche dans une vue réduite qui peut être développée en double-cliquant sur le **organigramme** Concepteur d’activités. Toutes les activités dans le **boîte à outils** peut être déplacé directement sur le **organigramme** Concepteur d’activités, y compris les autres activités de flux de contrôle.  
  
 Après avoir fait glisser différents concepteurs d'activités sur la zone de dessin de [!INCLUDE[wfd2](../includes/wfd2-md.md)], les objets <xref:System.Activities.Activity> qu'ils représentent peuvent être liés pour spécifier l'ordre d'exécution. Pour créer un lien entre une activité source et une activité de destination, pointez la souris sur le concepteur de l'activité source pour faire apparaître des poignées carrées sur chacun de ses côtés. Cliquez sur l'une des poignées carrées et faites-la glisser, en maintenant le bouton de la souris enfoncé, vers l'une des poignées qui s'affiche de manière similaire autour de l'activité de destination lorsque vous pointez dessus avec la souris. Relâchez le bouton de la souris, un lien est créé entre ces deux activités, représenté par une flèche du concepteur source au concepteur de destination.  
  
### <a name="flowchart-activity-properties"></a>Propriétés de l'activité Flowchart  
 Le tableau suivant présente les propriétés de <xref:System.Activities.Statements.Flowchart> et décrit comment elles sont utilisées dans le concepteur. Ces propriétés peuvent être modifiées dans la grille des propriétés ou dans l'aire du concepteur.  
  
|Nom de la propriété|Obligatoire|Utilisation|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Spécifie le nom d'affichage du concepteur d'activités dans l'en-tête. La valeur par défaut est Flowchart. La valeur peut être modifiée dans le **propriétés** fenêtre ou directement sur l’en-tête du Concepteur d’activité.<br /><br /> Bien que la propriété <xref:System.Activities.Activity.DisplayName%2A> ne soit pas strictement obligatoire, il est recommandé d'en utiliser une.|  
|<xref:System.Activities.Statements.Flowchart.Variables%2A>|False|Collection de variables dont l'étendue est limitée par cet objet <xref:System.Activities.Statements.Flowchart> pour partager l'état entre ses activités enfants.|  
|<xref:System.Activities.Statements.Flowchart.StartNode%2A>|False|Objet <xref:System.Activities.Statements.FlowNode> exécuté lorsque <xref:System.Activities.Statements.Flowchart> démarre.|  
|<xref:System.Activities.Statements.Flowchart.Nodes%2A>|False|Contient la collection d’objets <xref:System.Activities.Statements.FlowNode> dans <xref:System.Activities.Statements.Flowchart>.|  
  
## <a name="see-also"></a>Voir aussi  
 [Diagramme de flux](../workflow-designer/flowchart-activity-designers.md)   
 [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)   
 [FlowSwitch\<T >](../workflow-designer/flowswitch-t-activity-designer.md)