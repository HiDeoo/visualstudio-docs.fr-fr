---
title: 'CA1709 : la casse des identificateurs doit être correcte | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IdentifiersShouldBeCasedCorrectly
- CA1709
helpviewer_keywords:
- CA1709
- IdentifiersShouldBeCasedCorrectly
ms.assetid: f633d1a7-4ca4-40ae-b207-ec571c5fb083
caps.latest.revision: 30
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 14c50ed94f05401cc5575af9f8b98472c35b261d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85543999"
---
# <a name="ca1709-identifiers-should-be-cased-correctly"></a>CA1709 : La casse des identificateurs doit être correcte
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour obtenir la dernière documentation sur Visual Studio, consultez [CA1709 : la casse des identificateurs doit être correcte](/visualstudio/code-quality/ca1709-identifiers-should-be-cased-correctly).

|Élément|Valeur|
|-|-|
|TypeName|IdentifiersShouldBeCasedCorrectly|
|CheckId|CA1709|
|Category|Microsoft. Naming|
|Modification avec rupture|Avec rupture-en cas de déclenchement sur les assemblys, les espaces de noms, les types, les membres et les paramètres.<br /><br /> Sans rupture-en cas de déclenchement sur des paramètres de type générique.|

## <a name="cause"></a>Cause
 Le nom d’un identificateur ne respecte pas la casse.

 \- ou -

 Le nom d’un identificateur contient un acronyme à deux lettres et la deuxième lettre en minuscules.

 \- ou -

 Le nom d’un identificateur contient un acronyme de trois lettres majuscules ou plus.

## <a name="rule-description"></a>Description de la règle
 Les conventions d’affectation de noms fournissent une recherche commune pour les bibliothèques qui ciblent le common language runtime. Cela réduit la courbe d’apprentissage requise pour les nouvelles bibliothèques logicielles et augmente la confiance des clients dans la mesure où la bibliothèque a été développée par une personne ayant une expertise dans le développement de code géré.

 Par Convention, les noms de paramètres utilisent la casse mixte. les noms d’espaces de noms, de types et de membres utilisent la casse Pascal. Dans un nom à casse mixte, la première lettre est en minuscules et la première lettre de tous les mots restants dans le nom est en majuscules. « PacketSniffer », « ioFile » et « fatalErrorCode » sont des exemples de noms à casse mixte : « », « » et «». Dans un nom en respectant la casse Pascal, la première lettre est en majuscule et la première lettre des mots restants dans le nom est en majuscules. « PacketSniffer », « IOFile » et « FatalErrorCode » sont des exemples de noms en respectant la casse Pascal.

 Cette règle fractionne le nom en mots en fonction de la casse et vérifie les mots à deux lettres par rapport à une liste de mots à deux lettres communs, tels que « in » ou « My ». Si aucune correspondance n’est trouvée, le mot est supposé être un acronyme. En outre, cette règle suppose qu’elle a trouvé un acronyme lorsque le nom contient quatre lettres majuscules dans une ligne ou trois lettres majuscules dans une ligne à la fin du nom.

 Par Convention, les acronymes à deux lettres utilisent toutes les lettres majuscules, et les acronymes de trois caractères ou plus utilisent la casse Pascal. Les exemples suivants utilisent cette Convention d’affectation de noms : « DB », « CR », « CPA » et « ECMA ». Les exemples suivants enfreignent la Convention : 'io', 'XML’et’DoD', et pour les noms sans paramètre, 'XP’et’Cpl'.

 'ID’est à casse spéciale pour provoquer une violation de cette règle. 'ID’n’est pas un acronyme, mais il s’agit d’une abréviation pour’identification'.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Modifiez le nom pour qu’il respecte la casse.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer sans risque cet avertissement si vous avez vos propres conventions d’affectation de noms, ou si l’identificateur représente un nom approprié, par exemple, le nom d’une société ou d’une technologie.

 Vous pouvez également ajouter des termes, des abréviations et des acronymes spécifiques à un dictionnaire personnalisé d’analyse du code. Les termes spécifiés dans le dictionnaire personnalisé ne provoquent pas de violations de cette règle. Pour plus d’informations, consultez [Comment : personnaliser le dictionnaire d’analyse du code](../code-quality/how-to-customize-the-code-analysis-dictionary.md)

## <a name="related-rules"></a>Règles associées
 [CA1708 : Les identificateurs ne doivent pas différer uniquement par leur casse](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
