---
title: 'CA1809 : Évitez les variables locales excessives | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1809
- AvoidExcessiveLocals
helpviewer_keywords:
- AvoidExcessiveLocals
- CA1809
ms.assetid: 5c81ea43-cb49-448f-980f-a1dd9764043c
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: d39c8d9d09cf457738df87e3c2e6e109f7bc1696
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85543856"
---
# <a name="ca1809-avoid-excessive-locals"></a>CA1809 : Évitez le surplus de variables locales
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|AvoidExcessiveLocals|
|CheckId|CA1809|
|Category|Microsoft. performance|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause :
 Un membre contient plus de 64 variables locales, dont certaines peuvent être générées par le compilateur.

## <a name="rule-description"></a>Description de la règle
 Une optimisation des performances courante consiste à stocker une valeur dans un registre de processeur au lieu de la mémoire, qui est appelée *inscrire* la valeur. Le common language runtime prend en compte jusqu’à 64 variables locales pour l’inscription. Les variables qui ne sont pas inscrites sont placées dans la pile et doivent être déplacées vers un registre avant la manipulation. Pour autoriser l’inscription de toutes les variables locales, limitez le nombre de variables locales à 64.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, refactorisez l’implémentation de façon à ne pas utiliser plus de 64 variables locales.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer sans risque un avertissement de cette règle, ou de désactiver la règle, si les performances ne sont pas un problème.

## <a name="related-rules"></a>Règles associées
 [CA1804 : Supprimez les variables locales inutilisées](../code-quality/ca1804-remove-unused-locals.md)
