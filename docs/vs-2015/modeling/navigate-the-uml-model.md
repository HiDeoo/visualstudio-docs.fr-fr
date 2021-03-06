---
title: Naviguer dans le modèle UML | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML API
ms.assetid: 6d789b6d-2aa9-4ceb-92c4-84a300065a76
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 23f87c81e43b2dfafb1c9c78c3135faff809bb9f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "74289851"
---
# <a name="navigate-the-uml-model"></a>Naviguer dans le modèle UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette rubrique présente les principaux types du modèle UML.

## <a name="the-model-elements-model-and-model-store"></a>Les éléments de modèle, le modèle et le magasin de modèles
 Les types définis dans l’assembly **Microsoft.VisualStudio.Uml.Interfaces.dll** correspondent aux types définis dans la [spécification UML, version 2.1.2](https://www.omg.org/spec/UML/2.1.2/Superstructure/PDF/).

 Les types de la spécification UML sont réalisés en tant qu'interfaces dans Visual Studio. La lettre « I » est ajoutée devant le nom de chaque type. Par exemple : [IElement](/previous-versions/dd516035(v=vs.140)), [IClass](/previous-versions/dd523539%28v%3dvs.140%29), [IOperation](/previous-versions/dd481186(v=vs.140)).

 Tous les types sauf IElement héritent des propriétés d'un ou plusieurs supertypes.

- Pour obtenir un résumé des types de modèles, consultez [types d’éléments de modèle UML](../modeling/uml-model-element-types.md).

- Pour obtenir des informations complètes sur l’API, consultez [référence des API pour l’extensibilité de la modélisation UML](../modeling/api-reference-for-uml-modeling-extensibility.md).

### <a name="relationships"></a>Relations
 Les propriétés et relations définies dans la spécification UML sont implémentées en tant que propriétés .NET.

 La plupart des relations sont explorables dans les deux sens. Une relation correspond à une paire de propriétés, avec une propriété sur le type à chaque extrémité. Par exemple, les propriétés `IElement.Owner` et `IElement.OwnedElements` représentent deux extrémités d'une relation. Par exemple, cette expression sera toujours évaluée comme true :

 `IElement c; ...  c.OwnedElements.All(x => x.Owner == c)`

 De nombreuses relations, telles qu'IAssociation, sont également représentées par un objet qui peut avoir ses propres propriétés.

 Si vous supprimez un élément du modèle, toute relation à laquelle il participe est supprimée automatiquement et la propriété à l'autre extrémité est mise à jour.

 Si la spécification UML assigne une multiplicité de 0..1 à une propriété, elle peut avoir la valeur `null`. Une multiplicité avec un maximum supérieur à 1 signifie que la propriété .NET a le type : `IEnumerable<` *type* `>` .

 Pour plus d’informations sur le parcours des relations, consultez [Parcourir les relations avec l’API UML](../modeling/navigate-relationships-with-the-uml-api.md).

### <a name="the-ownership-tree"></a>Arborescence de propriété
 Un modèle contient une arborescence d’objets [IElement](/previous-versions/dd516035(v=vs.140)) . Chaque élément a des propriétés `OwnedElements` et `Owner`.

 Dans la plupart des cas, les cibles des propriétés `Owner` et `OwnedElements` sont également référencées par d'autres propriétés qui ont des noms plus spécifiques. Par exemple, chaque opération UML appartient à une classe UML. Par conséquent, [IOperation](/previous-versions/dd481186(v=vs.140)) a une propriété nommée [IOperation. Class](/previous-versions/dd473473%28v%3dvs.140%29)et, dans chaque objet [IOperation](/previous-versions/dd481186(v=vs.140)) , `Class == Owner` .

 L’élément le plus haut de l’arborescence, qui n’a pas de propriétaire, est un `AuxiliaryConstructs.IModel` . Le IModel est contenu dans un `IModelStore` , dans lequel il est [IModelStore. root](/previous-versions/ee789368(v=vs.140)).

 Chaque élément de modèle est créé avec un propriétaire. Pour plus d’informations, consultez [créer des éléments et des relations dans des modèles UML](../modeling/create-elements-and-relationships-in-uml-models.md).

 ![Diagramme de classes : modèle, diagramme, forme et élément](../modeling/media/uml-mm1.png)

## <a name="shapes-and-diagrams"></a>Formes et diagrammes
 Les éléments du modèle UML peuvent être illustrés sur des diagrammes. Différents types de diagrammes peuvent afficher différents sous-types d'IElement.

 Dans certains cas, un élément peut apparaître sur plusieurs diagrammes. Par exemple, un élément IUseCase peut avoir plusieurs IShapes, qui peuvent apparaître sur un ou différents diagrammes.

 Les formes sont organisées dans une arborescence. Les bords de l'arborescence sont représentés par les propriétés ParentShape et ChildShapes. Les diagrammes sont les seules formes qui n'ont pas de parents. Les formes sur la surface d'un diagramme sont composées de plus petites parties. Par exemple, une forme de classe a des compartiments pour des attributs et des opérations.

 Pour plus d’informations sur les formes, consultez [afficher un modèle UML sur des diagrammes](../modeling/display-a-uml-model-on-diagrams.md).

## <a name="access-to-the-model-in-extensions"></a>Accès au modèle dans des extensions
 Dans les extensions [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] définies comme composants MEF, vous pouvez déclarer des propriétés qui importent les informations à partir du contexte dans lequel l'extension s'exécute.

|Type d'attribut|Fournit l'accès à|Informations complémentaires|
|--------------------|----------------------------------|----------------------|
|Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation<br /><br /> IDiagramContext<br /><br /> (dans Microsoft.VisualStudio.ArchitectureTools.Extensibility.dll)|Diagramme de focus actuel.|[Définir une commande de menu sur un diagramme de modélisation](../modeling/define-a-menu-command-on-a-modeling-diagram.md)|
|Microsoft.VisualStudio.Modeling.ExtensionEnablement<br /><br /> ILinkedUndoContext<br /><br /> (dans Microsoft.VisualStudio.Modeling.Sdk.[version].dll)|Permet de regrouper des modifications dans des transactions.|[Lier des mises à jour de modèles UML à l’aide de transactions](../modeling/link-uml-model-updates-by-using-transactions.md)|
|Microsoft.VisualStudio.Shell .SVsServiceProvider<br /><br /> (dans Microsoft.VisualStudio.Shell.Immutable.[version].dll)|Hôte [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. À partir de là, vous pouvez accéder à des fichiers, des projets et d'autres aspects.|[Ouvrir un modèle UML à l'aide de l'API Visual Studio](../modeling/open-a-uml-model-by-using-the-visual-studio-api.md)|

### <a name="to-get-the-context"></a>Pour obtenir le contexte
 Déclarez l'une des interfaces suivantes, ou les deux, à l'intérieur de votre classe d'extension :

```
[Import] public IDiagramContext DiagramContext { get; set; }

```

 Managed Extensibility Framework (MEF) les liera à des définitions à partir desquelles vous pourrez obtenir le diagramme, le magasin de modèles et l'objet racine actuels, et ainsi de suite :

```
IDiagram diagram = this.DiagramContext.CurrentDiagram;
IClassDiagram classDiagram = diagram as IClassDiagram;
       // or diagrams of other types
IModelStore modelStore = diagram.ModelStore;
IModel model = modelStore.Root;
foreach (IDiagram diagram in modelStore.Diagrams) {...}
foreach (IElement element in modelStore.AllInstances<IUseCase>) {...}
```

### <a name="to-get-the-current-selection"></a>Pour obtenir la sélection actuelle

```
// All selected shapes and their elements
foreach (IShape shape in diagram.SelectedShapes)
{
   IDiagram selectedDiagram = shape as IDiagram;
   if (selectedDiagram != null)
   { // no shape selected - user right-clicked the diagram
     ... Context.CurrentDiagram ...
   }
   else
   {
     IElement selectedElement = shape.Element;
   ...}
// All selected shapes that display a specfic type of element
foreach (IShape<IInterface> in
   diagram.GetSelectedShapes<IInterface>())
{...}
```

## <a name="accessing-another-model-or-diagrams"></a>Accès à un autre modèle ou à d'autres diagrammes
 Vous pouvez :

- utiliser [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Model Bus pour créer des liens entre des éléments dans différents modèles. Pour plus d’informations, consultez [intégrer des modèles UML à d’autres modèles et outils](../modeling/integrate-uml-models-with-other-models-and-tools.md).

- charger un projet de modélisation et des diagrammes en mode lecture seule sans les rendre visibles dans l'interface utilisateur de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Pour plus d’informations, consultez [lire un modèle UML dans le code de programme](../modeling/read-a-uml-model-in-program-code.md).

- ouvrir un projet de modélisation et ses diagrammes dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], puis accéder au contenu. Pour plus d’informations, consultez [ouvrir un modèle UML à l’aide de l’API Visual Studio](../modeling/open-a-uml-model-by-using-the-visual-studio-api.md).

## <a name="see-also"></a>Voir aussi

- [Étendre des diagrammes et des modèles UML](../modeling/extend-uml-models-and-diagrams.md)
- [Programmation avec l’API UML](../modeling/programming-with-the-uml-api.md)
