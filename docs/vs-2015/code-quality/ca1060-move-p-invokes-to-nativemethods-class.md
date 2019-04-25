---
title: 'CA1060 : Déplacer les P-Invoke vers une classe NativeMethods | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
helpviewer_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
ms.assetid: 06686c8c-6ad3-42f7-a355-cbaefa347cfc
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f47fa4326da9914171e5014decbd6d6923c2f02e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58951600"
---
# <a name="ca1060-move-pinvokes-to-nativemethods-class"></a>CA1060 : Déplacer les P/Invoke vers une classe NativeMethods
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MovePInvokesToNativeMethodsClass|
|CheckId|CA1060|
|Category|Microsoft.Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Une méthode utilise Platform Invocation Services d’accéder au code non managé et n’est pas un membre de l’un de le **NativeMethods** classes.

## <a name="rule-description"></a>Description de la règle
 Méthodes d’appel de plateforme, telles que celles qui sont marquées à l’aide de la <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> attribut, ou les méthodes qui sont définies à l’aide de la `Declare` mot clé dans [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], accéder au code non managé. Ces méthodes doivent être dans une des classes suivantes :

- **NativeMethods** -cette classe ne supprime pas de parcours de pile pour l’autorisation de code non managé. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> ne doit pas être appliqué à cette classe.) Cette classe est pour les méthodes qui peuvent être utilisées partout, car un parcours de pile sera effectué.

- **SafeNativeMethods** -cette classe supprime des parcours de pile pour l’autorisation de code non managé. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> est appliqué à cette classe.) Cette classe est pour les méthodes qui sont sécurisés pour tous les appelants. Les appelants de ces méthodes n'êtes pas obligés d’effectuer une révision de sécurité complète pour vous assurer que l’utilisation est sécurisée, car les méthodes sont sans conséquence pour tout appelant.

