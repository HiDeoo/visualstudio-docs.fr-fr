---
title: 'CA1404 : appeler GetLastError immédiatement après P-Invoke | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
helpviewer_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
ms.assetid: 52ae9eff-50f9-4b2f-8039-ca7e49fba88e
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 54ac9a4d56136d9e981ae038a0b219aa4cb4774e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85544493"
---
# <a name="ca1404-call-getlasterror-immediately-after-pinvoke"></a>CA1404 : Appeler GetLastError immédiatement après P/Invoke
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|CallGetLastErrorImmediatelyAfterPInvoke|
|CheckId|CA1404|
|Category|Microsoft. Interoperability|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause :
 Un appel est fait à la <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A?displayProperty=fullName> méthode ou à la fonction Win32 équivalente `GetLastError` , et l’appel qui vient juste avant n’est pas une méthode d’appel de code non managé.

## <a name="rule-description"></a>Description de la règle
 Une méthode d’appel de plateforme accède au code non managé et est définie à l’aide du `Declare` mot clé dans [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ou de l' <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> attribut. En général, en cas d’échec, les fonctions non managées appellent la `SetLastError` fonction Win32 pour définir un code d’erreur associé à l’échec. L’appelant de la fonction failed appelle la `GetLastError` fonction Win32 pour récupérer le code d’erreur et déterminer la cause de l’échec. Le code d’erreur est conservé par thread et remplacé par l’appel suivant à `SetLastError` . Après un appel à une méthode d’appel de plateforme qui a échoué, le code managé peut récupérer le code d’erreur en appelant la <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> méthode. Étant donné que le code d’erreur peut être remplacé par des appels internes d’autres méthodes de la bibliothèque de classes managée, la `GetLastError` <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> méthode ou doit être appelée immédiatement après l’appel de la méthode d’appel de code non managé.

 La règle ignore les appels aux membres managés suivants lorsqu’ils se produisent entre l’appel à la méthode d’appel de code non managé et l’appel à <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> . Ces membres ne modifient pas le code d’erreur et sont utiles pour déterminer la réussite de certains appels de méthode d’appel de code non managé.

- <xref:System.IntPtr.Zero?displayProperty=fullName>

- <xref:System.IntPtr.op_Equality%2A?displayProperty=fullName>

- <xref:System.IntPtr.op_Inequality%2A?displayProperty=fullName>

- <xref:System.Runtime.InteropServices.SafeHandle.IsInvalid%2A?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, déplacez l’appel vers <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> afin qu’il suive immédiatement l’appel à la méthode d’appel de code non managé.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer sans risque un avertissement de cette règle si le code entre l’appel de la méthode d’appel de code non managé et l’appel de la <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> méthode ne peut pas explicitement ou implicitement entraîner la modification du code d’erreur.

## <a name="example"></a>Exemple
 L’exemple suivant montre une méthode qui enfreint la règle et une méthode qui satisfait la règle.

 [!code-csharp[FxCop.Interoperability.LastErrorPInvoke#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LastErrorPInvoke/cs/FxCop.Interoperability.LastErrorPInvoke.cs#1)]
 [!code-vb[FxCop.Interoperability.LastErrorPInvoke#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LastErrorPInvoke/vb/FxCop.Interoperability.LastErrorPInvoke.vb#1)]

## <a name="related-rules"></a>Règles associées
 [CA1060 : déplacer les P/Invoke vers une classe NativeMethods](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)

 [CA1400 : des points d’entrée P/Invoke doivent exister](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)

 [Ca1401 : les P/Invoke ne doivent pas être visibles](../code-quality/ca1401-p-invokes-should-not-be-visible.md)

 [CA2101 : spécifiez le marshaling pour les arguments de chaîne P/Invoke](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)

 [CA2205 : Utilisez des équivalents managés de l'API Win32](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)
