---
title: 'CA1060 : déplacer les P-Invoke vers la classe NativeMethods | Microsoft Docs'
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
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: e01ad9fc4fc57917c123404d8863d04240585793
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85533430"
---
# <a name="ca1060-move-pinvokes-to-nativemethods-class"></a>CA1060 : Déplacer les P/Invoke vers une classe NativeMethods
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|MovePInvokesToNativeMethodsClass|
|CheckId|CA1060|
|Category|Microsoft. Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Une méthode utilise des services d’appel de plateforme pour accéder à du code non managé et n’est pas membre de l’une des classes **NativeMethods** .

## <a name="rule-description"></a>Description de la règle
 Les méthodes d’appel de code non managé, telles que celles qui sont marquées à l’aide de l' <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> attribut, ou les méthodes définies à l’aide du `Declare` mot clé dans [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] , accèdent au code non managé. Ces méthodes doivent être dans l’une des classes suivantes :

- **NativeMethods** : cette classe ne supprime pas les parcours de pile pour l’autorisation de code non managé. ( <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> ne doit pas être appliqué à cette classe.) Cette classe est destinée aux méthodes qui peuvent être utilisées n’importe où, car un parcours de la pile sera effectué.

- **SafeNativeMethods** : cette classe supprime les parcours de la pile pour l’autorisation de code non managé. ( <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> s’applique à cette classe.) Cette classe est destinée aux méthodes qui peuvent être appelées en toute sécurité. Les appelants de ces méthodes ne sont pas requis pour effectuer une révision de sécurité complète afin de s’assurer que l’utilisation est sécurisée, car les méthodes sont inoffensives pour un appelant.

