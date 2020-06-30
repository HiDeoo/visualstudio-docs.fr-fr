---
title: 'Ca1305 : spécifier IFormatProvider | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyIFormatProvider
- CA1305
helpviewer_keywords:
- CA1305
- SpecifyIFormatProvider
ms.assetid: fb34ed9a-4eab-47cc-8eef-3068a4a1397e
caps.latest.revision: 24
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 025d76f8e946dd3021141d6736c6b4bd40d57170
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85539084"
---
# <a name="ca1305-specify-iformatprovider"></a>CA1305 : Spécifier IFormatProvider
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|SpecifyIFormatProvider|
|CheckId|CA1305|
|Category|Microsoft. Globalization|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Une méthode ou un constructeur appelle un ou plusieurs membres qui ont des surcharges qui acceptent un <xref:System.IFormatProvider?displayProperty=fullName> paramètre, et la méthode ou le constructeur n’appelle pas la surcharge qui prend le <xref:System.IFormatProvider> paramètre. Cette règle ignore les appels aux [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] méthodes documentées comme ignorant le <xref:System.IFormatProvider> paramètre et en plus des méthodes suivantes :

- <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>

- <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=fullName>

- <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>

## <a name="rule-description"></a>Description de la règle
 Lorsqu’un <xref:System.Globalization.CultureInfo?displayProperty=fullName> <xref:System.IFormatProvider> objet ou n’est pas fourni, la valeur par défaut fournie par le membre surchargé peut ne pas avoir l’effet souhaité dans tous les paramètres régionaux. En outre, [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] les membres choisissent la culture et la mise en forme par défaut en fonction des hypothèses qui peuvent ne pas être correctes pour votre code. Pour vous assurer que le code fonctionne comme prévu pour vos scénarios, vous devez fournir des informations spécifiques à la culture en respectant les instructions suivantes :

- Si la valeur est affichée à l’utilisateur, utilisez la culture actuelle. Consultez <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>.

- Si la valeur est stockée et accessible par le logiciel (conservée dans un fichier ou une base de données), utilisez la culture dite indifférente. Consultez <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.

- Si vous ne connaissez pas la destination de la valeur, faites en sorte que le consommateur de données ou le fournisseur spécifie la culture.

  Notez que <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> est utilisé uniquement pour récupérer des ressources localisées à l’aide d’une instance de la <xref:System.Resources.ResourceManager?displayProperty=fullName> classe.

  Même si le comportement par défaut du membre surchargé est adapté à vos besoins, il est préférable d’appeler explicitement la surcharge spécifique à la culture afin que votre code soit documenté automatiquement et plus facile à gérer.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, utilisez la surcharge qui prend un <xref:System.Globalization.CultureInfo> ou <xref:System.IFormatProvider> et spécifiez l’argument en fonction des indications répertoriées précédemment.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer sans risque un avertissement de cette règle lorsqu’il est certain que le fournisseur de format/culture par défaut est le bon choix et où la maintenabilité du code n’est pas une priorité de développement importante.

## <a name="example"></a>Exemple
 Dans l’exemple suivant, `BadMethod` provoque deux violations de cette règle. `GoodMethod`corrige la première violation en passant la culture dite indifférente à <xref:System.String.Compare%2A> et corrige la deuxième violation en passant la culture actuelle à, <xref:System.String.ToLower%2A> car `string3` est affiché à l’utilisateur.

 [!code-csharp[FxCop.Globalization.CultureInfo#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.CultureInfo/cs/FxCop.Globalization.CultureInfo.cs#1)]

## <a name="example"></a>Exemple
 L’exemple suivant montre l’effet de la culture actuelle sur la valeur par défaut <xref:System.IFormatProvider> qui est sélectionnée par le <xref:System.DateTime> type.

 [!code-csharp[FxCop.Globalization.IFormatProvider#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.IFormatProvider/cs/FxCop.Globalization.IFormatProvider.cs#1)]

 Cet exemple produit la sortie suivante.

 **6/4/1900 12:15:12 PM** 
 **06/04/1900 12:15:12**
## <a name="related-rules"></a>Règles associées
 [CA1304 : Spécifier CultureInfo](../code-quality/ca1304-specify-cultureinfo.md)

## <a name="see-also"></a>Voir aussi
 [PLUME : utilisation de la classe CultureInfo](https://msdn.microsoft.com/d4329e34-64c3-4d1e-8c73-5b0ee626ba7a)
