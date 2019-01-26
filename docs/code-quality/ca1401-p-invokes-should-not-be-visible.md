---
title: 'CA1401 : Les P-Invoke ne doivent pas être visibles'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- PInvokesShouldNotBeVisible
- CA1401
helpviewer_keywords:
- CA1401
- PInvokesShouldNotBeVisible
ms.assetid: 0f4d96c1-f9de-414e-b223-4dc7f691bee3
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a139dd44c470422554dd2d5ccb42ab61a9d84637
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021401"
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401 : Les P/Invoke ne doivent pas être visibles

|||
|-|-|
|TypeName|PInvokesShouldNotBeVisible|
|CheckId|CA1401|
|Category|Microsoft.Interoperability|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Une méthode publique ou protégée dans un type public a le <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> attribut (également implémenté par le `Declare` mot clé dans [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).

## <a name="rule-description"></a>Description de la règle
 Les méthodes marquées avec le <xref:System.Runtime.InteropServices.DllImportAttribute> attribut (ou les méthodes qui sont définies à l’aide de la `Declare` mot clé dans [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) Platform Invocation Services permet d’accéder au code non managé. De telles méthodes ne doivent pas être exposées. En gardant ces méthodes privées ou internes, vous vous assurer que votre bibliothèque ne peut pas être utilisée de violation de sécurité en autorisant l’accès à des API non managées qu’ils ne peuvent pas appeler sinon les appelants.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, modifiez le niveau d’accès de la méthode.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant déclare une méthode qui enfreint cette règle.

 [!code-vb[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/VisualBasic/ca1401-p-invokes-should-not-be-visible_1.vb)]
 [!code-csharp[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/CSharp/ca1401-p-invokes-should-not-be-visible_1.cs)]