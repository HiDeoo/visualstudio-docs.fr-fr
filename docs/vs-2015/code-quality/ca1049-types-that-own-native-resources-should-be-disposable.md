---
title: 'CA1049 : les types qui possèdent des ressources natives doivent être supprimables | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1049
- TypesThatOwnNativeResourcesShouldBeDisposable
helpviewer_keywords:
- TypesThatOwnNativeResourcesShouldBeDisposable
- CA1049
ms.assetid: 084e587d-0e45-4092-b767-49eed30d6a35
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 49c56b98e3be01675c2c21cd11c2961dd75f4877
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85546807"
---
# <a name="ca1049-types-that-own-native-resources-should-be-disposable"></a>CA1049 : Les types qui possèdent des ressources natives doivent être supprimables
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|TypesThatOwnNativeResourcesShouldBeDisposable|
|CheckId|CA1049|
|Category|Microsoft. Design|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause :
 Un type fait référence à un <xref:System.IntPtr?displayProperty=fullName> champ, à un <xref:System.UIntPtr?displayProperty=fullName> champ ou à un <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName> champ, mais n’implémente pas <xref:System.IDisposable?displayProperty=fullName> .

## <a name="rule-description"></a>Description de la règle
 Cette règle suppose que <xref:System.IntPtr> <xref:System.UIntPtr> les champs, et <xref:System.Runtime.InteropServices.HandleRef> stockent des pointeurs vers des ressources non managées. Les types qui allouent des ressources non managées doivent implémenter <xref:System.IDisposable> pour permettre aux appelants de libérer ces ressources à la demande et de raccourcir les durées de vie des objets qui contiennent les ressources.

 Le modèle de conception recommandé pour nettoyer les ressources non managées consiste à fournir un moyen implicite et explicite pour libérer ces ressources à l’aide de la <xref:System.Object.Finalize%2A?displayProperty=fullName> méthode et de la <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> méthode, respectivement. Le garbage collector appelle la <xref:System.Object.Finalize%2A> méthode d’un objet à un moment indéterminé une fois que l’objet est considéré comme n’étant plus accessible. Après <xref:System.Object.Finalize%2A> l’appel de, une garbage collection supplémentaire est nécessaire pour libérer l’objet. La <xref:System.IDisposable.Dispose%2A> méthode permet à l’appelant de libérer explicitement des ressources à la demande, avant que les ressources ne soient libérées si elles étaient laissées au garbage collector. Après le nettoyage des ressources non managées, <xref:System.IDisposable.Dispose%2A> doit appeler la <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> méthode pour permettre au garbage collector de savoir qu’il <xref:System.Object.Finalize%2A> n’est plus nécessaire d’appeler. cela élimine la nécessité d’un garbage collection supplémentaire et raccourcit la durée de vie de l’objet.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, implémentez <xref:System.IDisposable> .

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer sans risque un avertissement de cette règle si le type ne fait pas référence à une ressource non managée. Sinon, ne supprimez pas un avertissement de cette règle, car l’échec de l’implémentation <xref:System.IDisposable> peut entraîner l’indisponibilité ou la sous-utilisation des ressources non managées.

## <a name="example"></a>Exemple
 L’exemple suivant montre un type qui implémente <xref:System.IDisposable> pour nettoyer une ressource non managée.

 [!code-csharp[FxCop.Design.UnmanagedResources#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.UnmanagedResources/cs/FxCop.Design.UnmanagedResources.cs#1)]
 [!code-vb[FxCop.Design.UnmanagedResources#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.UnmanagedResources/vb/FxCop.Design.UnmanagedResources.vb#1)]

## <a name="related-rules"></a>Règles associées
 [CA2115 : Appelez GC.KeepAlive lorsque vous utilisez des ressources natives](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)

 [CA1816 : Appeler GC.SuppressFinalize correctement](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)

 [CA2216 : Les types pouvant être supprimés doivent déclarer un finaliseur](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

 [CA1001 : Les types qui possèdent des champs supprimables doivent être supprimables](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)

## <a name="see-also"></a>Voir aussi
  [Dispose, modèle](https://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)
