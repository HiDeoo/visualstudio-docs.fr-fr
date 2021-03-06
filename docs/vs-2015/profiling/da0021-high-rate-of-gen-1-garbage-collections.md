---
title: 'DA0021 : Taux élevé de garbage collection Gen 1 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.21
- vs.performance.DA0021
- vs.performance.rules.DA0021
ms.assetid: ebf5d9b3-a1ac-4688-8f0f-39a85f4dd15f
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d901d09350af063a11e3d156f36a100df85e7718
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "82586919"
---
# <a name="da0021-high-rate-of-gen-1-garbage-collections"></a>DA0021 : Taux élevé de garbage collection Gen 1
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ID de règle | DA0021 |  
| Catégorie |. Utilisation de .NET Framework |  
| Méthodes de profilage | Tout |  
| Message | Un taux relativement élevé de garbage collection de la génération 1 se produit. Si, par conception, la plupart des structures de données de votre programme sont allouées et persistent pour longtemps, cela ne pose pas de problème. Cependant, si ce comportement est involontaire, votre application peut épingler des objets. Si vous n’êtes pas sûr, vous pouvez regrouper les données d’allocation de mémoire .NET et les informations de durée de vie des objets afin de comprendre le modèle d’allocation de mémoire utilisé par votre application.|  
| Type de règle | Informations |  
  
 Lorsque vous effectuez un profilage à l’aide de la méthode d’échantillonnage, de mémoire .NET ou de conflit des ressources, vous devez collecter au moins 10 échantillons pour déclencher cette règle.  
  
## <a name="cause"></a>Cause :  
 Les données relatives aux performances système qui ont été collectées pendant le profilage indiquent qu’une importante quantité de mémoire allouée aux objets .NET Framework a été récupérée dans la génération 1 du garbage collection, par rapport à la collecte de données de la génération 0.  
  
## <a name="rule-description"></a>Description de la règle  
 Le common language runtime (CLR) Microsoft .NET fournit un mécanisme de gestion automatique de la mémoire qui utilise un récupérateur de mémoire pour récupérer la mémoire des objets que l’application n’utilise plus. Le récupérateur de mémoire est orienté génération et repose sur l’hypothèse que de nombreuses allocations sont de courte durée. Les variables locales, par exemple, doivent avoir une durée de vie courte. Les objets récemment créés commencent à la génération 0 (gen 0), puis progressent jusqu’à la génération 1 lorsqu’ils survivent à l’exécution d’un garbage collection. Enfin, ils passent à la génération 2 si l’application les utilise toujours.  
  
 Les objets de la génération 0 sont collectés fréquemment et généralement de manière très efficace. Les objets de la génération 1 sont collectés moins fréquemment et moins efficacement. Enfin, les objets à longue durée de vie de la génération 2 doivent être collectés encore moins fréquemment. Le garbage collection de génération 2, qui correspond à un garbage collection complet, constitue l’option la plus coûteuse.  
  
 Cette règle est déclenchée lorsque, proportionnellement, un trop grand nombre de garbage collections de génération 1 se sont produits. Si trop d’objets à courte durée de vie survivent au garbage collection de génération 0, mais qu’ils peuvent ensuite être collectés lors d’un garbage collection de génération 1, le coût de la gestion de la mémoire peut devenir excessif. Pour plus d’informations, consultez [Mid-life crisis](https://docs.microsoft.com/archive/blogs/ricom/mid-life-crisis) sur le blog Performance Tidbits de Rico Mariani sur le site MSDN.  
  
## <a name="how-to-investigate-a-warning"></a>Comment rechercher la cause d’un avertissement  
 Double-cliquez sur le message dans la fenêtre Liste d’erreurs pour accéder à la [vue Marques](../profiling/marks-view.md) des données de profilage. Accédez aux colonnes **Mémoire CLR .NET\\Nombre de collections de la génération 0** et **Mémoire CLR .NET\\Nombre de collections de la génération 1**. Déterminez s’il existe des phases spécifiques de l’exécution du programme durant lesquelles les garbage collections sont plus fréquents. Comparez ces valeurs à celles de la colonne **% temps dans le GC** pour voir si le modèle des allocations de mémoire managée provoque une charge excessive de gestion de la mémoire.  
  
 Pour comprendre la façon dont l’application utilise la mémoire managée, profilez-la de nouveau en exécutant un profil d’allocation de mémoire .NET et demandez des mesures de durée de vie.  
  
 Pour plus d’informations sur l’amélioration des performances du garbage collection, consultez [Garbage Collector Basics and Performance Hints](https://msdn2.microsoft.com/library/ms973837.aspx) sur le site de Microsoft. Pour plus d’informations sur la surcharge du garbage collection automatique, consultez [Le tas des objets volumineux dévoilé](https://msdn.microsoft.com/magazine/cc534993.aspx).
