---
title: Utilisation du diagramme de définition DSL | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.diagram
- vs.dsltools.dsldesigner.dsldiagram
helpviewer_keywords:
- Domain-Specific Language Tools, diagram
- Domain-Specific Language Tools, Split Tree
- Domain-Specific Language Tools, Show Map Lines
- Domain-Specific Language Tools, Show As Class
- Domain-Specific Language Tools, Bring Tree Here
ms.assetid: 1a4c7a58-e134-438e-848e-efd98f92bf10
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 1fc0dbc007dcb3e15891a4176fc5bdb96babbfa8
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49208583"
---
# <a name="working-with-the-dsl-definition-diagram"></a>Utilisation du schéma de définition DSL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Le diagramme d’un [!INCLUDE[dsl](../includes/dsl-md.md)] définition est un outil important pour la définition de la langue spécifique à un domaine. Vous pouvez ajouter des éléments à votre modèle de domaine et définir des relations sur le diagramme ; vous pouvez également modifier la disposition du diagramme pour accroître sa lisibilité.  
  
## <a name="the-layout-of-the-diagram"></a>Disposition du diagramme  
 Le [!INCLUDE[dsl](../includes/dsl-md.md)] diagramme de définition a deux partitions, le **Classes et relations** partition et le **éléments de diagramme** partition. Le **Classes et relations** partition affiche les classes de domaine, les relations de domaine et l’héritage. Le **éléments de diagramme** partition affiche les classes de formes, classes de connecteur, les classes de couloir et le diagramme du concepteur généré.  
  
 Classes de domaine peuvent apparaître dans plusieurs emplacements dans le **Classes et relations** partitions. La définition d'une classe de domaine affiche une arborescence d'héritage si elle est la classe de base d'autres classes de domaine et une arborescence de relations si elle est la source des relations d'incorporation ou de référence. Les espaces réservés de classes de domaine apparaissent comme les cibles des relations d'incorporation ou de référence. Par défaut, les éléments de l’espace réservé sont affichés avec le **propriétés de domaine** compartiment réduite. Ils n'affichent ni l'héritage ni les relations d'incorporation ou de référence.  
  
 Lorsque vous ajoutez une classe de domaine, il apparaît dans la partie inférieure de la **Classes et relations** partition. Lorsque vous ajoutez une relation d'incorporation ou de référence, elle est tracée sous et à la droite de la classe de domaine source.  
  
 Au fur et à mesure que vous ajoutez des classes de domaine et des relations, la recherche d'une classe de domaine particulière peut se révéler difficile. Vous trouverez une classe de domaine en effectuant un clic droit dans le **Explorateur DSL** , puis en cliquant sur **rechercher dans le diagramme**.  
  
 Les sections suivantes expliquent comment vous pouvez modifier l'aspect du diagramme pour accroître sa lisibilité.  
  
## <a name="copying-elements"></a>Copie d'éléments  
 Vous pouvez copier, couper ou coller des éléments du diagramme de définition DSL.  
  
## <a name="zooming-in-or-out-on-the-diagram"></a>Zoom avant ou arrière sur le diagramme  
 Vous pouvez effectuer un zoom avant ou arrière sur le diagramme à l’aide de la **concepteur DSL** barre d’outils pour définir le niveau de zoom.  
  
## <a name="hiding-map-lines"></a>Masquage des lignes de correspondance  
 Les lignes de correspondance sont les lignes tracées entre une classe de domaine ou une relation de domaine et la forme ou le connecteur auquel elle est mappée. Vous pouvez masquer les lignes de carte en cliquant sur le **afficher les lignes de carte** bouton sur le **concepteur DSL** barre d’outils. Pour afficher les lignes, cliquez à nouveau sur le bouton.  
  
## <a name="changing-the-diagram-layout"></a>Modification de la disposition du diagramme  
 Vous pouvez modifier la disposition de la **Classes et relations** de partition comme suit.  
  
### <a name="expandcollapse"></a>Développer/Réduire  
 Vous pouvez réduire la taille d’un élément de forme de compartiment qui représente une classe de domaine ou d’une forme en double-cliquant sur elle et puis en cliquant sur **réduire**. Cela masque le **propriétés de domaine** compartiment de la forme. Pour afficher le **propriétés de domaine** compartiment à nouveau, avec le bouton droit de la forme, puis sur **Expand**.  
  
### <a name="move-updown"></a>Déplacer vers le haut ou vers le bas  
 Vous pouvez déplacer une classe ou un diagramme élément de domaine vers le haut ou vers le bas dans la partition en double-cliquant sur l’élément, puis sur **monter** ou **Descendre**. Si vous déplacez un élément d'espace réservé affiché comme la cible d'une relation d'incorporation ou de référence, la relation sera également déplacée.  
  
### <a name="expandcollapse-relationships-tree"></a>Développer/réduire l'arborescence des relations  
 Si une classe de domaine joue le rôle source dans les relations d’incorporation ou de référence avec d’autres classes de domaine, vous pouvez masquer les relations en double-cliquant sur la définition de classe de domaine, puis sur **réduire l’arborescence des relations**. Pour afficher les relations, avec le bouton droit de l’élément de définition, puis cliquez sur **développez l’arborescence des relations**.  
  
### <a name="expandcollapse-inheritance-tree"></a>Développer/réduire l'arborescence d'héritage  
 Si une classe de domaine est la classe de base d’autres classes de domaine, vous pouvez masquer l’arborescence d’héritage en double-cliquant sur la définition de classe de domaine, puis sur **réduire l’arborescence d’héritage**. Pour afficher l’arborescence d’héritage, avec le bouton droit de l’élément de définition, puis cliquez sur **développez l’arborescence d’héritage**.  
  
### <a name="bring-tree-here"></a>Bring Tree Here (action)  
 Vous pouvez consolider le diagramme en double-cliquant sur une classe de domaine d’espace réservé, puis sur **déplacer l’arborescence ici**. La classe de domaine de l'espace réservé devient un élément de définition et affiche les arborescences d'héritage et de relations. Le précédent élément de définition devient un élément d'espace réservé s'il est la cible d'une relation ou l'enfant d'une relation d'héritage ; dans le cas contraire, il disparaît.  
  
### <a name="split-tree"></a>Split Tree  
 Vous pouvez scinder les arborescences d’héritage ou de relations en double-cliquant sur la définition de classe de domaine qui les affiche, puis sur **fractionner l’arborescence**. L'élément de définition devient un élément d'espace réservé et la classe de domaine de la définition, ainsi que ses relations d'héritage et de relation, s'affiche désormais en bas de la partition.  
  
### <a name="show-as-class"></a>Show As Class  
 Si une relation de domaine possède des relations dérivées, ou si elle a des relations d’incorporation ou de référence avec d’autres relations de domaine, vous pouvez afficher la relation en tant que classe en double-cliquant sur la relation, puis sur **afficher en tant que la classe** . La relation s’affichera avec un **propriétés de domaine** de compartiments et affiche les relations d’héritage et.  
  
## <a name="see-also"></a>Voir aussi  
 [Glossaire des outils Domain-Specific Language](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



