---
title: Gestionnaires de modification de la valeur de propriété de domaine | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, overriding event handlers
ms.assetid: 96d8f392-045e-4bc5-b165-fbaa470a3e16
caps.latest.revision: 25
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 69ebcc264eb3caa68fa0dfd2998613a7c9037b2e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72669771"
---
# <a name="domain-property-value-change-handlers"></a>Gestionnaire de modification de la valeur de propriété du domaine
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans un langage spécifique à un domaine [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], quand la valeur d'une propriété de domaine change, les méthodes `OnValueChanging()` et `OnValueChanged()` sont appelées dans le gestionnaire de propriétés de domaine. Pour répondre au changement, vous pouvez substituer ces méthodes.

## <a name="overriding-the-property-handler-methods"></a>Substitution des méthodes de gestionnaire de propriétés
 Chaque propriété de domaine de votre langage spécifique à un domaine est gérée par une classe imbriquée dans sa classe de domaine parente. Son nom suit le format *PropertyName*PropertyHandler. Vous pouvez inspecter cette classe de gestionnaire de propriétés dans le fichier **Dsl\Generated Code\DomainClasses.cs**. Dans la classe, `OnValueChanging()` est appelée juste avant que la valeur change et `OnValueChanged()` est appelée juste après que la valeur change.

 Par exemple, supposons que vous ayez une classe de domaine nommée `Comment` qui a une propriété de domaine de chaîne nommée `Text` et une propriété de type entier nommée `TextLengthCount` . Pour `TextLengthCount` que Always contienne toujours la longueur de la `Text` chaîne, vous pouvez écrire le code suivant dans un fichier distinct dans le projet DSL :

```
// Domain Class "Comment":
public partial class Comment
{
  // Domain Property "Text":
  partial class TextPropertyHandler
  {
    protected override void OnValueChanging(CommentBase element, string oldValue, string newValue)
    {
      base.OnValueChanging(element, oldValue, newValue);

      // To update values outside the Store, write code here.

      // Let the transaction manager handle undo:
      Store store = element.Store;
      if (store.InUndoRedoOrRollback || store.InSerializationTransaction) return;

      // Update values in the Store:
      this.TextLengthCount = newValue.Length;
    }
  }
}

```

 Notez les points suivants concernant les gestionnaires de propriétés :

- Les méthodes de gestionnaires de propriétés sont appelées à la fois quand l'utilisateur modifie une propriété de domaine et quand du code de programme assigne une valeur différente à la propriété.

- Les méthodes sont appelées uniquement quand la valeur change. Le gestionnaire n'est pas appelé si du code de programme assigne une valeur qui est égale à la valeur actuelle.

- Les propriétés de domaine de stockage personnalisées et calculées n'ont pas de méthodes OnValueChanged et OnValueChanging.

- Vous ne pouvez pas utiliser un gestionnaire de modification pour modifier la nouvelle valeur. Pour cela, par exemple si vous souhaitez restreindre la valeur à une plage spécifique, définissez une `ChangeRule`.

- Vous ne pouvez pas ajouter un gestionnaire de modification à une propriété qui représente un rôle d'une relation. Au lieu de cela, définissez une `AddRule` et une `DeleteRule` sur la classe de relation. Ces règles sont déclenchées quand les liens sont créés ou modifiés. Pour plus d’informations, consultez [règles de propagation des modifications dans le modèle](../modeling/rules-propagate-changes-within-the-model.md).

### <a name="changes-in-and-out-of-the-store"></a>Modifications dans le magasin
 Les méthodes de gestionnaires de propriétés sont appelées dans la transaction ayant initié la modification. Ainsi, vous pouvez apporter d'autres modifications dans le magasin sans ouvrir de nouvelle transaction. Vos modifications peuvent avoir comme conséquence des appels de gestionnaires supplémentaires.

 Quand une transaction est en cours d'annulation, de réexécution ou de restauration, vous ne devez pas modifier le magasin, c'est-à-dire ne pas modifier les éléments du modèle, relations, formes, connecteurs, diagrammes ou leurs propriétés.

 De plus, vous ne devez généralement pas mettre des valeurs à jour quand le modèle est en cours de chargement à partir du fichier.

 Les modifications apportées au modèle doivent donc être protégées par un test tel que celui-ci :

```
if (!store.InUndoRedoOrRollback
         && !store. InSerializationTransaction)
{ this.TextLength = ...; // in-store changes
}
```

 En revanche, si votre gestionnaire de propriétés propage les modifications en dehors du magasin, par exemple vers un fichier, une base de données ou des variables en dehors du magasin, vous devez toujours apporter ces modifications pour que les valeurs externes soient mises à jour quand l'utilisateur effectue une annulation ou un rétablissement.

