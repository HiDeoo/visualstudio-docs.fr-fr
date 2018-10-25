---
title: Concepteur d’activités InvokeMethod | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.InvokeMethod.UI
ms.assetid: 15e6efdc-52ca-46d8-9c5e-063f7c8265a6
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: a3fa1c07bbb32bc1da963a0d2f0a91ae6c193a30
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49863683"
---
# <a name="invokemethod-activity-designer"></a>Concepteur d'activités InvokeMethod
**InvokeMethod** concepteur est utilisé pour créer et configurer un <xref:System.Activities.Statements.InvokeMethod> activité.  
  
## <a name="the-invokemethod-activity"></a>Activité InvokeMethod  
 <xref:System.Activities.Statements.InvokeMethod> appelle une méthode publique d'un objet ou d'un type spécifié.  
  
### <a name="using-the-invokemethod-activity-designer"></a>Utilisation du concepteur d'activités InvokeMethod  
 Le **InvokeMethod** Concepteur d’activités peut être trouvé dans le **Primitives** catégorie de la **boîte à outils**, qui est accessible en cliquant sur le **boîte à outils** onglet [!INCLUDE[wfd2](../includes/wfd2-md.md)] (ou bien, sélectionnez **barre d’outils** à partir de la **vue** menu ou CTRL + ALT + X.)  
  
 Le **InvokeMethod** Concepteur d’activités peut être déplacé de la **boîte à outils** et déposé dans le [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface là où les activités sont généralement placées, par exemple dans un <xref:System.Activities.Statements.Sequence>. Cette opération crée une activité <xref:System.Activities.Statements.InvokeMethod> avec une propriété <xref:System.Activities.Activity.DisplayName%2A> affectée de la valeur par défaut InvokeMethod. Le <xref:System.Activities.Activity.DisplayName%2A> peuvent être modifiées dans l’en-tête de la **InvokeMethod** Concepteur d’activités ou dans le **DisplayName** case de la grille des propriétés.  
  
### <a name="the-invokemethod-properties"></a>Propriétés d'InvokeMethod  
 Le tableau suivant présente les propriétés de <xref:System.Activities.Statements.InvokeMethod> et décrit comment elles sont utilisées dans le concepteur. Ces propriétés peuvent être modifiées dans la grille des propriétés et certaines peuvent être modifiés dans l'aire de conception [!INCLUDE[wfd2](../includes/wfd2-md.md)].  
  
|Nom de la propriété|Obligatoire|Utilisation|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Nom convivial de l'activité <xref:System.Activities.Statements.InvokeMethod>. La valeur par défaut est InvokeMethod.<br /><br /> Bien que la propriété <xref:System.Activities.Activity.DisplayName%2A> ne soit pas strictement obligatoire, il est recommandé d'en utiliser une.|  
|<xref:System.Activities.Statements.InvokeMethod.MethodName%2A>|True|Nom de la méthode à appeler lorsque l'activité s'exécute. La méthode appelée doit être déclarée en tant que **public**. Cette propriété peut être modifiée dans l'aire du concepteur. Il s'agit d'une propriété obligatoire.|  
|<xref:System.Activities.Statements.InvokeMethod.Parameters%2A>|False|Collection de paramètres de la méthode appelée. Les paramètres doivent être ajoutés à la collection selon leur ordre d’affichage dans la signature de méthode. Dans la grille des propriétés, cliquez sur le bouton de sélection dans le **paramètres** champ, il affiche le **paramètres** boîte de dialogue pour vous permettre de définir cette propriété. Cliquez sur le **créer un Argument** pour ajouter les paramètres.|  
|<xref:System.Activities.Statements.InvokeMethod.Result%2A>|False|Valeur de retour de l'appel de méthode.|  
|<xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A>|True|Spécifie si la méthode est appelée de façon asynchrone. La valeur par défaut est **False**.|  
|<xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>|False|Objet qui contient la méthode à appeler. Cette propriété peut être modifiée dans l'aire du concepteur.<br /><br /> La propriété <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> ou <xref:System.Activities.Statements.InvokeMethod.TargetType%2A> doit obligatoirement être définie.|  
|<xref:System.Activities.Statements.InvokeMethod.TargetType%2A>|False|Type d'élément <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>. Cette propriété peut être modifiée dans l'aire du concepteur. Elle doit être définie uniquement si la méthode appelée est statique.|  
  
 Pour passer des paramètres en tant que C# **out** paramètre (par exemple, `Method1(out myParam)),` vous devez utiliser **OutArgument** au lieu de **InOutArgument**  
  
 Méthodes comportant des arguments appelés **TargetObject** ou **résultat** ne peut pas être appelé à l’aide de la <xref:System.Activities.Statements.InvokeMethod> activité. En effet, l'activité <xref:System.Activities.Statements.InvokeMethod> inscrit <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A>, <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> et <xref:System.Activities.Statements.InvokeMethod.Result%2A> dans <xref:System.Activities.Activity.CacheMetadata%2A>.  
  
 L'algorithme permettant d'inscrire les paramètres dans <xref:System.Activities.Activity.CacheMetadata%2A> est présenté dans la liste suivante :  
  
1. Inscrivez l'argument <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>.  
  
2. Inscrivez l'argument <xref:System.Activities.Statements.InvokeMethod.Result%2A>.  
  
3. Effectuez une itération au sein de la collection <xref:System.Activities.Statements.InvokeMethod.Parameters%2A> et inscrivez chaque argument.  
  
   L'exception obtenue est de type <xref:System.Activities.InvalidWorkflowException> avec le message suivant : 'InvokeMethod' : Une variable, un RuntimeArgument ou un DelegateArgument, portant le nom 'TargetObject' existe déjà. Les noms doivent être uniques au sein de la portée de l'environnement.  
  
   Cette restriction ne s’applique pas à <xref:System.Activities.Statements.InvokeMethod.TargetType%2A> et <xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A>, car il ne s’agit pas d’arguments de flux de travail et ils ne sont donc pas inscrits dans la collection <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A> de l’activité <xref:System.Activities.Statements.InvokeMethod> dans méthode <xref:System.Activities.Activity.CacheMetadata%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Primitives](../workflow-designer/primitives-activity-designers.md)   
 [Affecter](../workflow-designer/assign-activity-designer.md)   
 [Délai](../workflow-designer/delay-activity-designer.md)   
 [WriteLine](../workflow-designer/writeline-activity-designer.md)