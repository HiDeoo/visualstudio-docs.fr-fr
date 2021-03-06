---
title: 'Ca1702 : la casse des mots composés doit être correcte | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
helpviewer_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
ms.assetid: 05481245-7ad8-48c3-a456-3aa44b6160a6
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: f9dc15cec4012d2b63eb5f21c25bd709961c95c8
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85544077"
---
# <a name="ca1702-compound-words-should-be-cased-correctly"></a>CA1702 : La casse des mots composés doit être correcte
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour obtenir la documentation la plus récente sur Visual Studio, consultez [ca1702 : la casse des mots composés doit être correcte](/visualstudio/code-quality/ca1702-compound-words-should-be-cased-correctly).

|Élément|Valeur|
|-|-|
|TypeName|CompoundWordsShouldBeCasedCorrectly|
|CheckId|CA1702|
|Category|Microsoft. Naming|
|Modification avec rupture|Avec rupture-en cas de déclenchement sur les assemblys.<br /><br /> Sans rupture-en cas de déclenchement sur les paramètres de type.|

## <a name="cause"></a>Cause
 Le nom d’un identificateur contient plusieurs mots et au moins l’un des mots semble être un mot composé qui ne respecte pas la casse.

## <a name="rule-description"></a>Description de la règle
 Le nom de l’identificateur est fractionné en mots basés sur la casse. Chaque combinaison contiguë à deux mots est vérifiée par la bibliothèque du vérificateur d’orthographe Microsoft. S’il est reconnu, l’identificateur produit une violation de la règle. Les exemples de mots composés qui provoquent une violation sont « CheckSum » et « multipart », qui doivent respecter la casse « checksum » et « multipart », respectivement. En raison de l’utilisation courante précédente, plusieurs exceptions sont intégrées à la règle, et plusieurs mots uniques sont signalés, tels que « Toolbar » et « filename », qui doivent respecter la casse de deux mots distincts (dans ce cas, « ToolBar » et « FileName »).

 Les conventions d’affectation de noms fournissent une recherche commune pour les bibliothèques qui ciblent le common language runtime. Cela réduit la courbe d’apprentissage requise pour les nouvelles bibliothèques logicielles et augmente la confiance des clients dans la mesure où la bibliothèque a été développée par une personne ayant une expertise dans le développement de code géré.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Modifiez le nom pour qu’il respecte la casse.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer sans risque un avertissement de cette règle si les deux parties du mot composé sont reconnues par le dictionnaire d’orthographe et si l’objectif est d’utiliser deux mots.

## <a name="related-rules"></a>Règles associées
 [CA1701 : La casse des mots composés de la chaîne de ressources doit être correcte](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)

 [CA1709 : La casse des identificateurs doit être correcte](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

 [CA1708 : Les identificateurs ne doivent pas différer uniquement par leur casse](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

## <a name="see-also"></a>Voir aussi
 Conventions de mise en [majuscules](https://msdn.microsoft.com/library/4c4ea526-9203-486f-b72d-29d61c5b3c6d) des [directives de nommage](https://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3)
