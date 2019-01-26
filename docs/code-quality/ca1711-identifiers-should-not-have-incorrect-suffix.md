---
title: 'CA1711 : Les identificateurs ne doivent pas porter un suffixe incorrect'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
helpviewer_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a612aa39899336eda4802e849529ae61faf192be
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54935642"
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711 : Les identificateurs ne doivent pas porter un suffixe incorrect

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|
|CheckId|CA1711|
|Category|Microsoft.Naming|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause

Un identificateur a un suffixe incorrect.

## <a name="rule-description"></a>Description de la règle

Par convention, seuls les noms des types qui étendent certains types de base ou qui implémentent certaines interfaces, ou les types dérivés de ces types, doivent se terminer par des suffixes réservés spécifiques. Les autres noms de types ne doivent pas utiliser ces suffixes réservés.

Le tableau suivant répertorie les suffixes réservés et les types de base et les interfaces à laquelle ils sont associés.

|Suffix|Interface/type de base|
|------------|--------------------------|
|Attribut|<xref:System.Attribute?displayProperty=fullName>|
|Collection|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|
|Dictionary|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|
|EventHandler|Un délégué de gestionnaire d’événements|
|Exception|<xref:System.Exception?displayProperty=fullName>|
|Autorisation|<xref:System.Security.IPermission?displayProperty=fullName>|
|File d'attente|<xref:System.Collections.Queue?displayProperty=fullName>|
|Stack|<xref:System.Collections.Stack?displayProperty=fullName>|
|Flux|<xref:System.IO.Stream?displayProperty=fullName>|

En outre, les suffixes suivants doivent **pas** servir :

- `Delegate`

- `Enum`

- `Impl` (utilisez `Core` à la place)

- `Ex` ou suffixe semblable pour le distinguer d’une version antérieure du même type

Conventions d’affectation de noms fournissent une apparence commune pour les bibliothèques qui ciblent le common language runtime. Cela réduit la courbe d’apprentissage qui est requis pour les nouvelles bibliothèques de logiciels et confirment au client que la bibliothèque a été développée par une personne compétente en matière de développement de code managé.

## <a name="how-to-fix-violations"></a>Comment corriger les violations

Supprimez le suffixe du nom de type.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements

Ne supprimez pas d’avertissement de cette règle, sauf si le suffixe a une signification non équivoque dans le domaine d’application.

## <a name="related-rules"></a>Règles associées

- [CA1710 : Les identificateurs doivent avoir un suffixe correct](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)

## <a name="see-also"></a>Voir aussi

- [Attributs](/dotnet/standard/design-guidelines/attributes)
- [Gestion et déclenchement d’événements](/dotnet/standard/events/index)