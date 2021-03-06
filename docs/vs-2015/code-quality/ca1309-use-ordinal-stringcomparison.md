---
title: 'CA1309 : utiliser StringComparison avec la position ordinale | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseOrdinalStringComparison
- CA1309
helpviewer_keywords:
- UseOrdinalStringComparison
- CA1309
ms.assetid: 19be0854-cb6e-4efd-a4c8-a5c1fc6f7a71
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: be60d2a1dcb769a0b7a8574984de3d288bf57af4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85538877"
---
# <a name="ca1309-use-ordinal-stringcomparison"></a>CA1309 : Utiliser StringComparison avec la valeur Ordinal
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|UseOrdinalStringComparison|
|CheckId|CA1309|
|Category|Microsoft. Globalization|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause :
 Une opération de comparaison de chaînes non linguistique ne définit pas le <xref:System.StringComparison> paramètre sur **ordinal** ou **OrdinalIgnoreCase**.

## <a name="rule-description"></a>Description de la règle
 De nombreuses opérations de chaînes, les plus importantes des <xref:System.String.Compare%2A?displayProperty=fullName> <xref:System.String.Equals%2A?displayProperty=fullName> méthodes et, fournissent désormais une surcharge qui accepte une <xref:System.StringComparison?displayProperty=fullName> valeur d’énumération en tant que paramètre.

 Lorsque vous spécifiez **StringComparison. Ordinal** ou **StringComparison. OrdinalIgnoreCase**, la comparaison de chaînes sera non linguistique. Autrement dit, les fonctionnalités spécifiques au langage naturel sont ignorées lorsque des décisions de comparaison sont prises. Cela signifie que les décisions sont basées sur des comparaisons d’octets simples et ignorent la casse ou les tables d’équivalences paramétrables par la culture. Par conséquent, en affectant explicitement au paramètre la valeur **StringComparison. Ordinal** ou **StringComparison. OrdinalIgnoreCase**, votre code gagne souvent en vitesse, augmente l’exactitude et devient plus fiable.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, remplacez la méthode de comparaison de chaînes par une surcharge qui accepte l' <xref:System.StringComparison?displayProperty=fullName> énumération en tant que paramètre et spécifiez **ordinal** ou **OrdinalIgnoreCase**. Par exemple, remplacez `String.Compare(str1, str2)` par `String.Compare(str1, str2, StringComparison.Ordinal)`.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer sans risque un avertissement de cette règle lorsque la bibliothèque ou l’application est destinée à un public local limité ou lorsque la sémantique de la culture actuelle doit être utilisée.

## <a name="see-also"></a>Voir aussi
 [Avertissements de globalisation](../code-quality/globalization-warnings.md) [CA1307 : spécifier StringComparison](../code-quality/ca1307-specify-stringcomparison.md)
