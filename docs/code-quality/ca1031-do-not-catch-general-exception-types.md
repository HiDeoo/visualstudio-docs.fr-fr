---
title: "CA1031 : Ne pas intercepter des types d'exception générale"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
helpviewer_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
ms.assetid: cbc283ae-2a46-4ec0-940e-85aa189b118f
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 16b43aa25ef4e2d81b2d6f72e7e1c2bfa3e8b6f7
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551620"
---
# <a name="ca1031-do-not-catch-general-exception-types"></a>CA1031 : Ne pas intercepter des types d'exception générale

|||
|-|-|
|TypeName|DoNotCatchGeneralExceptionTypes|
|CheckId|CA1031|
|Category|Microsoft.Design|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Une exception générale comme <xref:System.Exception?displayProperty=fullName> ou <xref:System.SystemException?displayProperty=fullName> est interceptée dans un `catch` instruction ou une clause catch générale comme `catch()` est utilisé.

## <a name="rule-description"></a>Description de la règle
 Les exceptions générales ne doivent pas être interceptées.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, interceptez une exception plus spécifique ou levez à nouveau l’exception générale en tant que la dernière instruction dans le `catch` bloc.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle. Interception de types d’exception générale peut masquer des problèmes d’exécution à partir de l’utilisateur de la bibliothèque et peut compliquer le débogage.

> [!NOTE]
> En commençant par le [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)], le common language runtime (CLR) n’envoie plus d’exceptions d’état endommagé qui se produisent dans le système d’exploitation et le code managé, telles que des violations d’accès dans [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)], pour être gérées par le code managé. Si vous voulez compiler une application dans le [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] ou versions ultérieures et maintenir gestion des exceptions d’état endommagé, vous pouvez appliquer le <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> d’attribut à la méthode qui gère l’exception d’état endommagé.

## <a name="example"></a>Exemple
 L’exemple suivant montre un type qui enfreint cette règle et un type qui implémente correctement le `catch` bloc.

 [!code-cpp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CPP/ca1031-do-not-catch-general-exception-types_1.cpp)]
 [!code-vb[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/VisualBasic/ca1031-do-not-catch-general-exception-types_1.vb)]
 [!code-csharp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CSharp/ca1031-do-not-catch-general-exception-types_1.cs)]

## <a name="related-rules"></a>Règles associées
 [CA2200 : Levez à nouveau une exception pour conserver les détails de la pile](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)