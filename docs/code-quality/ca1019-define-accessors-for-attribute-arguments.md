---
title: "CA1019 : Définir des accesseurs pour les arguments d'attribut"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
helpviewer_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
ms.assetid: 197f2378-3c43-427e-80de-9ec25006c05c
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8a604ea8731108c73c3dfb1c279f2f243c0a05ad
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54931178"
---
# <a name="ca1019-define-accessors-for-attribute-arguments"></a>CA1019 : Définir des accesseurs pour les arguments d'attribut

|||
|-|-|
|TypeName|DefineAccessorsForAttributeArguments|
|CheckId|CA1019|
|Category|Microsoft.Design|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Dans son constructeur, un attribut définit des arguments qui n’ont pas de propriétés correspondantes.

## <a name="rule-description"></a>Description de la règle
 Les attributs peuvent définir des arguments obligatoires qui doivent être spécifiés lorsque vous appliquez l’attribut à une cible. Ceux-ci sont également appelés arguments positionnels parce qu’ils sont fournis aux constructeurs d’attributs en tant que paramètres positionnels. Pour chaque argument obligatoire, l’attribut doit également fournir une propriété en lecture seule correspondante afin que la valeur de l’argument puisse être récupérée au moment de l’exécution. Cette règle vérifie que, pour chaque paramètre de constructeur, vous avez défini la propriété correspondante.

 Les attributs peuvent également définir des arguments facultatifs, qui sont également appelés arguments nommés. Ces arguments sont fournis aux constructeurs d'attributs par noms et doivent disposer d'une propriété en lecture/écriture correspondante.

 Pour les arguments obligatoires et facultatifs, les propriétés correspondantes et les paramètres du constructeur doivent utiliser le même nom mais une casse différente. Propriétés utilisent Pascal casse et les paramètres la casse.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, ajoutez une propriété en lecture seule pour chaque paramètre de constructeur qui n’en a pas.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Supprimez un avertissement de cette règle si vous ne souhaitez pas la valeur de l’argument obligatoire soit récupérable.

## <a name="custom-attributes-example"></a>Exemple d’attributs personnalisés

L’exemple suivant montre deux attributs qui définissent un paramètre obligatoire (positionnel). La première implémentation de l’attribut est définie incorrectement. La seconde implémentation est correcte.

[!code-csharp[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_1.cs)]
[!code-vb[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/VisualBasic/ca1019-define-accessors-for-attribute-arguments_1.vb)]

## <a name="positional-and-named-arguments"></a>Arguments nommés et positionnels

Arguments nommés et positionnels indiquer clairement à des consommateurs de votre bibliothèque quels sont les arguments obligatoires pour l’attribut et les arguments sont facultatifs.

L’exemple suivant illustre une implémentation d’un attribut qui a des arguments positionnels et nommés :

[!code-csharp[FxCop.Design.AttributeAccessorsNamed#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_2.cs)]

L’exemple suivant montre comment appliquer l’attribut personnalisé à deux propriétés :

[!code-csharp[FxCop.Design.AttributeAccessorsNamedApplied#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_3.cs)]

## <a name="related-rules"></a>Règles associées
 [CA1813 : Évitez les attributs unsealed](../code-quality/ca1813-avoid-unsealed-attributes.md)

## <a name="see-also"></a>Voir aussi
 [Attributs](/dotnet/standard/design-guidelines/attributes)