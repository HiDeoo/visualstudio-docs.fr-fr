---
title: 'CA1065 : ne levez pas d’exceptions dans des emplacements inattendus | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1065
- DoNotRaiseExceptionsInUnexpectedLocations
helpviewer_keywords:
- DoNotRaiseExceptionsInUnexpectedLocations
- CA1065
ms.assetid: 4e1bade4-4ca2-4219-abc3-c7b2d741e157
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: ddfc95d27179f48aef9444819cc0437a3143d5a0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85539254"
---
# <a name="ca1065-do-not-raise-exceptions-in-unexpected-locations"></a>CA1065 : Ne pas lever d'exceptions dans les emplacements inattendus
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|DoNotRaiseExceptionsInUnexpectedLocations|
|CheckId|CA1065|
|Category|Microsoft. Design|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause :
 Une méthode dont l'objet n'est pas de lever des exceptions lève une exception.

## <a name="rule-description"></a>Description de la règle
 Les méthodes qui ne sont pas censées lever des exceptions peuvent être classées comme suit :

- Méthodes d’extraction de propriété

- Méthodes d’accesseur d’événement

- Equals (méthodes)

- Méthodes GetHashCode

- Méthodes ToString

- Constructeurs statiques

- Finaliseurs

- Méthodes dispose

- Opérateurs d'égalité

- Opérateurs de cast implicite

  Les sections suivantes décrivent ces types de méthode.

### <a name="property-get-methods"></a>Méthodes d’extraction de propriété
 Les propriétés sont essentiellement des champs intelligents. Par conséquent, ils doivent se comporter comme un champ autant que possible. Les champs ne lèvent pas d’exceptions et aucune propriété ne doit l’être. Si vous avez une propriété qui lève une exception, pensez à en faire une méthode.

 Les exceptions suivantes peuvent être levées à partir d’une méthode d’extraction de propriété :

- <xref:System.InvalidOperationException?displayProperty=fullName> et tous les dérivés (y compris <xref:System.ObjectDisposedException?displayProperty=fullName> )

- <xref:System.NotSupportedException?displayProperty=fullName> et tous les dérivés

- <xref:System.ArgumentException?displayProperty=fullName> (uniquement à partir d’une récupération indexée)

- <xref:System.Collections.Generic.KeyNotFoundException> (uniquement à partir d’une récupération indexée)

### <a name="event-accessor-methods"></a>Méthodes d’accesseur d’événement
 Les accesseurs d’événement doivent être des opérations simples qui ne lèvent pas d’exceptions. Un événement ne doit pas lever d’exception lorsque vous essayez d’ajouter ou de supprimer un gestionnaire d’événements.

 Les exceptions suivantes peuvent être levées à partir d’un événement accesor :

- <xref:System.InvalidOperationException?displayProperty=fullName> et tous les dérivés (y compris <xref:System.ObjectDisposedException?displayProperty=fullName> )

- <xref:System.NotSupportedException?displayProperty=fullName> et tous les dérivés

- <xref:System.ArgumentException> et dérivés

### <a name="equals-methods"></a>Equals (méthodes)
 Les méthodes **Equals** suivantes ne doivent pas lever d’exceptions :

- <xref:System.Object.Equals%2A?displayProperty=fullName>

- [M:IEquatable.Equals](https://msdn2.microsoft.com/library/ms131190(VS.80).aspx)

  Une méthode **Equals** doit retourner `true` ou `false` au lieu de lever une exception. Par exemple, si est passé deux types incompatibles, il doit simplement retourner la valeur `false` au lieu de lever une <xref:System.ArgumentException> .

### <a name="gethashcode-methods"></a>Méthodes GetHashCode
 Les méthodes **GetHashCode** suivantes ne doivent généralement pas lever d’exceptions :

- <xref:System.Object.GetHashCode%2A>

- [M :IEqualityComparer.GetHashCode (T)](https://msdn2.microsoft.com/library/system.collections.iequalitycomparer.gethashcode.aspx)

  **GetHashCode** doit toujours retourner une valeur. Dans le cas contraire, vous pouvez perdre des éléments dans la table de hachage.

  Les versions de **GetHashCode** qui acceptent un argument peuvent lever une exception <xref:System.ArgumentException> . Toutefois, **Object. GetHashCode** ne doit jamais lever d’exception.

### <a name="tostring-methods"></a>Méthodes ToString
 Le débogueur utilise <xref:System.Object.ToString%2A?displayProperty=fullName> pour aider à afficher des informations sur les objets au format de chaîne. Par conséquent, **ToString** ne doit pas modifier l’état d’un objet et ne doit pas lever d’exceptions.

### <a name="static-constructors"></a>Constructeurs statiques
 La levée d’exceptions à partir d’un constructeur statique rend le type inutilisable dans le domaine d’application actuel. Vous devez avoir une bonne raison (un problème de sécurité, par exemple) pour lever une exception à partir d’un constructeur statique.

### <a name="finalizers"></a>Finaliseurs
 Lever une exception à partir d’un finaliseur provoque l’échec rapide du CLR, ce qui a pour effet de détruire le processus. Par conséquent, la levée d’exceptions dans un finaliseur doit toujours être évitée.

### <a name="dispose-methods"></a>Méthodes dispose
 Une <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> méthode ne doit pas lever d’exception. La méthode dispose est souvent appelée dans le cadre de la logique de nettoyage dans une `finally` clause. Par conséquent, lever explicitement une exception à partir de dispose force l’utilisateur à ajouter la gestion des exceptions à l’intérieur de la `finally` clause.

 Le chemin d’accès de code **dispose (false)** ne doit jamais lever d’exceptions, car il est presque toujours appelé à partir d’un finaliseur.

### <a name="equality-operators--"></a>Opérateurs d’égalité (= =, ! =)
 À l’instar des méthodes Equals, les opérateurs d’égalité doivent retourner `true` ou `false` et ne doivent pas lever d’exceptions.

### <a name="implicit-cast-operators"></a>Opérateurs de cast implicite
 Étant donné que l’utilisateur ignore souvent qu’un opérateur de conversion implicite a été appelé, une exception levée par l’opérateur de cast implicite est complètement inattendue. Par conséquent, aucune exception ne doit être levée à partir des opérateurs de conversion implicite.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour les accesseurs get de propriété, modifiez la logique afin qu’il n’ait plus à lever une exception ou remplacez la propriété par une méthode.

 Pour tous les autres types de méthode énumérés précédemment, modifiez la logique pour qu’elle ne doive plus lever d’exception.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer sans risque un avertissement de cette règle si la violation a été provoquée par une déclaration d’exception au lieu d’une exception levée.

## <a name="related-rules"></a>Règles associées
 [CA2219 : Ne pas lever d'exceptions dans les clauses d'exception](../code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses.md)

## <a name="see-also"></a>Voir aussi
 [Avertissements de conception](../code-quality/design-warnings.md)
