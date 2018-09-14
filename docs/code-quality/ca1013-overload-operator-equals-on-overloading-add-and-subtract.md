---
title: "CA1013 : Surchargez l'opérateur égal lors de la surcharge de l'opérateur d'addition et de soustraction"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
helpviewer_keywords:
- OverrideOperatorEqualsOnOverloadingAddAndSubtract
- OverrideOperatorEqualsOnOverridingAddAndSubtract
- CA1013
- OverloadOperatorEqualsOnOverloadingAddAndSubtract
ms.assetid: 5bd28d68-c179-49ff-af47-5250b8b18a10
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e8f0f3d40ea24828430983efd2cf39f4fa399238
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45547722"
---
# <a name="ca1013-overload-operator-equals-on-overloading-add-and-subtract"></a>CA1013 : Surchargez l'opérateur égal lors de la surcharge de l'opérateur d'addition et de soustraction

|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverloadingAddAndSubtract|
|CheckId|CA1013|
|Category|Microsoft.Design|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Un type public ou protégé implémente les opérateurs d'addition ou de soustraction sans implémenter l'opérateur d'égalité.

## <a name="rule-description"></a>Description de la règle
 Lorsque les instances d’un type peuvent être combinées à l’aide des opérations telles que l’addition et la soustraction, vous devez presque toujours définir l’égalité pour retourner `true` pour les deux instances qui ont les mêmes valeurs qui le composent.

 Vous ne pouvez pas utiliser l’opérateur d’égalité par défaut dans une implémentation surchargée de l’opérateur d’égalité. Cela provoque un dépassement de capacité de pile. Pour implémenter l’opérateur d’égalité, utilisez la méthode Object.Equals dans votre implémentation. Lisez l'exemple suivant.

```vb
If (Object.ReferenceEquals(left, Nothing)) Then
    Return Object.ReferenceEquals(right, Nothing)
Else
    Return left.Equals(right)
End If
```

```csharp
if (Object.ReferenceEquals(left, null))
    return Object.ReferenceEquals(right, null);
return left.Equals(right);
```

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, implémentez l’opérateur d’égalité afin qu’il soit mathématiquement cohérent avec les opérateurs d’addition et soustraction.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer un avertissement de cette règle lorsque l’implémentation par défaut de l’opérateur d’égalité fournit le comportement correct pour le type.

## <a name="example"></a>Exemple
 L’exemple suivant définit un type (`BadAddableType`) qui enfreint cette règle. Ce type doit implémenter l’opérateur d’égalité pour rendre les deux instances qui ont les mêmes valeurs de champ à tester `true` d’égalité. Le type `GoodAddableType` affiche l’implémentation corrigée. Notez que ce type implémente l’opérateur d’inégalité également et remplace <xref:System.Object.Equals%2A> pour répondre à d’autres règles. Une implémentation complète implémenterait également <xref:System.Object.GetHashCode%2A>.

 [!code-csharp[FxCop.Design.AddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_1.cs)]

## <a name="example"></a>Exemple
 L’exemple suivant teste l’égalité à l’aide des instances des types qui ont été définis précédemment dans cette rubrique pour illustrer la valeur par défaut et le comportement correct pour l’opérateur d’égalité.

 [!code-csharp[FxCop.Design.TestAddAndSubtract#1](../code-quality/codesnippet/CSharp/ca1013-overload-operator-equals-on-overloading-add-and-subtract_2.cs)]

Cet exemple génère la sortie suivante :

```txt
Bad type:  {2,2} {2,2} are equal? No
Good type: {3,3} {3,3} are equal? Yes
Good type: {3,3} {3,3} are == ?   Yes
Bad type:  {2,2} {9,9} are equal? No
Good type: {3,3} {9,9} are == ?   No
```

## <a name="see-also"></a>Voir aussi

- [Opérateurs d’égalité](/dotnet/standard/design-guidelines/equality-operators)