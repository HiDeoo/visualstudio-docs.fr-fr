---
title: 'CA1059 : les membres ne doivent pas exposer certains types concrets | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1059
- MembersShouldNotExposeCertainConcreteTypes
helpviewer_keywords:
- MembersShouldNotExposeCertainConcreteTypes
- CA1059
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 792426615dd78241ade1d38a24ec1f4d5702cede
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85545377"
---
# <a name="ca1059-members-should-not-expose-certain-concrete-types"></a>CA1059 : Les membres ne doivent pas exposer certains types concrets
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|MembersShouldNotExposeCertainConcreteTypes|
|CheckId|CA1059|
|Category|Microsoft. Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause :
 Un membre visible de l’extérieur est un certain type concret ou expose certains types concrets via l’un de ses paramètres ou sa valeur de retour. Actuellement, cette règle signale l’exposition des types concrets suivants :

- Type dérivé de <xref:System.Xml.XmlNode?displayProperty=fullName>.

## <a name="rule-description"></a>Description de la règle
 Un type concret est un type qui présente une implémentation complète et, par conséquent, peut être instancié. Pour permettre une utilisation généralisée du membre, remplacez le type concret par l’interface suggérée. Cela permet au membre d’accepter tout type qui implémente l’interface ou d’être utilisé lorsqu’un type qui implémente l’interface est attendu.

 Le tableau suivant répertorie les types concrets ciblés et leurs remplacements suggérés.

|Type concret|Remplacement|
|-------------------|-----------------|
|<xref:System.Xml.XPath.XPathDocument>|<xref:System.Xml.XPath.IXPathNavigable?displayProperty=fullName>.<br /><br /> L’utilisation de l’interface dissocie le membre d’une implémentation spécifique d’une source de données XML.|

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, remplacez le type concret par l’interface suggérée.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer sans risque un message de cette règle si les fonctionnalités spécifiques fournies par le type concret sont requises.

## <a name="related-rules"></a>Règles associées
 [CA1011 : Si possible, transmettez les types de base en tant que paramètres](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)
