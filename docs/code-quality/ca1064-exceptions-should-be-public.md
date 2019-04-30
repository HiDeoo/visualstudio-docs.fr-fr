---
title: 'CA1064 : Les exceptions doivent être publiques'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1064
- ExceptionsShouldBePublic
helpviewer_keywords:
- ExceptionsShouldBePublic
- CA1064
ms.assetid: 83eb224c-2456-4368-acf4-3b3378e67759
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8196d4c48bfb93735b62c6f24cb08ec462e64c91
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62788579"
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064 : Les exceptions doivent être publiques

|||
|-|-|
|TypeName|ExceptionsShouldBePublic|
|CheckId|CA1064|
|Category|Microsoft.Design|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Une exception non publique dérive directement de <xref:System.Exception>, <xref:System.SystemException>, ou <xref:System.ApplicationException>.

## <a name="rule-description"></a>Description de la règle
 Une exception interne est uniquement visible à l’intérieur de sa propre portée interne. Lorsque l'exception se situe en dehors de la portée interne, seule l'exception de base peut être utilisée pour intercepter l'exception. Si l’exception interne est héritée de <xref:System.Exception>, <xref:System.SystemException>, ou <xref:System.ApplicationException>, le code externe n’aura pas d’informations suffisantes pour savoir que faire avec l’exception.

 Toutefois, si le code a une exception publique ultérieurement est utilisée comme base pour une exception interne, il est raisonnable de supposer que le code plus out sera en mesure de faire quelque chose d’intelligent avec l’exception de base. L’exception publique aura plus d’informations que celles fournies par <xref:System.Exception>, <xref:System.SystemException>, ou <xref:System.ApplicationException>.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Rendez l’exception publique ou dérivez l’exception interne d’une exception publique qui n’est pas <xref:System.Exception>, <xref:System.SystemException>, ou <xref:System.ApplicationException>.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Supprimer un message à partir de cette règle si vous êtes sûr dans tous les cas que l’exception privée sera interceptée dans sa propre portée interne.

## <a name="example"></a>Exemple
 Cette règle se déclenche sur le premier exemple de méthode, FirstCustomException, car la classe d’exception dérive directement d’Exception et est interne. La règle ne déclenche pas sur la classe SecondCustomException, car bien que la classe dérive également directement à partir de l’Exception, la classe est déclarée publique. La troisième classe également ne pas se déclencher la règle, car il ne dérive pas directement à partir de <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, ou <xref:System.ApplicationException?displayProperty=fullName>.

 [!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../code-quality/codesnippet/CSharp/ca1064-exceptions-should-be-public_1.cs)]
