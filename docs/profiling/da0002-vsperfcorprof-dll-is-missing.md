---
title: 'DA0002 : VSPerfCorProf.dll est manquant | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.DA0002
- vs.performance.2
- vs.performance.rules.DAVsPerfCorProfMissing
- vs.performance.rules.DA0002
ms.assetid: 76e614b3-ad7e-4b92-b7be-88dc1329be1d
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: f768a35e7c50ec55867ae49901718063ca39bd0b
ms.sourcegitcommit: 00b71889bd72b6a566586885bdb982cfe807cf54
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74777749"
---
# <a name="da0002-vsperfcorprofdll-is-missing"></a>DA0002 : VSPerfCorProf.dll manquant

|||
|-|-|
|ID de la règle|DA0002|
|Category|Utilisation des outils de profilage|
|Méthodes de profilage|Profilage avec les outils en ligne de commande VSPerfCmd et VSPerfASPNETCmd|
|Message|Le fichier semble avoir été collecté sans que les variables d’environnement n’aient été définies correctement avec *VSPerfCLREnv.cmd*. Les symboles pour des fichiers binaires managés peuvent ne pas être résolus.|
|Type de règle|Informations|

## <a name="cause"></a>Cause
 Le profileur n’a pas trouvé *VSPerfCorProf.dll* lors de l’exécution du profilage. Cet avertissement se produit quand les outils en ligne de commande pour la collecte de données du profileur sont utilisés sans l’outil *VSPerfCLREnv.cmd* pour initialiser les variables d’environnement nécessaires. L’avertissement peut également se déclencher si un autre profileur est en cours d’exécution quand les outils de profilage démarrent.

## <a name="rule-description"></a>Description de la règle
 Des variables d’environnement spécifiques doivent être définies avant l’exécution d’un profilage pour que le profileur résolve les symboles dans les fichiers binaires .NET Framework. Cet avertissement suggère que l’outil *VSPerfCLREnv.cmd* n’a pas été exécuté avant la collecte des données de profilage. Les symboles pour des fichiers binaires managés peuvent ne pas être résolus. Pour plus d’informations sur l’utilisation des outils de profilage à partir de la ligne de commande, consultez [Profilage à partir de la ligne de commande](../profiling/using-the-profiling-tools-from-the-command-line.md)

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Quand vous profilez des applications managées en utilisant les outils en ligne de commande des Outils de profilage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], exécutez l’outil en ligne de commande [VSPerfCLREnv](../profiling/vsperfclrenv.md) avant de commencer la collecte de données.
