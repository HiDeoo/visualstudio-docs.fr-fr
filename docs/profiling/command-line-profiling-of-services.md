---
title: Profilage de services à partir de la ligne de commande | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling toos,services
- profiling services
ms.assetid: f0d62318-b0e8-49c6-9a30-9f7a6adef2f6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 77d03b933952df7597807460846e504317756055
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56614088"
---
# <a name="command-line-profiling-of-services"></a>Profilage de services à partir de la ligne de commande
Cette section décrit les procédures et les options de collecte des données de performances des services Windows utilisant les outils de profilage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] à partir de la ligne de commande.

> [!NOTE]
>  Les fonctionnalités de sécurité renforcée de Windows 8 et Windows Server 2012 ont imposé des changements importants dans la façon dont le profileur Visual Studio collecte les données sur ces plateformes. Les applications UWP nécessitent aussi de nouvelles techniques de collecte. Consultez [Outils d’analyse des performances sur les applications Windows 8 et Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="common-tasks"></a>Tâches courantes


| Tâche | Contenu associé |
| - | - |
| **Collecter des statistiques d’applications :** utiliser la méthode d’échantillonnage pour collecter les statistiques de performances. Les données d’échantillonnage sont utiles pour analyser les problèmes d’utilisation du processeur et pour comprendre les caractéristiques des performances générales d’une application. | -   [Collecter des statistiques d’applications en utilisant l’échantillonnage](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md) |
| **Collecter des données de temporisation détaillées :** utiliseR la méthode d’instrumentation pour collecter des information de temporisation détaillées. Les données d’instrumentation sont utiles pour analyser les problèmes d’E/S et pour analyser de manière plus approfondie les scénarios d’application. | -   [Collecter les données temporelles détaillées à l’aide de l’instrumentation](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method.md) |
| **Collecter les données de mémoire .NET :** utiliser la méthode d’échantillonnage ou d’instrumentation pour collecter des données d’allocation de mémoire .NET indiquant le nombre d’objets alloués et leur taille. Vous pouvez également collecter des données de durée de vie des objets qui indiquent le nombre et la taille des objets qui sont récupérés dans chaque génération de garbage collection. | -   [Collecter des données de mémoire .NET](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md) |
| **Collecter des données concurrentielles :** utiliser la méthode d’accès concurrentiel pour collecter des données de conflit de ressources et des données d’activité de thread montrant l’utilisation du processeur, les conflits de threads, la migration des threads, les délais de synchronisation, les zones d’E/S avec chevauchement, et autres événements système. | -   [Collecter des données concurrentielles](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md) |
| **Ajouter des données d’interaction de couche** : vous pouvez ajouter des données de performances relatives aux appels ADO.NET synchrones émis par le service vers une base de données Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]. | -   [Collecter les données d’interaction de couche](../profiling/adding-tier-interaction-data-from-the-command-line.md) |

## <a name="related-tasks"></a>Tâches connexes

|Tâche|Contenu associé|
|----------|---------------------|
|**Profiler des applications autonomes (clientes)**|-   [Profiler des applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)|
|**Profiler des applications ASP.NET**|-   [Profiler des applications web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)|