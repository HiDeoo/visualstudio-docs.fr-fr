---
title: 'CA1004 : les méthodes génériques doivent fournir un paramètre de type | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1004
- GenericMethodsShouldProvideTypeParameter
helpviewer_keywords:
- GenericMethodsShouldProvideTypeParameter
- CA1004
ms.assetid: 38755f6a-fb45-4bf2-932e-0354ad826499
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: e7a96c95313ffee82448e3485c90868c8103814a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85539800"
---
# <a name="ca1004-generic-methods-should-provide-type-parameter"></a>CA1004 : Les méthodes génériques doivent fournir un paramètre de type
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|GenericMethodsShouldProvideTypeParameter|
|CheckId|CA1004|
|Category|Microsoft. Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause :
 La signature de paramètre d’une méthode générique visible de l’extérieur ne contient pas les types qui correspondent à tous les paramètres de type de la méthode.

## <a name="rule-description"></a>Description de la règle
 L'inférence désigne la manière dont l'argument de type d'une méthode générique est déterminé par le type d'argument passé à la méthode, au lieu d'utiliser la spécification explicite de l'argument de type. Pour activer l'inférence, la signature de paramètre d'une méthode générique doit contenir un paramètre du même type que le paramètre de type de la méthode. Dans ce cas, il n'est pas nécessaire de spécifier l'argument de type. Quand vous utilisez l’inférence pour tous les paramètres de type, la syntaxe pour appeler des méthodes d’instance génériques et non génériques est identique. Cela simplifie l’utilisation des méthodes génériques.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, modifiez la conception afin que la signature de paramètre contienne le même type pour chaque paramètre de type de la méthode.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle. La fourniture de génériques dans une syntaxe facile à comprendre et à utiliser réduit le temps nécessaire à l’apprentissage et à l’augmentation du taux d’adoption de nouvelles bibliothèques.

## <a name="example"></a>Exemple
 L’exemple suivant illustre la syntaxe d’appel de deux méthodes génériques. L’argument de type pour `InferredTypeArgument` est déduit, et l’argument de type pour `NotInferredTypeArgument` doit être spécifié explicitement.

 [!code-csharp[FxCop.Design.Inference#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.Inference/cs/FxCop.Design.Inference.cs#1)]
 [!code-vb[FxCop.Design.Inference#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.Inference/vb/FxCop.Design.Inference.vb#1)]

## <a name="related-rules"></a>Règles associées
 [CA1005 : Éviter les paramètres excessifs sur les types génériques](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010 : Les collections doivent implémenter une interface générique](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000 : Ne pas déclarer de membres statiques sur les types génériques](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002 : Ne pas exposer de listes génériques](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006 : Ne pas imbriquer les types génériques dans les signatures de membre](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1003 : Utiliser les instances du gestionnaire d'événements génériques](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007 : Utiliser des classes génériques lorsque cela est approprié](../code-quality/ca1007-use-generics-where-appropriate.md)