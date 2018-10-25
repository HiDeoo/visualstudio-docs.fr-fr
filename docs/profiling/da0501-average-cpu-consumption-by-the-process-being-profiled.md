---
title: 'DA0501 : consommation processeur moyenne par le processus en cours de profilage. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DA0501
- vs.performance.DA0501
- vs.performance.501
ms.assetid: b01946b4-75e3-47d5-a1a1-cebfae66a3af
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f9612c895f7453d250b4f37c06e3630901602685
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49847109"
---
# <a name="da0501-average-cpu-consumption-by-the-process-being-profiled"></a>DA0501 : consommation UC moyenne par le processus en cours de profilage.

|||  
|-|-|  
|ID de règle|DA501|  
|Category|Analyse des ressources|  
|Méthode de profilage|Tous|  
|Message|Consommation UC moyenne par le processus en cours de profilage.|  
|Type de règle|Information|  

 Lorsque vous effectuez un profilage à l’aide de la méthode d’échantillonnage, de mémoire .NET ou de conflit des ressources, vous devez collecter au moins 10 échantillons pour déclencher cette règle.  

## <a name="rule-description"></a>Description de la règle  
 Ce message indique le temps, en pourcentage, pendant lequel un processeur a exécuté des instructions à partir de l’application. La valeur signalée correspond à la moyenne de tous les intervalles de mesure pendant lesquels le processus profilé était actif. Cette valeur peut être supérieure à 100 % sur les ordinateurs qui comprennent plusieurs processeurs.  

## <a name="how-to-use-rule-data"></a>Comment utiliser les données de règle  
 Utilisez la valeur de la règle pour comparer les performances des différentes versions du programme ou pour comprendre les performances de l’application dans différents scénarios de test.