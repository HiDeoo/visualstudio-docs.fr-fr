---
title: 'CA1027 : marquer les enums avec FlagsAttribute | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkEnumsWithFlags
- CA1027
helpviewer_keywords:
- CA1027
- MarkEnumsWithFlags
ms.assetid: 249e882c-8cd1-4c00-a2de-7b6bdc1849ff
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 774279dd05bd14c34df7f1d450f00599812d6a5b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85544506"
---
# <a name="ca1027-mark-enums-with-flagsattribute"></a>CA1027 : Marquer les enums avec FlagsAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|MarkEnumsWithFlags|
|CheckId|CA1027|
|Category|Microsoft. Design|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause :
 Les valeurs d’une énumération publique sont des puissances de deux ou sont des combinaisons d’autres valeurs qui sont définies dans l’énumération, et l' <xref:System.FlagsAttribute?displayProperty=fullName> attribut n’est pas présent. Pour réduire les faux positifs, cette règle ne signale pas de violation pour les énumérations qui ont des valeurs contiguës.

## <a name="rule-description"></a>Description de la règle
 Une énumération est un type valeur qui définit un jeu de constantes nommées associées. S’applique <xref:System.FlagsAttribute> à une énumération lorsque ses constantes nommées peuvent être combinées de manière significative. Par exemple, considérez une énumération des jours de la semaine dans une application qui effectue le suivi des ressources de jour disponibles. Si la disponibilité de chaque ressource est encodée à l’aide de l’énumération qui est <xref:System.FlagsAttribute> présente, toute combinaison de jours peut être représentée. Sans l’attribut, un seul jour de la semaine peut être représenté.

 Pour les champs qui stockent des énumérations combinables, les valeurs d’énumération individuelles sont traitées comme des groupes de bits dans le champ. Par conséquent, ces champs sont parfois appelés *champs de bits*. Pour combiner des valeurs d’énumération pour le stockage dans un champ de bits, utilisez les opérateurs conditionnels booléens. Pour tester un champ de bits afin de déterminer si une valeur d’énumération spécifique est présente, utilisez les opérateurs logiques booléens. Pour qu’un champ de bits stocke et récupère correctement des valeurs d’énumération combinées, chaque valeur définie dans l’énumération doit être une puissance de deux. Sauf cela, les opérateurs logiques booléens ne seront pas en mesure d’extraire les valeurs d’énumération individuelles stockées dans le champ.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, ajoutez <xref:System.FlagsAttribute> à l’énumération.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Supprimez un avertissement de cette règle si vous ne souhaitez pas que les valeurs d’énumération soient combinables.

## <a name="example"></a>Exemple
 Dans l’exemple suivant, `DaysEnumNeedsFlags` est une énumération qui répond à la configuration requise pour l’utilisation de <xref:System.FlagsAttribute> , mais elle ne l’a pas. L' `ColorEnumShouldNotHaveFlag` énumération n’a pas de valeurs qui sont des puissances de deux, mais spécifie de manière incorrecte <xref:System.FlagsAttribute> . Cela ne respecte pas la règle [CA2217 : ne Marquez pas les enums avec FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md).

 [!code-csharp[FxCop.Design.EnumFlags#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumFlags/cs/FxCop.Design.EnumFlags.cs#1)]

## <a name="related-rules"></a>Règles associées
 [CA2217 : Ne marquez pas les enums avec l'attribut FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Voir aussi
 <xref:System.FlagsAttribute?displayProperty=fullName>
