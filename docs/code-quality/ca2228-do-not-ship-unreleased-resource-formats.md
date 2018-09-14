---
title: 'CA2228 : Ne distribuez pas des formats de ressources non commercialisés'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e2823933e4792dd6127ffbd4b1bfe5dfe1b71a0c
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45547546"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228 : Ne distribuez pas des formats de ressources non commercialisés
|||
|-|-|
|TypeName|DoNotShipUnreleasedResourceFormats|
|CheckId|CA2228|
|Category|Microsoft.Usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Un fichier de ressources a été créé à l’aide d’une version de la [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] qui est actuellement pas en charge.

## <a name="rule-description"></a>Description de la règle
 Les fichiers de ressources qui ont été créés à l’aide de versions préliminaires de la [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] peut ne pas être utilisables par les versions prises en charge du .NET Framework.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, générez la ressource à l’aide d’une version prise en charge de la [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]k.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.