### <a name="canceling-a-change"></a>Annulation d'une modification
 Si vous souhaitez empêcher une modification, vous pouvez rétablir la transaction actuelle. Vous pourriez par exemple souhaiter vous assurer qu'une propriété demeure dans une plage spécifique.

```
if (newValue > 10)
{ store.TransactionManager.CurrentTransaction.Rollback();
  System.Windows.Forms.MessageBox.Show("Value must be less than 10");
}

```

### <a name="alternative-technique-calculated-properties"></a>Autre technique : propriétés calculées
 L'exemple précédent montre comment OnValueChanged() peut être utilisée pour propager des valeurs d'une propriété de domaine à une autre. Chaque propriété a sa propre valeur stockée.

 Au lieu de cela, vous pourriez définir la propriété dérivée en tant que propriété calculée. Dans ce cas, la propriété n'a aucun stockage propre et sa fonction de définition est évaluée chaque fois que sa valeur est nécessaire. Pour plus d’informations, consultez [Propriétés de stockage calculées et personnalisées](../modeling/calculated-and-custom-storage-properties.md).

 Au lieu de l’exemple précédent, vous pouvez définir le champ **Kind** de `TextLengthCount` à **calculer** dans la définition DSL. Vous devez fournir votre propre méthode d' **extraction** pour cette propriété de domaine. La méthode **obtenir** retourne la longueur actuelle de la `Text` chaîne.

 Toutefois, l'un des inconvénients potentiels des propriétés calculées est que l'expression est évaluée chaque fois que la valeur est utilisée, ce qui pourrait poser un problème de performance. De plus, il n'existe aucune méthode OnValueChanging() et OnValueChanged() sur une propriété calculée.

### <a name="alternative-technique-change-rules"></a>Autre technique : modifier les règles
 Si vous définissez une ChangeRule, elle est exécutée à la fin d'une transaction dans laquelle la valeur d'une propriété change.  Pour plus d’informations, consultez [règles de propagation des modifications dans le modèle](../modeling/rules-propagate-changes-within-the-model.md).

 Si plusieurs modifications sont apportées dans une même transaction, la ChangeRule s'exécute quand elles sont toutes terminées. En revanche, le OnValue... les méthodes sont exécutées lorsque certaines modifications n’ont pas été effectuées. Selon le résultat souhaité, une ChangeRule pourrait être plus appropriée.

 Vous pouvez aussi utiliser une ChangeRule pour ajuster la nouvelle valeur de la propriété pour qu'elle demeure dans une page spécifique.

> [!WARNING]
> Si une règle modifie le contenu du magasin, d'autres règles et gestionnaires de propriétés peuvent être déclenchés. Si une règle modifie la propriété qui l'a déclenchée, elle est de nouveau appelée. Vous devez vous assurer que vos définitions de règles ne provoquent pas un déclenchement sans fin.

```
using Microsoft.VisualStudio.Modeling;
...
// Change rule on the domain class Comment:
[RuleOn(typeof(Comment), FireTime = TimeToFire.TopLevelCommit)]
class MyCommentTrimRule : ChangeRule
{
  public override void
    ElementPropertyChanged(ElementPropertyChangedEventArgs e)
  {
    base.ElementPropertyChanged(e);
    Comment comment = e.ModelElement as Comment;

    if (comment.Text.StartsWith(" ") || comment.Text.EndsWith(" "))
      comment.Text = comment.Text.Trim();
    // If changed, rule will trigger again.
  }
}

// Register the rule:
public partial class MyDomainModel
{
 protected override Type[] GetCustomDomainModelTypes()
 { return new Type[] { typeof(MyCommentTrimRule) };
 }
}

```

## <a name="example"></a>Exemple

### <a name="description"></a>Description
 L'exemple suivant substitue le gestionnaire de propriétés d'une propriété de domaine et informe l'utilisateur quand une propriété pour la classe de domaine `ExampleElement` a changé.

### <a name="code"></a>Code

```
using DslModeling = global::Microsoft.VisualStudio.Modeling;
using DslDesign = global::Microsoft.VisualStudio.Modeling.Design;

namespace msft.FieldChangeSample
{
  public partial class ExampleElement
  {
    internal sealed partial class NamePropertyHandler
    {
      protected override void OnValueChanged(ExampleElement element,
         string oldValue, string newValue)
      {
        if (!this.Store.InUndoRedoOrRollback)
        {
           // make in-store changes here...
        }
        // This part is called even in undo:
        System.Windows.Forms.MessageBox.Show("Value Has Changed");
        base.OnValueChanged(element, oldValue, newValue);
      }
    }
  }
}
```
