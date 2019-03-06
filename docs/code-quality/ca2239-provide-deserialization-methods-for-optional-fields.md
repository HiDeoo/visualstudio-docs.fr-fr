---
title: 'CA2239 : Spécifiez des méthodes de désérialisation pour les champs facultatifs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2239
- ProvideDeserializationMethodsForOptionalFields
helpviewer_keywords:
- ProvideDeserializationMethodsForOptionalFields
- CA2239
ms.assetid: 6480ff5e-0caa-4707-814e-2f927cdafef5
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5599f111d6580f654436fdd2ff85f69f1329920d
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55907527"
---
# <a name="ca2239-provide-deserialization-methods-for-optional-fields"></a>CA2239 : Spécifiez des méthodes de désérialisation pour les champs facultatifs

|||
|-|-|
|TypeName|ProvideDeserializationMethodsForOptionalFields|
|CheckId|CA2239|
|Category|Microsoft.Usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Un type a un champ qui est marqué avec le <xref:System.Runtime.Serialization.OptionalFieldAttribute?displayProperty=fullName> attribut et le type ne fournit pas de méthodes de gestion des événements de désérialisation.

## <a name="rule-description"></a>Description de la règle
 Le <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribut n’a aucun effet sur la sérialisation ; un champ marqué avec l’attribut est sérialisé. Toutefois, le champ est ignoré lors de la sérialisation de déduplication et conserve la valeur par défaut associée à son type. Gestionnaires d’événements de désérialisation doivent être déclarés pour définir le champ au cours du processus de désérialisation.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, ajoutez des méthodes pour le type de gestion des événements de désérialisation.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer un avertissement de cette règle si le champ doit être ignoré pendant le processus de désérialisation.

## <a name="example"></a>Exemple
 L’exemple suivant illustre un type avec un champ facultatif et un événement de désérialisation des méthodes de gestion.

 [!code-csharp[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/CSharp/ca2239-provide-deserialization-methods-for-optional-fields_1.cs)]
 [!code-vb[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/VisualBasic/ca2239-provide-deserialization-methods-for-optional-fields_1.vb)]

## <a name="related-rules"></a>Règles associées
 [CA2236 : Appeler des méthodes de classe de base sur les types ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240 : Implémentez ISerializable correctement](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229 : Implémentez des constructeurs de sérialisation](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238 : Implémentez les méthodes de sérialisation](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235 : Marquez tous les champs non sérialisables](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237 : Marquer les types ISerializable avec SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2120 : Constructeurs de sérialisation sécurisé](../code-quality/ca2120-secure-serialization-constructors.md)