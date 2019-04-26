---
title: Vues des données de la méthode d’échantillonnage du profileur | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,sampling data views
- sampling data views
ms.assetid: 798de693-e43a-4056-aff5-48310c2172c5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 622a088506fe913c834e7de8807dc167f6ab0fc9
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63431988"
---
# <a name="profiler-sampling-method-data-views"></a>Vues des données de la méthode d’échantillonnage du profileur
Cette section contient des informations de référence pour les vues et rapports des fichiers de données de profilage générés avec la méthode d’instrumentation.

> [!NOTE]
> Les fonctionnalités de sécurité renforcée de Windows 8 et Windows Server 2012 ont imposé des changements importants dans la façon dont le profileur Visual Studio collecte les données sur ces plateformes. Les applications UWP nécessitent aussi de nouvelles techniques de collecte. Consultez [Outils d’analyse des performances sur les applications Windows 8 et Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="in-this-section"></a>Dans cette section
- [Vue Résumé](../profiling/summary-view-sampling-data.md)

 Répertorie les fonctions qui ont été exécutées le plus fréquemment lors de la collecte des échantillons, et les fonctions qui ont effectué le plus de travail individuel.

- [Mode Arborescence des appels](../profiling/call-tree-view-sampling-data.md)

 Affiche les chemins d’exécution des fonctions dans une arborescence hiérarchique.

- [Vue Modules](../profiling/modules-view-sampling-data.md)

 Organise les données de profilage par module, et répertorie les fonctions, les lignes de code source et les instructions qui s’exécutaient pendant la collecte des échantillons.

- [Vue Appelant/Appelé - Données d’échantillonnage](../profiling/caller-callee-view-sampling-data.md)

 Affiche les données de profilage pour une fonction sélectionnée, et pour les fonctions qui l’ont appelée et qui ont été appelées par celle-ci.

- [Vue Fonctions](../profiling/functions-view-sampling-data.md)

 Organise le profilage par fonction et répertorie les fonctions qui s’exécutaient pendant la collecte des échantillons.

- [Vue Lignes](../profiling/lines-view-sampling-data.md)

 Répertorie les lignes de code source qui s’exécutaient pendant la collecte des échantillons.

- [Vue Pointeurs d’instruction (IP)](../profiling/instruction-pointers-ips-view-sampling-data.md)

 Répertorie les lignes de code source qui s’exécutaient pendant la collecte des échantillons.

## <a name="reference"></a>Référence
- [Vue Processus](../profiling/process-view.md)

 Répertorie les heures de début et de fin des processus et des threads.

- [Vue Marques](../profiling/marks-view.md)

 Répertorie les événements ETW et les événements d’échantillonnage insérés dans un fichier de données de profilage.

- [Vue Informations relatives à la fonction](../profiling/function-details-view.md)

 Affiche un graphique de la relation qui existe entre une fonction sélectionnée et les fonctions qui l’ont appelée et qui ont été appelées par celle-ci.

## <a name="related-sections"></a>Rubriques connexes
- [Vues de données de la méthode d'instrumentation](../profiling/instrumentation-method-data-views.md)

 Informations de référence sur les vues et les rapports des fichiers de données du profileur générés à l’aide de la méthode d’instrumentation.

- [Vues des données de la mémoire .NET](../profiling/dotnet-memory-data-views.md)

 Informations de référence pour les vues et rapports des fichiers de données du profileur qui incluent les données de mémoire .NET.

## <a name="see-also"></a>Voir aussi
- [Fonctionnement des valeurs de données d’échantillonnage](../profiling/understanding-sampling-data-values.md)