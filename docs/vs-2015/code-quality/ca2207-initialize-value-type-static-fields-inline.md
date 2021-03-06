---
title: 'CA2207 : initialisez les champs statiques de type valeur Inline | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 792fe18a4f472d0b8a4fd62c652f2ae34fcf6864
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85546300"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207 : Initialisez les champs statiques des types valeur en ligne
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|InitializeValueTypeStaticFieldsInline|
|CheckId|CA2207|
|Category|Microsoft. usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause :
 Un type valeur déclare un constructeur statique explicite.

## <a name="rule-description"></a>Description de la règle
 Lorsqu’un type valeur est déclaré, il subit une initialisation par défaut où tous les champs de type valeur ont la valeur zéro et tous les champs de type référence ont la valeur `null` ( `Nothing` en Visual Basic). L’exécution d’un constructeur statique explicite est garantie uniquement avant l’appel d’un constructeur d’instance ou d’un membre statique du type. Par conséquent, si le type est créé sans appeler un constructeur d’instance, l’exécution du constructeur statique n’est pas garantie.

 Si toutes les données statiques sont initialisées inline et qu’aucun constructeur statique explicite n’est déclaré, les compilateurs C# et Visual Basic ajoutent l' `beforefieldinit` indicateur à la définition de la classe MSIL. Les compilateurs ajoutent également un constructeur statique privé qui contient le code d’initialisation statique. Ce constructeur statique privé est garanti s’exécuter avant l’accès à tous les champs statiques du type.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, initialisez toutes les données statiques lorsqu’elles sont déclarées et supprimez le constructeur statique.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="related-rules"></a>Règles associées
 [CA1810 : Initialisez les champs statiques de type référence en ligne](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)
