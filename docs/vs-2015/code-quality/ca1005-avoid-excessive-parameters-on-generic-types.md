---
title: 'CA1005 : Éviter les paramètres excessifs sur les types génériques | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ed72b3ebb8ccacbf18e27bade20e1777e6434166
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49259517"
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005 : Éviter les paramètres excessifs sur les types génériques
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|AvoidExcessiveParametersOnGenericTypes|
|CheckId|CA1005|
|Category|Microsoft.Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un type générique extérieurement visible a plus de deux paramètres de type.

## <a name="rule-description"></a>Description de la règle
 Plus un type générique contient de paramètres de type, plus il est difficile de déterminer et de mémoriser la représentation de chaque paramètre de type. Il est généralement évident avec un paramètre de type, comme dans `List<T>`et dans certains cas avec deux paramètres de type, comme dans `Dictionary<TKey, TValue>`. Si plus de deux paramètres de type existent, la difficulté devient trop grande pour la plupart des utilisateurs (par exemple, `TooManyTypeParameters<T, K, V>` en c# ou `TooManyTypeParameters(Of T, K, V)` dans [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, modifiez le design pour utiliser pas plus de deux paramètres de type.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez pas d’avertissement de cette règle, sauf si le design nécessite absolument plus de deux paramètres de type. Fourniture de génériques dans une syntaxe facile à comprendre et à utiliser réduit le temps qui est nécessaire pour en savoir plus et augmente la vitesse d’adoption de nouvelles bibliothèques.

## <a name="related-rules"></a>Règles associées
 [CA1010 : Les collections doivent implémenter une interface générique](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000 : Ne déclarez pas de membres statiques sur les types génériques](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002 : N’exposez pas de listes génériques](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006 : Ne pas imbriquer les types génériques dans les signatures de membre](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004 : Les méthodes génériques doivent fournir un paramètre de type](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003 : Utiliser les instances du gestionnaire d’événements génériques](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007 : Utiliser des méthodes génériques lorsque cela est approprié](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Voir aussi
 [Génériques](http://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)