- **UnsafeNativeMethods** : cette classe supprime les parcours de la pile pour l’autorisation de code non managé. ( <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> s’applique à cette classe.) Cette classe est destinée aux méthodes potentiellement dangereuses. Tout appelant de ces méthodes doit effectuer une révision de sécurité complète pour s’assurer que l’utilisation est sécurisée, car aucun parcours de la pile ne sera effectué.

  Ces classes sont déclarées comme `internal` ( `Friend` , dans Visual Basic) et déclarent un constructeur privé pour empêcher la création de nouvelles instances. Les méthodes de ces classes doivent être `static` et `internal` ( `Shared` et `Friend` dans Visual Basic).

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, déplacez la méthode vers la classe **NativeMethods** appropriée. Pour la plupart des applications, le déplacement des P/Invoke vers une nouvelle classe nommée **NativeMethods** est suffisant.

 Toutefois, si vous développez des bibliothèques à utiliser dans d’autres applications, vous devez envisager de définir deux autres classes appelées **SafeNativeMethods** et **UnsafeNativeMethods**. Ces classes ressemblent à la classe **NativeMethods** ; Toutefois, ils sont marqués à l’aide d’un attribut spécial appelé **SuppressUnmanagedCodeSecurityAttribute**. Quand cet attribut est appliqué, le runtime n’effectue pas de parcours de pile complet pour s’assurer que tous les appelants ont l’autorisation **UnmanagedCode** . Le runtime vérifie habituellement cette autorisation au démarrage. Étant donné que la vérification n’est pas effectuée, elle peut améliorer les performances des appels à ces méthodes non managées. elle permet également au code qui a des autorisations limitées d’appeler ces méthodes.

 Toutefois, vous devez utiliser cet attribut avec beaucoup de soin. Elle peut avoir des implications graves en matière de sécurité si elle est implémentée de manière incorrecte.

 Pour plus d’informations sur la façon d’implémenter les méthodes, consultez l’exemple **NativeMethods** , l’exemple **SafeNativeMethods** et l’exemple **UnsafeNativeMethods** .

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant déclare une méthode qui enfreint cette règle. Pour corriger la violation, vous devez déplacer **RemoveDirectory** p/Invoke vers une classe appropriée conçue pour contenir uniquement les p/Invoke.

 [!code-csharp[FxCop.Design.DllImportNativeMethods#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.DllImportNativeMethods/cs/FxCop.Design.DllImportNativeMethods.cs#1)]
 [!code-vb[FxCop.Design.DllImportNativeMethods#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.DllImportNativeMethods/vb/FxCop.Design.DllImportNativeMethods.vb#1)]

## <a name="nativemethods-example"></a>Exemple NativeMethods

### <a name="description"></a>Description
 Étant donné que la classe **NativeMethods** ne doit pas être marquée à l’aide de **SuppressUnmanagedCodeSecurityAttribute**, les P/Invoke qui y sont placés requièrent l’autorisation **UnmanagedCode** . Étant donné que la plupart des applications s’exécutent à partir de l’ordinateur local et s’exécutent avec un niveau de confiance totale, ce n’est généralement pas un problème. Toutefois, si vous développez des bibliothèques réutilisables, vous devez envisager de définir une classe **SafeNativeMethods** ou **UnsafeNativeMethods** .

 L’exemple suivant montre une méthode **interaction. Beep** qui encapsule la fonction **MessageBeep** à partir de user32.dll. Le **MessageBeep** P/Invoke est placé dans la classe **NativeMethods** .

### <a name="code"></a>Code
 [!code-csharp[FxCop.Design.NativeMethods#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethods/cs/FxCop.Design.NativeMethods.cs#1)]
 [!code-vb[FxCop.Design.NativeMethods#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethods/vb/FxCop.Design.NativeMethods.vb#1)]

## <a name="safenativemethods-example"></a>Exemple SafeNativeMethods

### <a name="description"></a>Description
 Les méthodes P/Invoke qui peuvent être exposées en toute sécurité à une application et qui n’ont pas d’effets secondaires doivent être placées dans une classe nommée **SafeNativeMethods**. Vous n’avez pas à demander d’autorisations et vous n’avez pas à faire attention à l’emplacement à partir duquel elles sont appelées.

 L’exemple suivant montre une propriété **Environment. TickCount** qui encapsule la fonction **GetTickCount** à partir de kernel32.dll.

### <a name="code"></a>Code
 [!code-csharp[FxCop.Design.NativeMethodsSafe#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethodsSafe/cs/FxCop.Design.NativeMethodsSafe.cs#1)]
 [!code-vb[FxCop.Design.NativeMethodsSafe#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethodsSafe/vb/FxCop.Design.NativeMethodsSafe.vb#1)]

## <a name="unsafenativemethods-example"></a>Exemple UnsafeNativeMethods

### <a name="description"></a>Description
 Les méthodes P/Invoke qui ne peuvent pas être appelées en toute sécurité et qui peuvent provoquer des effets secondaires doivent être placées dans une classe nommée **UnsafeNativeMethods**. Ces méthodes doivent être vérifiées rigoureusement pour s’assurer qu’elles ne sont pas exposées involontairement à l’utilisateur. L’utilisation de la règle [CA2118 : Review SuppressUnmanagedCodeSecurityAttribute](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md) peut vous aider. Les méthodes doivent également avoir une autre autorisation demandée au lieu de **UnmanagedCode** lorsqu’elles sont utilisées.

 L’exemple suivant montre une méthode **Cursor. Hide** qui encapsule la fonction **ShowCursor** à partir de user32.dll.

### <a name="code"></a>Code
 [!code-csharp[FxCop.Design.NativeMethodsUnsafe#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethodsUnsafe/cs/FxCop.Design.NativeMethodsUnsafe.cs#1)]
 [!code-vb[FxCop.Design.NativeMethodsUnsafe#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.NativeMethodsUnsafe/vb/FxCop.Design.NativeMethodsUnsafe.vb#1)]

## <a name="see-also"></a>Voir aussi
 [Avertissements de conception](../code-quality/design-warnings.md)
