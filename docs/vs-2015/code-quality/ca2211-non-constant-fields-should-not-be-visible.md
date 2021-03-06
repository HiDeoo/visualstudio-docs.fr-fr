---
title: 'CA2211 : les champs non constants ne doivent pas être visibles | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2211
- NonConstantFieldsShouldNotBeVisible
helpviewer_keywords:
- NonConstantFieldsShouldNotBeVisible
- CA2211
ms.assetid: e1e42c40-0acd-4312-af29-70133739a304
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: aa67c33eac5d618c0a080323720775beea7b68c3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85548211"
---
# <a name="ca2211-non-constant-fields-should-not-be-visible"></a>CA2211 : Les champs non constants ne doivent pas être visibles
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|NonConstantFieldsShouldNotBeVisible|
|CheckId|CA2211|
|Category|Microsoft. usage|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause :
 Un champ statique public ou protégé n’est pas constant et est en lecture seule.

## <a name="rule-description"></a>Description de la règle
 Les champs statiques qui ne sont ni constants ni en lecture seule ne sont pas thread-safe. L’accès à ce champ doit être contrôlé avec soin et nécessite des techniques de programmation avancées pour la synchronisation de l’accès à l’objet de classe. Étant donné que ces compétences sont difficiles à apprendre et à maîtriser, et que le test d’un tel objet pose ses propres défis, les champs statiques sont mieux utilisés pour stocker des données qui ne changent pas. Cette règle s’applique aux bibliothèques ; les applications ne doivent pas exposer de champs.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, définissez la constante de champ statique ou en lecture seule. Si ce n’est pas possible, reconcevez le type pour utiliser un autre mécanisme comme une propriété thread-safe qui gère l’accès thread-safe au champ sous-jacent. Sachez que des problèmes tels que la contention de verrou et les blocages peuvent affecter les performances et le comportement de la bibliothèque.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer sans risque un avertissement de cette règle si vous développez une application et que vous disposez par conséquent d’un contrôle total sur l’accès au type qui contient le champ statique. Les concepteurs de bibliothèques ne doivent pas supprimer un avertissement de cette règle ; l’utilisation de champs statiques non constants peut compliquer l’utilisation de la bibliothèque pour les développeurs.

## <a name="example"></a>Exemple
 L’exemple suivant montre un type qui viole cette règle.

 [!code-csharp[FxCop.Usage.AvoidStaticNonConstants#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.AvoidStaticNonConstants/cs/FxCop.Usage.AvoidStaticNonConstants.cs#1)]
 [!code-vb[FxCop.Usage.AvoidStaticNonConstants#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.AvoidStaticNonConstants/vb/FxCop.Usage.AvoidStaticNonConstants.vb#1)]
