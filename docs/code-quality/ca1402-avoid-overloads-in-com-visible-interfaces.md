---
title: 'CA1402 : Éviter les surcharges dans les interfaces COM visibles'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
helpviewer_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
ms.assetid: 2724c1f9-d5d3-4704-b124-21c4d398e5df
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e4360ff6c6355827a77d165c9a4975ffa8bdc89a
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45549009"
---
# <a name="ca1402-avoid-overloads-in-com-visible-interfaces"></a>CA1402 : Éviter les surcharges dans les interfaces COM visibles

|||
|-|-|
|TypeName|AvoidOverloadsInComVisibleInterfaces|
|CheckId|CA1402|
|Category|Microsoft.Interoperability|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un composant COM (Object Model) visible interface déclare les méthodes surchargées.

## <a name="rule-description"></a>Description de la règle
 Lorsque les méthodes surchargées sont exposées aux clients COM, seule la première surcharge de méthode conserve son nom. Les surcharges suivantes sont renommées de manière unique en ajoutant le nom, un caractère de trait de soulignement « _ » et un entier qui correspond à l’ordre de déclaration de la surcharge. Par exemple, considérez les méthodes suivantes :

```csharp
void SomeMethod(int valueOne);
void SomeMethod(int valueOne, int valueTwo, int valueThree);
void SomeMethod(int valueOne, int valueTwo);
```

Ces méthodes sont exposées aux clients COM comme suit.

```csharp
void SomeMethod(int valueOne);
void SomeMethod_2(int valueOne, int valueTwo, int valueThree);
void SomeMethod_3(int valueOne, int valueTwo);
```

Les clients COM Visual Basic 6 ne peut pas implémenter des méthodes d’interface à l’aide d’un trait de soulignement dans le nom.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, renommez les méthodes surchargées afin que les noms sont uniques. Vous pouvez également rendre l’interface invisible à COM en modifiant l’accessibilité à `internal` (`Friend` dans [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) ou en appliquant la <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> attribut la valeur `false`.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant montre une interface qui enfreint la règle et une interface qui satisfait la règle.

 [!code-vb[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/VisualBasic/ca1402-avoid-overloads-in-com-visible-interfaces_1.vb)]
 [!code-csharp[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/CSharp/ca1402-avoid-overloads-in-com-visible-interfaces_1.cs)]

## <a name="related-rules"></a>Règles associées
 [CA1413 : Évitez les champs non publics dans les types valeur visibles par COM](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

 [CA1407 : Éviter les membres statiques dans les types visibles par COM](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017 : Marquez les assemblys avec ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Voir aussi

- [Interopération avec du code non managé](/dotnet/framework/interop/index)
- [Long (type de données)](/dotnet/visual-basic/language-reference/data-types/long-data-type)