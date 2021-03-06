---
title: Concepteur d’activités Concepteur de flux de travail-RemoveFromCollection &lt; T &gt;
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c8af0a0bf8bdf60c8ae9911ef0926cb9e395989a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "86875577"
---
# <a name="removefromcollectiont-activity-designer"></a>Concepteur d’activités RemoveFromCollection\<T>

Le concepteur d’activités ** \<T> RemoveFromCollection** permet de créer et de configurer une <xref:System.Activities.Statements.RemoveFromCollection%601> activité.

## <a name="the-removefromcollectiontactivity"></a>Activité RemoveFromCollection \<T>

L'activité <xref:System.Activities.Statements.RemoveFromCollection%601> supprime un élément spécifié d'une collection particulière.

### <a name="using-the-removefromcollectiont-activity-designer"></a>Utilisation du \<T> Concepteur d’activités RemoveFromCollection

Accédez au concepteur d’activités **RemoveFromCollection \<T> ** dans la catégorie **collection** de la **boîte à outils**.
Le concepteur d’activités **RemoveFromCollection \<T> ** peut être déplacé de la **boîte à outils** et déposé dans l’aire de concepteur de flux de travail, là où les activités sont généralement placées, par exemple dans un <xref:System.Activities.Statements.Sequence> . Une <xref:System.Activities.Statements.RemoveFromCollection%601> activité est créée avec la valeur par défaut <xref:System.Activities.Activity.DisplayName%2A> RemoveFromCollection<Int32 \> . La <xref:System.Activities.Activity.DisplayName%2A> valeur peut être modifiée dans l’en-tête du concepteur d’activités **RemoveFromCollection<T \> ** ou dans la zone **DisplayName** de la grille des propriétés. Les autres propriétés doivent être modifiées dans la grille des propriétés.

### <a name="the-removefromcollectiont-properties"></a>Propriétés de RemoveFromCollection<T \>

Le tableau suivant présente les <xref:System.Activities.Statements.RemoveFromCollection%601> Propriétés et décrit comment elles sont utilisées dans le concepteur :

|Nom de la propriété|Obligatoire|Usage|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|Faux|Nom convivial facultatif de l'activité <xref:System.Activities.Statements.RemoveFromCollection%601>. La valeur par défaut est RemoveFromCollection<Int32 \> .<br /><br /> Bien que la propriété <xref:System.Activities.Activity.DisplayName%2A> ne soit pas strictement obligatoire, il est recommandé d'en utiliser une.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|Vrai|Élément à supprimer de la **collection \<T> **. Cet élément est de type *T*, qui est de type *TypeArgument*. Pour spécifier l'élément, tapez une expression Visual Basic dans la grille des propriétés.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|Vrai|Collection à partir de laquelle l’élément doit être supprimé. Cette collection est de type **ICollection<TypeArgument \> .** Pour spécifier la collection, tapez une expression Visual Basic dans la grille des propriétés.|
|*TypeArgument*|Vrai|Type T des éléments contenus dans la collection <xref:System.Collections.Generic.ICollection%601>. Par défaut, ce type de *TypeArgument* est défini sur **Int32**. Pour modifier le type, modifiez la valeur de *TypeArgument* dans la zone de liste déroulante de la grille des propriétés.|
|<xref:System.Activities.Activity%601.Result%2A>|Faux|Valeur qui indique si l’élément spécifié a été supprimé de la collection. Pour spécifier une variable à lier au résultat, entrez une variable dans la grille des propriétés|

## <a name="see-also"></a>Voir aussi

- [Collection](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T>](../workflow-designer/clearcollection-t-activity-designer.md)
- [ExistsInCollection\<T>](../workflow-designer/existsincollection-t-activity-designer.md)