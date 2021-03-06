---
title: Conseils sur les performances | Microsoft Docs
ms.date: 9/11/2020
ms.topic: how-to
ms.assetid: 509d2d4f-48a5-4cdf-acad-6f7b75421303
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f260307b677046be54e6d80b0d8fe122b13292e4
ms.sourcegitcommit: 14637be49401f56341c93043eab560a4ff6b57f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90075468"
---
# <a name="perftips"></a>Conseils sur les performances

Les *conseils sur les performances* du débogueur et les **outils de diagnostic** intégrés au débogueur de Visual Studio vous aident à surveiller et à analyser les performances de votre application pendant le débogage.

Bien que les outils de diagnostic intégrés au débogueur constituent un excellent moyen de détecter les problèmes de performances pendant le développement, le débogueur lui-même peut avoir un impact significatif sur les performances de votre application. Pour collecter des données de performances plus précises, envisagez d’utiliser les outils du profileur de performances en tant que partie supplémentaire de vos investigations de performances. Consultez [exécuter les outils de profilage avec ou sans le débogueur](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="perftips"></a>Conseils sur les performances

Quand le débogueur arrête l'exécution à un point d'arrêt ou lors de l'exécution pas à pas, le temps qui s'écoule entre l'arrêt et le point d'arrêt précédent apparaît sous la forme d'un conseil dans la fenêtre de l'éditeur. Pour plus d’informations, consultez [PerfTips: Performance Information at-a-glance while Debugging with Visual Studio](https://devblogs.microsoft.com/devops/perftips-performance-information-at-a-glance-while-debugging-with-visual-studio/).

![PerfTip](../profiling/media/dbgdiag_perf_perftip.png "DBGDIAG_PERF_PerfTip")

## <a name="diagnostics-tools-window"></a>Fenêtre Outils de diagnostic

Les points d’arrêt et les données de minutage associées sont enregistrés dans la fenêtre de **outils de diagnostic** .

L’illustration suivante montre la fenêtre de **outils de diagnostic** .

![Outils&#45;Update 1](../profiling/media/diagnostictools-update1.png "DiagnosticTools-Update1")

- La chronologie **Événements d'arrêt** marque les points d'arrêt qui ont été atteints dans la session de débogage. Cliquez sur un événement pour le sélectionner dans la liste des détails **Débogueur** .

- Le graphique **Utilisation du processeur** montre les changements dans l'utilisation du processeur pour tous ses cœurs dans la session de débogage.

- La liste **Événements** du volet des détails **Débogueur** comprend des éléments pour chaque événement d'arrêt.

- La colonne **Durée** d'un événement d'arrêt affiche le temps écoulé entre l'événement et le point d'arrêt précédent.

## <a name="turn-perftips-on-or-off"></a>Activer ou désactiver les conseils sur les performances

Pour activer ou désactiver les conseils sur les performances :

1. Dans le menu **Déboguer** , choisissez **Options**.

2. Cochez ou décochez **Afficher les conseils sur les performances pendant le débogage**.

## <a name="turn-the-diagnostic-tools-window-on-or-off"></a>Activer ou désactiver la fenêtre Outils de diagnostic

Pour activer ou désactiver la fenêtre Outils de diagnostic :

1. Dans le menu **Déboguer** , choisissez **Options**.

2. Cochez ou décochez **Activer les outils de diagnostic pendant le débogage**.

## <a name="see-also"></a>Voir aussi

- [Profilage dans Visual Studio](../profiling/index.yml)
- [Découvrir les outils de profilage](../profiling/profiling-feature-tour.md)
