---
title: 'CA2004 : supprimez les appels à GC. KeepAlive | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 53fa5f61cb7c503502956831452bc3eca1a9fece
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85521197"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004 : Supprimez les appels à GC.KeepAlive
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|Category|Microsoft. fiabilité|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Les classes utilisent `SafeHandle` mais contiennent toujours des appels à `GC.KeepAlive` .

## <a name="rule-description"></a>Description de la règle
 Si vous effectuez une conversion vers `SafeHandle` l’utilisation, supprimez tous les appels à `GC.KeepAlive` (Object). Dans ce cas, les classes n’ont pas besoin d’appeler `GC.KeepAlive` , en supposant qu’elles n’ont pas de finaliseur, mais qu’elles s’appuient sur `SafeHandle` pour terminer le handle du système d’exploitation.  Bien que le coût de la sortie d’un appel à puisse `GC.KeepAlive` être négligeable en termes de performances, la perception qu’un appel à soit `GC.KeepAlive` nécessaire ou suffisant pour résoudre un problème de durée de vie qui n’existe peut-être plus rend le code plus difficile à gérer.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Supprimez les appels à `GC.KeepAlive` .

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Vous pouvez supprimer cet avertissement uniquement s’il n’est pas techniquement correct de le convertir en `SafeHandle` utilisation dans votre classe.
