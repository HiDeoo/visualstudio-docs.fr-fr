---
title: 'CA2205 : utilisez des équivalents managés de l’API Win32 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
helpviewer_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
ms.assetid: 1c65ab59-3e50-4488-a727-3969c7f6cbe4
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 85e27ab04ca81f5513a0b09bc41548f4a7c2430d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85547678"
---
# <a name="ca2205-use-managed-equivalents-of-win32-api"></a>CA2205 : Utilisez des équivalents managés de l'API Win32
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|UseManagedEquivalentsOfWin32Api|
|CheckId|CA2205|
|Category|Microsoft. usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause :
 Une méthode d’appel de code non managé est définie et une méthode avec la fonctionnalité équivalente existe dans la [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] bibliothèque de classes.

## <a name="rule-description"></a>Description de la règle
 Une méthode d’appel de code non managé est utilisée pour appeler une fonction DLL non managée et est définie à l’aide de l' <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> attribut, ou du `Declare` mot clé dans Visual Basic. Une méthode d’appel de code non managé définie de manière incorrecte peut entraîner des exceptions d’exécution en raison de problèmes tels qu’une fonction mal nommée, un mappage défectueux de types de données de paramètres et de valeurs de retour, ainsi que des spécifications de champ incorrectes, telles que la Convention d’appel et le jeu de caractères. S’il est disponible, il est généralement plus simple et moins sujette aux erreurs d’appeler la méthode managée équivalente que de définir et d’appeler directement la méthode non managée. L’appel d’une méthode d’appel de code non managé peut également entraîner des problèmes de sécurité supplémentaires qui doivent être traités.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, remplacez l’appel à la fonction non managée par un appel à son équivalent managé.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Supprimez un avertissement de cette règle si la méthode de remplacement suggérée ne fournit pas les fonctionnalités nécessaires.

## <a name="example"></a>Exemple
 L’exemple suivant montre une définition de méthode d’appel de code non managé qui enfreint la règle. En outre, les appels à la méthode d’appel de code non managé et à la méthode managée équivalente sont affichés.

 [!code-csharp[FxCop.Usage.ManagedEquivalents#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.ManagedEquivalents/cs/FxCop.Usage.ManagedEquivalents.cs#1)]
 [!code-vb[FxCop.Usage.ManagedEquivalents#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.ManagedEquivalents/vb/FxCop.Usage.ManagedEquivalents.vb#1)]

## <a name="related-rules"></a>Règles associées
 [CA1404 : appeler GetLastError immédiatement après P/Invoke](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)

 [CA1060 : déplacer les P/Invoke vers une classe NativeMethods](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)

 [CA1400 : des points d’entrée P/Invoke doivent exister](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)

 [Ca1401 : les P/Invoke ne doivent pas être visibles](../code-quality/ca1401-p-invokes-should-not-be-visible.md)

 [CA2101 : spécifiez le marshaling pour les arguments de chaîne P/Invoke](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)
