---
title: avertissements liés à l’affectation de noms
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- vs.codeanalysis.namingrules
helpviewer_keywords:
- managed code analysis warnings, naming warnings
- naming warnings
- warnings, naming
ms.assetid: f97223ce-1d39-4134-81c9-fff2c75d979b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 931c4b29bd5f90b23492cba854644435a7e99bc5
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54980880"
---
# <a name="naming-warnings"></a>avertissements liés à l’affectation de noms
Avertissements d’affectation de noms prend en charge l’adhésion aux conventions d’affectation de noms de directives de conception .NET Framework.

## <a name="in-this-section"></a>Dans cette section

|Règle|Description|
|----------|-----------------|
|[CA1700 : Ne nommez pas les valeurs enum 'Reserved'](../code-quality/ca1700-do-not-name-enum-values-reserved.md)|Cette règle suppose qu'un membre de l'énumération dont le nom contient le terme "reserved" n'est pas utilisé actuellement, mais constitue un espace réservé à renommer ou à supprimer dans une version ultérieure. Renommer ou supprimer un membre constitue une modification avec rupture.|
|[CA1713 : Événements ne doivent pas être préfixe before ou after](../code-quality/ca1713-events-should-not-have-before-or-after-prefix.md)|Le nom d'un événement commence par « Before » ou « After ». Pour nommer des événements associés déclenchés dans une séquence spécifique, utilisez le présent ou le passé pour indiquer la position relative dans la séquence d'actions.|
|[CA1714 : Énumérations d’indicateurs doivent avoir des noms au pluriel](../code-quality/ca1714-flags-enums-should-have-plural-names.md)|Une énumération publique comporte l’attribut System.FlagsAttribute et son nom ne termine pas par « s ». Les types marqués avec FlagsAttribute ont des noms au pluriel, car l’attribut indique que plusieurs valeurs peuvent être spécifiées.|
|[CA1704 : Les identificateurs doivent être correctement orthographiés](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)|Le nom d'un identificateur visible de l'extérieur contient un ou plusieurs mots qui ne sont pas reconnus par la bibliothèque du vérificateur d'orthographe Microsoft.|
|[CA1708 : Les identificateurs doivent différer par leur casse](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)|Les identificateurs des espaces de noms, types, membres et paramètres ne peuvent pas différer uniquement par la casse car les langages qui ciblent le Common Language Runtime ne sont pas tenus de respecter celle-ci.|
|[CA1715 : Les identificateurs doivent avoir un préfixe correct](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)|Le nom d’une interface extérieurement visible ne commence pas par un « I » majuscule.  Le nom d’un paramètre de type générique sur un type visible de l’extérieur ou de la méthode ne commence pas par un « T » majuscule.|
|[CA1720 : Identificateurs ne doivent pas contenir les noms de types](../code-quality/ca1720-identifiers-should-not-contain-type-names.md)|Le nom d'un paramètre dans un membre extérieurement visible contient un nom de type de données, ou le nom d'un membre extérieurement visible contient un nom de type de données spécifique à une langue.|
|[CA1722 : Les identificateurs ne doivent pas porter un préfixe incorrect](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)|Par convention, seuls certains éléments de programmation présentent des noms qui commencent par un préfixe spécifique.|
|[CA1711 : Les identificateurs ne doivent pas porter un suffixe incorrect](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)|Par convention, seuls les noms des types qui étendent certains types de base ou qui implémentent certaines interfaces, ou les types dérivés de ces types, doivent se terminer par des suffixes réservés spécifiques. Les autres noms de types ne doivent pas utiliser ces suffixes réservés.|
|[CA1717 : Uniquement des enums FlagsAttribute doivent avoir des noms au pluriel](../code-quality/ca1717-only-flagsattribute-enums-should-have-plural-names.md)|Selon les conventions d'attribution de nom, un nom au pluriel pour une énumération indique que plusieurs valeurs de l'énumération peuvent être spécifiées simultanément.|
|[CA1725 : Les noms de paramètre doivent correspondre à la déclaration de base](../code-quality/ca1725-parameter-names-should-match-base-declaration.md)|La désignation cohérente des paramètres dans une hiérarchie de substitution augmente la facilité d'utilisation des substitutions de méthode. Un nom de paramètre dans une méthode dérivée qui diffère du nom dans la déclaration de base peut créer une confusion pour déterminer si la méthode est une substitution de la méthode de base ou une nouvelle surcharge de la méthode.|
|[CA1719 : Noms de paramètres ne doivent pas correspondre aux noms de membres](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)|Un nom de paramètre doit véhiculer la signification d’un paramètre et un nom de membre doit véhiculer la signification d’un membre. Un design où ceux-ci sont identiques est rare. Donner à un paramètre le même que son membre n'est pas une méthode intuitive et rend la bibliothèque difficile à utiliser.|
|[CA1701 : Mots composés de chaînes de ressources doivent être correcte](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)|Chaque mot dans la chaîne de ressource est fractionné en jetons basés sur la casse. Chaque combinaison de deux jetons contiguë est vérifiée par la bibliothèque du correcteur orthographique Microsoft. S'il est reconnu, le mot produit une violation de la règle.|
|[CA1703 : Chaînes de ressources doivent être correcte](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)|Une chaîne de ressource contient un ou plusieurs mots qui ne sont pas reconnus par la bibliothèque du vérificateur d'orthographe Microsoft.|
|[CA1724 : Noms de types ne doivent pas correspondre aux espaces de noms](../code-quality/ca1724-type-names-should-not-match-namespaces.md)|Noms de types ne doivent pas correspondre aux noms des espaces de noms définis dans la bibliothèque de classes .NET Framework. Violation de cette règle peut réduire la facilité d’utilisation de la bibliothèque.|
|[CA1707 : Identificateurs ne doivent pas contenir de traits de soulignement](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)|Par convention, les noms d'identificateurs ne contiennent pas de trait de soulignement (_). Cette règle vérifie les espaces de noms, types, membres et paramètres.|
|[CA1721 : Noms de propriétés ne doivent pas correspondre à des méthodes get](../code-quality/ca1721-property-names-should-not-match-get-methods.md)|Le nom d'un membre public ou protégé commence par « Get ». Sinon, il correspond au nom d'une propriété publique ou protégée. Les méthodes et propriétés « Get » doivent porter des noms distinguant clairement leur fonction.|
|[CA1716 : Les identificateurs ne doivent pas correspondre aux mots clés](../code-quality/ca1716-identifiers-should-not-match-keywords.md)|Un nom d'espace de noms ou un nom de type correspond à un mot clé réservé dans un langage de programmation. Les identificateurs des espaces de noms et des types ne doivent pas correspondre aux mots clés définis par les langages qui ciblent le Common Language Runtime.|
|[CA1726 : Utilisez les termes préférés](../code-quality/ca1726-use-preferred-terms.md)|Le nom d'un identificateur visible de l'extérieur contient un terme pour lequel un autre terme par défaut existe. Le nom peut également inclure le terme « Indicateur » ou « Indicateurs ».|
|[CA1709 : Identificateurs doivent être correcte](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)|Par convention, les noms de paramètre utilisent mixte casse et espace de noms, le type et les noms de membres Pascal casse.|
|[CA1702 : Mots composés doivent être correcte](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)|Le nom d'un identificateur contient plusieurs mots et au moins l'un des mots semble être un mot composé qui ne présente pas une casse correcte.|
|[CA1712 : N’ajoutez pas de valeurs d’énumération avec le nom de type préfixe](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)|Noms des membres de l’énumération ne sont pas préfixés par le nom de type, car les informations de type sont censées être fournis par les outils de développement.|
|[CA1710 : Les identificateurs doivent avoir un suffixe correct](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)|Par convention, les noms des types qui étendent certains types de base ou qui implémentent certaines interfaces, ou les types dérivés de ces types, présentent un suffixe qui est associé au type de base ou interface.|