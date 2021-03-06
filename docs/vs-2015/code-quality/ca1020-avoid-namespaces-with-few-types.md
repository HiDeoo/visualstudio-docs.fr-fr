---
title: 'Ca1020 : éviter les espaces de noms avec peu de types | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
helpviewer_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
ms.assetid: 9cb272f6-a3ff-45af-b35d-70dea620b074
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 0ddd69c62eb4d6b818410a588967c1e23f164f9a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85546729"
---
# <a name="ca1020-avoid-namespaces-with-few-types"></a>CA1020 : Éviter les espaces de noms comportant peu de types
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|AvoidNamespacesWithFewTypes|
|CheckId|CA1020|
|Category|Microsoft. Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause :
 Un espace de noms autre que l’espace de noms global contient moins de cinq types.

## <a name="rule-description"></a>Description de la règle
 Assurez-vous que chacun de vos espaces de noms a une organisation logique, et qu’il existe une raison valable pour placer les types dans un espace de noms peu rempli. Les espaces de noms doivent contenir des types qui sont utilisés ensemble dans la plupart des scénarios. Lorsque leurs applications sont mutuellement exclusives, les types doivent se trouver dans des espaces de noms distincts. Par exemple, l' <xref:System.Web.UI> espace de noms contient des types utilisés dans les applications Web, et l' <xref:System.Windows.Forms> espace de noms contient des types utilisés dans des [!INCLUDE[TLA#tla_mswin](../includes/tlasharptla-mswin-md.md)] applications basées sur. Même si les deux espaces de noms ont des types qui contrôlent les aspects de l’interface utilisateur, ces types ne sont pas conçus pour être utilisés dans la même application. Par conséquent, ils se trouvent dans des espaces de noms distincts. L’organisation de l’espace de noms avec prudence peut également être utile, car elle augmente la détectabilité d’une fonctionnalité. En examinant la hiérarchie des espaces de noms, les consommateurs de bibliothèques doivent être en mesure de localiser les types qui implémentent une fonctionnalité.

> [!NOTE]
> Les types et autorisations au moment du design ne doivent pas être fusionnés dans d’autres espaces de noms pour se conformer à cette instruction. Ces types appartiennent à leurs propres espaces de noms sous votre espace de noms principal, et les espaces de noms doivent se terminer par `.Design` et `.Permissions` , respectivement.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, essayez de combiner des espaces de noms qui contiennent seulement quelques types dans un espace de noms unique.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer sans risque un avertissement de cette règle lorsque l’espace de noms ne contient pas les types utilisés avec les types dans vos autres espaces de noms.
