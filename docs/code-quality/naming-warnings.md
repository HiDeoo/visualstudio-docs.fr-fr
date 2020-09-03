---
title: avertissements liés à l’affectation de noms
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.namingrules
helpviewer_keywords:
- managed code analysis warnings, naming warnings
- naming warnings
- warnings, naming
ms.assetid: f97223ce-1d39-4134-81c9-fff2c75d979b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f6d1e40b809f27292f2a808458584837913d881f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75587301"
---
# <a name="naming-warnings"></a>avertissements liés à l’affectation de noms

Les avertissements de nommage prennent en charge l’adhésion aux conventions de nommage des règles de conception .NET.

## <a name="in-this-section"></a>Dans cette section

|Règle|Description|
|----------|-----------------|
|[CA1700 : Ne nommez pas les valeurs enum 'Reserved'](../code-quality/ca1700.md)|Cette règle suppose qu'un membre de l'énumération dont le nom contient le terme "reserved" n'est pas utilisé actuellement, mais constitue un espace réservé à renommer ou à supprimer dans une version ultérieure. Renommer ou supprimer un membre constitue une modification avec rupture.|
|[CA1713 : Les événements ne doivent pas être munis d'un préfixe Before ou After](../code-quality/ca1713.md)|Le nom d'un événement commence par « Before » ou « After ». Pour nommer des événements associés déclenchés dans une séquence spécifique, utilisez le présent ou le passé pour indiquer la position relative dans la séquence d'actions.|
|[CA1714 : Les noms des enums Flags doivent être au pluriel](../code-quality/ca1714.md)|Une énumération publique a l’attribut System. FlagsAttribute et son nom ne se termine pas par « s ». Les types marqués avec FlagsAttribute ont des noms au pluriel, car l’attribut indique qu’il est possible de spécifier plusieurs valeurs.|
|[CA1704 : L'orthographe des identificateurs doit être correcte](../code-quality/ca1704.md)|Le nom d'un identificateur visible de l'extérieur contient un ou plusieurs mots qui ne sont pas reconnus par la bibliothèque du vérificateur d'orthographe Microsoft.|
|[CA1708 : Les identificateurs ne doivent pas différer uniquement par leur casse](../code-quality/ca1708.md)|Les identificateurs des espaces de noms, types, membres et paramètres ne peuvent pas différer uniquement par la casse car les langages qui ciblent le Common Language Runtime ne sont pas tenus de respecter celle-ci.|
|[CA1715 : Les identificateurs doivent être dotés d'un préfixe correct](../code-quality/ca1715.md)|Le nom d’une interface extérieurement visible ne commence pas par un « I » majuscule.  Le nom d’un paramètre de type générique sur un type ou une méthode extérieurement visible ne commence pas par un « T » majuscule.|
|[CA1720 : Les identificateurs ne doivent pas contenir de noms de types](../code-quality/ca1720.md)|Le nom d'un paramètre dans un membre extérieurement visible contient un nom de type de données, ou le nom d'un membre extérieurement visible contient un nom de type de données spécifique à une langue.|
|[CA1722 : Les identificateurs ne doivent pas porter un préfixe incorrect](../code-quality/ca1722.md)|Par convention, seuls certains éléments de programmation présentent des noms qui commencent par un préfixe spécifique.|
|[CA1711 : Les identificateurs ne doivent pas porter un suffixe incorrect](../code-quality/ca1711.md)|Par convention, seuls les noms des types qui étendent certains types de base ou qui implémentent certaines interfaces, ou les types dérivés de ces types, doivent se terminer par des suffixes réservés spécifiques. Les autres noms de types ne doivent pas utiliser ces suffixes réservés.|
|[CA1717 : Seuls les noms des enums FlagsAttribute doivent être au pluriel](../code-quality/ca1717.md)|Selon les conventions d'attribution de nom, un nom au pluriel pour une énumération indique que plusieurs valeurs de l'énumération peuvent être spécifiées simultanément.|
|[CA1725 : Les noms des paramètres doivent correspondre à la déclaration de base](../code-quality/ca1725.md)|La désignation cohérente des paramètres dans une hiérarchie de substitution augmente la facilité d'utilisation des substitutions de méthode. Un nom de paramètre dans une méthode dérivée qui diffère du nom dans la déclaration de base peut créer une confusion pour déterminer si la méthode est une substitution de la méthode de base ou une nouvelle surcharge de la méthode.|
|[CA1719 : Les noms des paramètres ne doivent pas être identiques aux noms des membres](../code-quality/ca1719.md)|Un nom de paramètre doit communiquer la signification d’un paramètre, et un nom de membre doit communiquer la signification d’un membre. Un design où ceux-ci sont identiques est rare. Donner à un paramètre le même que son membre n'est pas une méthode intuitive et rend la bibliothèque difficile à utiliser.|
|[CA1701 : La casse des mots composés de la chaîne de ressources doit être correcte](../code-quality/ca1701.md)|Chaque mot de la chaîne de ressource est fractionné en jetons basés sur la casse. Chaque combinaison de deux jetons contiguë est vérifiée par la bibliothèque du correcteur orthographique Microsoft. S'il est reconnu, le mot produit une violation de la règle.|
|[CA1703 : L'orthographe des chaînes de ressources doit être correcte](../code-quality/ca1703.md)|Une chaîne de ressource contient un ou plusieurs mots qui ne sont pas reconnus par la bibliothèque du vérificateur d'orthographe Microsoft.|
|[CA1724 : Les noms de types ne doivent pas être identiques aux espaces de noms](../code-quality/ca1724.md)|Les noms de types ne doivent pas correspondre aux noms des espaces de noms .NET. La violation de cette règle peut réduire l’utilisation de la bibliothèque.|
|[CA1707 : Les identificateurs ne doivent pas contenir de traits de soulignement](../code-quality/ca1707.md)|Par convention, les noms d'identificateurs ne contiennent pas de trait de soulignement (_). Cette règle vérifie les espaces de noms, types, membres et paramètres.|
|[CA1721 : Les noms des propriétés ne doivent pas être identiques à ceux des méthodes Get](../code-quality/ca1721.md)|Le nom d'un membre public ou protégé commence par « Get ». Sinon, il correspond au nom d'une propriété publique ou protégée. Les méthodes et propriétés « Get » doivent porter des noms distinguant clairement leur fonction.|
|[CA1716 : Les identificateurs ne doivent pas correspondre à des mots clés](../code-quality/ca1716.md)|Un nom d'espace de noms ou un nom de type correspond à un mot clé réservé dans un langage de programmation. Les identificateurs des espaces de noms et des types ne doivent pas correspondre aux mots clés définis par les langages qui ciblent le Common Language Runtime.|
|[CA1726 : Utilisez les termes par défaut](../code-quality/ca1726.md)|Le nom d'un identificateur visible de l'extérieur contient un terme pour lequel un autre terme par défaut existe. Le nom peut également inclure le terme « Indicateur » ou « Indicateurs ».|
|[CA1709 : La casse des identificateurs doit être correcte](../code-quality/ca1709.md)|Par Convention, les noms de paramètres utilisent la casse mixte et les noms d’espaces de noms, de types et de membres utilisent la casse Pascal.|
|[CA1702 : La casse des mots composés doit être correcte](../code-quality/ca1702.md)|Le nom d'un identificateur contient plusieurs mots et au moins l'un des mots semble être un mot composé qui ne présente pas une casse correcte.|
|[CA1712 : N'ajoutez pas le nom de type en guise de préfixe à des valeurs enum](../code-quality/ca1712.md)|Les noms des membres de l’énumération n’ont pas le préfixe du nom de type, car les informations de type doivent être fournies par les outils de développement.|
|[CA1710 : Les identificateurs doivent être dotés d'un suffixe correct](../code-quality/ca1710.md)|Par Convention, les noms des types qui étendent certains types de base ou qui implémentent certaines interfaces, ou des types dérivés de ces types, ont un suffixe associé à l’interface ou au type de base.|
