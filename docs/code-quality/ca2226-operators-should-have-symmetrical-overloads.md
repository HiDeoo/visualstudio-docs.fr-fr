---
title: 'CA2226 : Les opérateurs doivent contenir des surcharges symétriques'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
helpviewer_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
ms.assetid: d202401a-ea14-4559-b15e-0ea4f5b68789
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5f31abd49b2d9ef8c00e7d308d66583d968691f8
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45549769"
---
# <a name="ca2226-operators-should-have-symmetrical-overloads"></a>CA2226 : Les opérateurs doivent contenir des surcharges symétriques
|||
|-|-|
|TypeName|OperatorsShouldHaveSymmetricalOverloads|
|CheckId|CA2226|
|Category|Microsoft.Usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Un type implémente l’opérateur d’égalité ou d’inégalité et n’implémente pas l’opérateur opposé.

## <a name="rule-description"></a>Description de la règle
 Il n’existe aucun cas où l’égalité ou inégalité s’applique aux instances d’un type, et l’opérateur opposé n’est pas défini. Types implémentent généralement l’opérateur d’inégalité en retournant la valeur négative de l’opérateur d’égalité.

 Le compilateur c# émet une erreur pour les violations de cette règle.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, implémentez l’égalité et les opérateurs d’inégalité, ou supprimez celui qui est présent.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle. Votre type ne fonctionnera pas de manière cohérente avec le [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].

## <a name="related-rules"></a>Règles associées
 [CA1046 : Ne pas surcharger l’opérateur égal sur les types de référence](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225 : Les surcharges d’opérateur ont d’autres méthodes nommées](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2224 : Remplacez Equals lors de la surcharge de l’opérateur égal](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2218 : Remplacez GetHashCode lors du remplacement de Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231 : Surchargez l’opérateur égal (equals) en remplaçant ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)