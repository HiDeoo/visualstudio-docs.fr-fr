---
title: 'CA1050 : Déclarer les types dans des espaces de noms'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1050
- DeclareTypesInNamespaces
helpviewer_keywords:
- DeclareTypesInNamespaces
- CA1050
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 97cc36e7b454484f4fcdfb3d3be499e48af9c407
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55018837"
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050 : Déclarer les types dans des espaces de noms

|||
|-|-|
|TypeName|DeclareTypesInNamespaces|
|CheckId|CA1050|
|Category|Microsoft.Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un type public ou protégé est défini en dehors de l’étendue d’un espace de noms nommé.

## <a name="rule-description"></a>Description de la règle
 Les types sont déclarés dans les espaces de noms pour empêcher les collisions de nom et comme un moyen d’organiser les types associés dans une hiérarchie d’objets. Les types qui sont en dehors de tout espace de noms nommé sont dans un espace de noms global qui ne peut pas être référencé dans le code.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, placez le type dans un espace de noms.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Bien que vous ayez jamais supprimer un avertissement de cette règle, il est possible pour ce faire, lorsque l’assembly ne sera jamais utilisé avec d’autres assemblys.

## <a name="example"></a>Exemple
 L’exemple suivant montre une bibliothèque qui a un type déclaré incorrectement hors d’un espace de noms et un type qui a le même nom déclaré dans un espace de noms.

 [!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_1.cs)]
 [!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_1.vb)]

## <a name="example"></a>Exemple
 L’application suivante utilise la bibliothèque qui a été définie précédemment. Notez que le type qui est déclaré en dehors d’un espace de noms est créé lorsque le nom `Test` n’est pas qualifié par un espace de noms. Notez également que pour accéder à la `Test` tapez `Goodspace`, le nom de l’espace de noms est obligatoire.

 [!code-csharp[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_2.cs)]
 [!code-vb[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_2.vb)]