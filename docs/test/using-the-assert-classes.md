---
title: Méthodes et classes assert MSTest
ms.date: 06/07/2018
ms.topic: reference
helpviewer_keywords:
- Assert classes
- Assert methods
- unit tests, Assert classes
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: c36916c79bd783ed2c6ce960b068e85478b9971d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75592046"
---
# <a name="use-assert-classes-for-unit-testing"></a>Utiliser des classes Assert pour les tests unitaires

Utilisez les classes Assert de l’espace de noms <xref:Microsoft.VisualStudio.TestTools.UnitTesting> pour vérifier des fonctionnalités spécifiques. Une méthode de test unitaire teste le code d’une méthode dans le code de votre application. Toutefois, elle ne signale l’exactitude du comportement du code que si vous incluez des instructions Assert.

## <a name="kinds-of-asserts"></a>Genres d’assertion

L’espace de noms <xref:Microsoft.VisualStudio.TestTools.UnitTesting> fournit plusieurs genres de classes Assert.

Dans votre méthode de test, vous pouvez appeler des méthodes de la classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert?displayProperty=fullName>, telles que <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A?displayProperty=nameWithType>. La classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> propose de nombreuses méthodes, dont la plupart ont plusieurs surcharges.

### <a name="compare-strings-and-collections"></a>Comparer des chaînes et des collections

Utilisez la classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert> pour comparer des collections d’objets ou pour vérifier l’état d’une collection.

Utilisez la classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert> pour comparer et examiner des chaînes. Cette classe contient diverses méthodes utiles, telles que <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Contains%2A?displayProperty=nameWithType>, <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Matches%2A?displayProperty=nameWithType> et <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.StartsWith%2A?displayProperty=nameWithType>.

### <a name="exceptions"></a>Exceptions

L’exception <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException> est levée à chaque échec d’un test. Un test est considéré comme un échec s’il arrive à expiration, lève une exception inattendue ou contient une instruction Assert qui produit un résultat **Failed**.

L’exception <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException> est levée chaque fois qu’un test produit un résultat **Inconclusive**. En général, vous ajoutez une instruction <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Inconclusive%2A?displayProperty=nameWithType> à un test sur lequel vous travaillez pour indiquer qu’il n’est pas encore prêt à être exécuté.

> [!NOTE]
> Une autre stratégie consiste à marquer un test qui n’est pas prêt à être exécuté avec l’attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.IgnoreAttribute>. Toutefois, cela présente un inconvénient : vous ne pouvez pas générer facilement un rapport sur le nombre de tests qui ne sont pas implémentés.

Si vous écrivez une nouvelle classe d’exception assert, héritez de la classe de base <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException> pour identifier plus facilement l’exception comme un échec d’assertion, et non comme une exception inattendue levée à partir de votre code de test ou de production.

Pour vérifier qu’une exception censée être levée par une méthode dans le code de votre application est effectivement levée, utilisez la méthode <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>Voir aussi

- [Test unitaire de votre code](../test/unit-test-your-code.md)
