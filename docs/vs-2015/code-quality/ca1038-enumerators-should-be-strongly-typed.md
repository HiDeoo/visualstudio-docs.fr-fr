---
title: 'CA1038 : les énumérateurs doivent être fortement typés | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
helpviewer_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
ms.assetid: 8919f526-d487-42a4-87dc-2b2ee25260c4
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: e660b1af58dca8d0d69ce2844076382c4a5a1f12
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85548263"
---
# <a name="ca1038-enumerators-should-be-strongly-typed"></a>CA1038 : Les énumérateurs doivent être fortement typés
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|EnumeratorsShouldBeStronglyTyped|
|CheckId|CA1038|
|Category|Microsoft. Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause :
 Un type public ou protégé implémente <xref:System.Collections.IEnumerator?displayProperty=fullName> , mais ne fournit pas de version fortement typée de la <xref:System.Collections.IEnumerator.Current%2A?displayProperty=fullName> propriété. Les types dérivés des types suivants sont exempts de cette règle :

- <xref:System.Collections.CollectionBase?displayProperty=fullName>

- <xref:System.Collections.DictionaryBase?displayProperty=fullName>

- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

## <a name="rule-description"></a>Description de la règle
 Cette règle requiert <xref:System.Collections.IEnumerator> que les implémentations fournissent également une version fortement typée de la <xref:System.Collections.IEnumerator.Current%2A> propriété afin que les utilisateurs ne soient pas tenus d’effectuer un cast de la valeur de retour vers le type fort lorsqu’ils utilisent les fonctionnalités fournies par l’interface. Cette règle suppose que le type qui implémente <xref:System.Collections.IEnumerator> contient une collection d’instances d’un type qui est plus fort que <xref:System.Object> .

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, implémentez explicitement la propriété d’interface (déclarez-la comme `IEnumerator.Current` ). Ajoutez une version publique fortement typée de la propriété, déclarée en tant que `Current` , et retournent un objet fortement typé.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Supprimez un avertissement de cette règle quand vous implémentez un énumérateur basé sur un objet pour une utilisation avec une collection basée sur un objet, telle qu’une arborescence binaire. Les types qui étendent la nouvelle collection définissent l’énumérateur fortement typé et exposent la propriété fortement typée.

## <a name="example"></a>Exemple
 L’exemple suivant illustre la méthode correcte pour implémenter un type fortement typé <xref:System.Collections.IEnumerator> .

 [!code-csharp[FxCop.Design.IEnumeratorStrongTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.IEnumeratorStrongTypes/cs/FxCop.Design.IEnumeratorStrongTypes.cs#1)]

## <a name="related-rules"></a>Règles associées
 [CA1035 : Les implémentations ICollection possèdent des membres fortement typés](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)

 [CA1039 : Les listes sont fortement typées](../code-quality/ca1039-lists-are-strongly-typed.md)

## <a name="see-also"></a>Voir aussi
 <xref:System.Collections.IEnumerator?displayProperty=fullName> <xref:System.Collections.CollectionBase?displayProperty=fullName>
 <xref:System.Collections.DictionaryBase?displayProperty=fullName>
 <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>
