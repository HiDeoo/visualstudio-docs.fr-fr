---
title: 'CA1034 : Les types imbriqués ne doivent pas être visibles'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e82189d496e6f9aaa651e59d98ce0f3ab17153c1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54958132"
---
# <a name="ca1034-nested-types-should-not-be-visible"></a>CA1034 : Les types imbriqués ne doivent pas être visibles

|||
|-|-|
|TypeName|NestedTypesShouldNotBeVisible|
|CheckId|CA1034|
|Category|Microsoft.Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause

Un type visible de l’extérieur contient une déclaration de type visible de l’extérieur. Les énumérations imbriquées et les types protégés sont exemptés de cette règle.

## <a name="rule-description"></a>Description de la règle
 Un type imbriqué est un type déclaré dans l’étendue d’un autre type. Les types imbriqués sont utiles pour encapsuler les détails d’implémentation privée du type conteneur. Utilisés à cette fin, les types imbriqués ne doivent pas être visibles de l'extérieur.

 N’utilisez pas les types imbriqués extérieurement visibles pour le regroupement logique ou pour éviter les collisions de nom ; au lieu de cela, utilisez des espaces de noms.

 Les types imbriqués incluent la notion d’accessibilité des membres, certains programmeurs ne comprennent pas clairement.

 Les types protégés peuvent être utilisés dans les sous-classes et les types imbriqués dans des scénarios de personnalisation avancée.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Si vous n’envisagez pas de type imbriqué à être visible de l’extérieur, modifiez l’accessibilité du type. Sinon, supprimez le type imbriqué de son parent. Si l’objectif de l’imbrication consiste à catégoriser le type imbriqué, utilisez un espace de noms pour créer la hiérarchie à la place.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant montre un type qui viole la règle.

 [!code-cpp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CPP/ca1034-nested-types-should-not-be-visible_1.cpp)]
 [!code-csharp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CSharp/ca1034-nested-types-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/VisualBasic/ca1034-nested-types-should-not-be-visible_1.vb)]