- **UnsafeNativeMethods** -cette classe supprime des parcours de pile pour l’autorisation de code non managé. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> est appliqué à cette classe.) Cette classe est pour les méthodes qui sont potentiellement dangereuses. Un appelant de ces méthodes doit effectuer une révision de sécurité complète pour vous assurer que l’utilisation est sécurisée, car aucun parcours de pile ne sera effectuée.

  Ces classes sont déclarées en tant que `internal` (`Friend`, en Visual Basic) et de déclarer un constructeur privé pour empêcher la création de nouvelles instances. Les méthodes dans ces classes doivent être `static` et `internal` (`Shared` et `Friend` en Visual Basic).

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, déplacer la méthode appropriés **NativeMethods** classe. Pour la plupart des applications, déplacement de P/Invoke vers une nouvelle classe nommée **NativeMethods** est suffisant.

 Toutefois, si vous développez des bibliothèques pour une utilisation dans d’autres applications, vous devez envisager de définir deux autres classes sont appelés **SafeNativeMethods** et **UnsafeNativeMethods**. Ces classes ressemblent à la **NativeMethods** classe ; Toutefois, ils sont marqués à l’aide d’un attribut spécial appelé **SuppressUnmanagedCodeSecurityAttribute**. Lorsque cet attribut est appliqué, le runtime n’effectue pas un parcours de pile complet pour vous assurer que tous les appelants ont le **UnmanagedCode** autorisation. En règle générale, le runtime vérifie pour cette autorisation au démarrage. Étant donné que la vérification n’est pas effectuée, elle peut améliorer considérablement les performances pour les appels à ces méthodes non managées, il permet également au code qui a des autorisations limitées pour appeler ces méthodes.

 Toutefois, vous devez utiliser cet attribut avec une extrême prudence. Il peut avoir des implications en matière de sécurité sérieux si elle est implémentée de manière incorrecte...

 Pour plus d’informations sur la façon d’implémenter les méthodes, consultez le **NativeMethods** exemple, **SafeNativeMethods** exemple, et **UnsafeNativeMethods** exemple.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant déclare une méthode qui enfreint cette règle. Pour corriger la violation, la **RemoveDirectory** P/Invoke doivent être déplacée vers une classe appropriée est conçue pour contenir uniquement de P/Invoke.

 [!code-csharp[FxCop.Design.DllImportNativeMethods#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.DllImportNativeMethods/cs/FxCop.Design.DllImportNativeMethods.cs#1)]
 [!code-vb[FxCop.Design.DllImportNativeMethods#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.DllImportNativeMethods/vb/FxCop.Design.DllImportNativeMethods.vb#1)]

## <a name="nativemethods-example"></a>Exemple de NativeMethods

### <a name="description"></a>Description
 Étant donné que le **NativeMethods** classe ne doit pas être marquée à l’aide de **SuppressUnmanagedCodeSecurityAttribute**, P/Invoke qui sont placées dans il nécessitera **UnmanagedCode** autorisation. Étant donné que la plupart des applications s’exécutent à partir de l’ordinateur local et être exécuté avec une confiance totale, il s’agit généralement pas un problème. Toutefois, si vous développez des bibliothèques réutilisables, vous devez envisager de définir un **SafeNativeMethods** ou **UnsafeNativeMethods** classe.

 L’exemple suivant montre un **Interaction.Beep** méthode qui encapsule le **MessageBeep** fonction par user32.dll. Le **MessageBeep** P/Invoke est placé dans le **NativeMethods** classe.

### <a name="code"></a>Code
 [!code-csharp[FxCop.Design.NativeMethods#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethods/cs/FxCop.Design.NativeMethods.cs#1)]
 [!code-vb[FxCop.Design.NativeMethods#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethods/vb/FxCop.Design.NativeMethods.vb#1)]

## <a name="safenativemethods-example"></a>Exemple SafeNativeMethods

### <a name="description"></a>Description
 Les méthodes P/Invoke qui peuvent être exposés en toute sécurité à n’importe quelle application et qui n’ont pas d’effets secondaires doivent être placés dans une classe nommée **SafeNativeMethods**. Vous n’avez pas à demander des autorisations et vous n’êtes pas obligé de faites bien attention à où elles sont appelées à partir de.

 L’exemple suivant montre un **Environment.TickCount** propriété qui encapsule le **GetTickCount** fonction à partir de kernel32.dll.

### <a name="code"></a>Code
 [!code-csharp[FxCop.Design.NativeMethodsSafe#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethodsSafe/cs/FxCop.Design.NativeMethodsSafe.cs#1)]
 [!code-vb[FxCop.Design.NativeMethodsSafe#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethodsSafe/vb/FxCop.Design.NativeMethodsSafe.vb#1)]

## <a name="unsafenativemethods-example"></a>Exemple UnsafeNativeMethods

### <a name="description"></a>Description
 Les méthodes P/Invoke qui ne peut pas être appelée en toute sécurité et qui peut provoquer des effets secondaires doivent être placés dans une classe nommée **UnsafeNativeMethods**. Ces méthodes doivent être vérifiées rigoureusement pour vous assurer qu’ils ne sont pas exposées à l’utilisateur involontairement. La règle [CA2118 : Passez en revue l’utilisation de SuppressUnmanagedCodeSecurityAttribute](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md) peut vous y aider. Les méthodes doivent également avoir une autre autorisation demandée au lieu de **UnmanagedCode** lors de leur utilisation.

 L’exemple suivant montre un **Cursor.Hide** méthode qui encapsule le **ShowCursor** fonction par user32.dll.

### <a name="code"></a>Code
 [!code-csharp[FxCop.Design.NativeMethodsUnsafe#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethodsUnsafe/cs/FxCop.Design.NativeMethodsUnsafe.cs#1)]
 [!code-vb[FxCop.Design.NativeMethodsUnsafe#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethodsUnsafe/vb/FxCop.Design.NativeMethodsUnsafe.vb#1)]

## <a name="see-also"></a>Voir aussi
 [Avertissements liés à la conception](../code-quality/design-warnings.md)
