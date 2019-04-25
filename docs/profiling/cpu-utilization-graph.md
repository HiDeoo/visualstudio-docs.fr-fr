---
title: Graphique d’utilisation du processeur | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.cpu.graph
helpviewer_keywords:
- CPU Utilization GraphConcurrency Visualizer, CPU Utilization Graph
ms.assetid: 5332fd38-622d-47a3-874f-8c2fd7a30f95
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e09526930bf98141ae4f9d4d204b20383763c208
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62552874"
---
# <a name="cpu-utilization-graph"></a>Graphique d’utilisation du processeur
Le graphique d’utilisation du processeur affiche le niveau d’utilisation d’une application dans le temps. L’axe des abscisses représente la durée du suivi et l’axe des ordonnées représente le nombre de cœurs logiques sur le système. Le graphique n’affiche pas les cœurs qui sont actifs à un moment donné. Par exemple, si deux cœurs s’exécutent chacun à 50 % de leur capacité pendant une période donnée, cette vue ne montre qu’un seul cœur logique en cours d’utilisation.

## <a name="cpu-utilization-graph-colors"></a>Couleurs du graphique d’utilisation du processeur

- Le vert indique l’utilisation des cœurs logiques du système par le processus en cours.

- Le gris clair indique l’utilisation des cœurs logiques par d’autres processus sur le système. Un pourcentage élevé de gris clair dans le graphique du processeur indique que le système est très chargé par d’autres processus et que votre processus est susceptible d’être anticipé. Pour réduire la consommation des cœurs logiques par d’autres processus, réduisez le nombre des processus qui s’exécutent sur le système.

- Le gris foncé indique la consommation des cœurs logiques par le processus système. Vous n’avez pas de contrôle direct sur cette consommation, mais il est utile de savoir quand elle se produit, car elle peut affecter la disponibilité des cœurs logiques pour votre processus.

- Le blanc indique la disponibilité des cœurs logiques inutilisés sur le système. Ces cœurs sont disponibles pour votre processus si vous trouvez davantage d’opportunités de parallélisme.

## <a name="see-also"></a>Voir aussi
- [Vue Utilisation](../profiling/utilization-view.md)
- [Utilisation moyenne de l’UC](../profiling/average-cpu-utilization.md)