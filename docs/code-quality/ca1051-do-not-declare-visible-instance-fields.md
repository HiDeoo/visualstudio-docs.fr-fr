---
title: "CA1051 : Ne pas déclarer de champs d'instances visibles"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fd4783f6327061da0ce522cc02082289cdee3d39
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55938093"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051 : Ne pas déclarer de champs d'instances visibles

|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|Category|Microsoft.Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un type visible de l’extérieur a un champ d’instance extérieurement visible.

## <a name="rule-description"></a>Description de la règle
 Un champ s'utilise principalement en tant que détail d'implémentation. Les champs doivent être `private` ou `internal` et doivent être exposés à l’aide de propriétés. Il est aussi facile d’accéder à une propriété comme il est d’accéder à un champ, et le code dans les accesseurs d’une propriété peut changer lorsque les fonctionnalités du type évoluent sans introduire de modifications avec rupture. Propriétés qui retournent simplement la valeur d’un champ privé ou interne sont optimisées pour s’exécuter identiques à celles de l’accès à un champ ; très peu de gain de performances est associé à l’utilisation de champs extérieurement visibles sur les propriétés.

 Extérieurement visible fait référence à `public`, `protected`, et `protected internal` (`Public`, `Protected`, et `Protected Friend` en Visual Basic) niveaux d’accessibilité.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, rendez le champ `private` ou `internal` et l’exposer à l’aide d’une propriété visible de l’extérieur.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle. Champs extérieurement visibles ne fournissent pas les avantages qui ne sont pas disponibles aux propriétés. En outre, les champs publics ne peuvent pas être protégés par [demandes de liaison](/dotnet/framework/misc/link-demands). Consultez [CA2112 : Types sécurisés ne doivent pas exposer de champs](../code-quality/ca2112-secured-types-should-not-expose-fields.md).

## <a name="example"></a>Exemple
 L’exemple suivant illustre un type (`BadPublicInstanceFields`) qui enfreint cette règle. `GoodPublicInstanceFields` Affiche le code corrigé.

 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]

## <a name="related-rules"></a>Règles associées
 [CA2112 : Types sécurisés ne doivent pas exposer de champs](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>Voir aussi
 [Demandes de liaison](/dotnet/framework/misc/link-demands)