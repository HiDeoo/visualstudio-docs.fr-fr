---
title: Programmation à l’aide de l’API UML | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML model, API
- UML model, extending
ms.assetid: c5937139-49d0-4439-8a9f-89f5e0474618
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bdf1111198c7f874d03596382372fe25851e37d3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75852134"
---
# <a name="programming-with-the-uml-api"></a>Programmation à l'aide de l'API UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

L'API UML de Visual Studio vous permet d'écrire du code pour créer, lire et mettre à jour des modèles et diagrammes UML. Pour connaître les versions de Visual Studio qui prennent en charge les modèles UML, consultez [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

 Outre les pages de référence de l'API, les rubriques suivantes décrivent l'API.

|Rubrique|Exemples de types et méthodes décrits|Fonctionnalités décrites|
|-----------|-----------------------------------------|------------------------|
|[Naviguer parmi les relations avec l'API UML](../modeling/navigate-relationships-with-the-uml-api.md)|Éléments UML et leurs propriétés et associations. Par exemple, IElement et ses descendants, notamment : IClass, IActivity, IUseCase, IComponent, IInteraction, IModel, IPackage|Dans Visual Studio, les modèles UML sont conformes à la spécification UML version 2.1.2, qui peut être obtenue à partir de la [page de ressources UML](https://www.uml.org/). Chaque type est une interface qui porte le même nom que le type UML, avec un préfixe « I ».|
|[Créer des éléments et des relations dans des modèles UML](../modeling/create-elements-and-relationships-in-uml-models.md)|IPackage.CreateClass()<br /><br /> IClass.CreateOperation()|Chaque type d'élément comporte des méthodes pour la création de ses enfants.|
|[Afficher un modèle UML sur des diagrammes](../modeling/display-a-uml-model-on-diagrams.md)|IShape, IDiagram<br /><br /> IShape.Move()|Chaque élément inclus dans un modèle peut être représenté par une forme dans un diagramme. Dans certains cas, vous pouvez créer des formes pour chaque objet. Vous pouvez déplacer, redimensionner, colorer, réduire ou développer ces formes.|
|[Naviguer dans le modèle UML](../modeling/navigate-the-uml-model.md)|IModelStore<br /><br /> IDiagramContext|Le magasin de modèles stocke le modèle.<br /><br /> Le contexte du diagramme vous donne accès au diagramme et au magasin actuels.|
|[Lier des mises à jour de modèles UML à l’aide de transactions](../modeling/link-uml-model-updates-by-using-transactions.md)|ILinkedUndoContext|Vous pouvez lier une série de modifications dans une seule transaction.|
|[Définir une commande de menu sur un diagramme de modélisation](../modeling/define-a-menu-command-on-a-modeling-diagram.md)|IMenuCommand<br /><br /> IGestureExtension<br /><br /> ICommandExtension|Vous pouvez étendre les fonctionnalités d'un diagramme en définissant des commandes appelées en double-cliquant dessus et en les faisant glisser sur le diagramme.|
|[Définir des contraintes de validation pour les modèles UML](../modeling/define-validation-constraints-for-uml-models.md)|ValidationContext|Vous pouvez définir des règles de validation pour veiller à ce qu'un modèle soit conforme aux contraintes spécifiées.|
|[Obtenir des éléments de modèle UML à partir de l'interface IDataObject](../modeling/get-uml-model-elements-from-idataobject.md)|IElement, IShape|Quand un élément est déplacé à partir de l'Explorateur de modèles UML ou d'un diagramme UML vers un autre diagramme ou une autre application, il est sérialisé en tant qu'interface IDataObject.|
|[Modifier des diagrammes de séquence à l’aide de l’API UML](../modeling/edit-uml-sequence-diagrams-by-using-the-uml-api.md)|IInteraction, ILifeline, IMessage|La création et la mise à jour d'un diagramme d'interaction diffèrent légèrement de l'utilisation des autres types de diagramme.|
|[Étendre des diagrammes de couche](../modeling/extend-layer-diagrams.md)|ILayer, ILayerDiagram|Vous pouvez écrire du code pour créer et modifier des diagrammes de couche, mais aussi valider du code de programme en fonction d'eux.|

## <a name="about-the-implementation"></a>À propos de l'implémentation
 Les outils de modélisation UML s'appuient sur [!INCLUDE[dsl](../includes/dsl-md.md)]. Chaque package et chaque diagramme sont représentés par un modèle [!INCLUDE[dsl](../includes/dsl-md.md)]. Une collection de règles et d'autres méthodes maintiennent la cohérence entre eux.

 Les types de cette plateforme sont visibles dans certains assemblys que vous référencez pour écrire des extensions UML. Bien que vous puissiez créer des extensions aux outils UML en accédant à l'API [!INCLUDE[dsl](../includes/dsl-md.md)], vous devez garder les considérations suivantes à l'esprit :

- Vous constaterez peut-être que certaines modifications en apparence simples introduisent des incohérences et des effets inattendus.

- L'implémentation est sujette à de futures modifications, si bien que les adaptations que vous apportez à l'aide de l'API [!INCLUDE[dsl](../includes/dsl-md.md)] risquent de ne plus fonctionner.

## <a name="the-api-assemblies"></a>Assemblys de l'API
 Ce tableau récapitule les assemblys qui offrent une extensibilité des outils UML, ainsi que les espaces de noms dont l'utilisation est recommandée.

|Assembly|Espaces de noms|Fournit l'accès à :|
|--------------|----------------|-------------------------|
|Microsoft.VisualStudio.Uml.Interfaces|(Tout)|Types UML.|
|Microsoft.VisualStudio.ArchitectureTools.Extensibility|Microsoft. VisualStudio. ArchitectureTools. Extensibility. Uml|[Méthodes de création](../modeling/create-elements-and-relationships-in-uml-models.md)|
||Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation|[Diagrammes et formes](../modeling/display-a-uml-model-on-diagrams.md)|
||Microsoft.VisualStudio.ArchitectureTools.Extensibility|[Projet de modélisation](../modeling/read-a-uml-model-in-program-code.md)|
|Microsoft.VisualStudio.Modeling.Sdk.[version]|<xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement>|[Extension de commande de menu](../modeling/define-a-menu-command-on-a-modeling-diagram.md).<br /><br /> [Transactions d’annulation liées](../modeling/link-uml-model-updates-by-using-transactions.md).|
||<xref:Microsoft.VisualStudio.Modeling.Validation>|[Validation](../modeling/define-validation-constraints-for-uml-models.md)|
||(autres espaces de noms)|Recommandé uniquement pour l'utilisation avancée.|
|Microsoft.VisualStudio.Modeling.Sdk.Diagrams.[version]|<xref:Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement>|[Gestionnaires de mouvements](../modeling/define-a-gesture-handler-on-a-modeling-diagram.md).|
||(autres espaces de noms)|Recommandé uniquement pour l'utilisation avancée.|
|Microsoft.VisualStudio.TeamFoundation.WorkItemTracking|Microsoft.VisualStudio.TeamFoundation.WorkItemTracking|[Liens vers les éléments de travail](../modeling/define-a-work-item-link-handler.md).|
|Microsoft.TeamFoundation.WorkItemTracking.Client|Microsoft.TeamFoundation.WorkItemTracking.Client|[Éléments de travail et leurs champs](../modeling/define-a-work-item-link-handler.md).|
|Microsoft.TeamFoundation.Client|Microsoft.TeamFoundation.Client|[Éléments de travail et leurs champs](../modeling/define-a-work-item-link-handler.md).|
|System.ComponentModel.Composition|<xref:System.ComponentModel.Composition>|[Exporter et importer des composants MEF](../modeling/define-and-install-a-modeling-extension.md)|
|System.Linq|<xref:System.Linq>|[Manipulation facile des collections, en particulier lors du traitement des relations](../modeling/navigate-relationships-with-the-uml-api.md).|

## <a name="see-also"></a>Voir aussi
 [Étendre les modèles et diagrammes UML](../modeling/extend-uml-models-and-diagrams.md) [référence des API pour l’extensibilité de la modélisation UML](../modeling/api-reference-for-uml-modeling-extensibility.md)
