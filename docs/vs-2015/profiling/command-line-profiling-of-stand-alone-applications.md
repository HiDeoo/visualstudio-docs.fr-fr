---
title: Profilage d’applications autonomes à partir de la ligne de commande | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- profillng tools,stand-alone applications
- profling stand-alone applications
ms.assetid: a47f2bf2-186d-4120-bb79-34e2f3a1ee42
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3b261ab2da3ee405db46d8c18e3d41771f1ae5e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47500920"
---
# <a name="command-line-profiling-of-stand-alone-applications"></a>Profilage d’applications autonomes à partir de la ligne de commande
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [profilage de ligne de commande de Stand-Alone Applications](https://docs.microsoft.com/visualstudio/profiling/command-line-profiling-of-stand-alone-applications).  
  
Cette section décrit les procédures et les options de collecte des données de performances pour les applications autonomes (clientes) à l’aide des outils de profilage [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], à partir de la ligne de commande.  
  
## <a name="common-tasks"></a>Tâches courantes  
  
|Tâche|Contenu connexe|  
|----------|---------------------|  
|**Collecter des statistiques d’application** : Utilisez la méthode d’échantillonnage pour collecter les statistiques de performance. Les données d’échantillonnage sont utiles pour analyser les problèmes d’utilisation du processeur et pour comprendre les caractéristiques des performances générales d’une application.|-   [Collecte de statistiques d’applications en utilisant l’échantillonnage](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Collecter des données de minutage détaillées** : utilisez la méthode d’instrumentation pour collecter les données de minutage détaillées. Les données d’instrumentation sont utiles pour analyser les problèmes d’E/S et pour analyser de manière plus approfondie les scénarios d’application.|-   [Collecte de données de minutage détaillées à l’aide de l’instrumentation](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**Collecter les données de mémoire .NET** : utilisez la méthode d’échantillonnage ou d’instrumentation pour collecter des données d’allocation de mémoire .NET indiquant le nombre d’objets alloués, ainsi que leur taille. Vous pouvez également collecter des données de durée de vie des objets qui indiquent le nombre et la taille des objets qui sont récupérés dans chaque génération de garbage collection.|-   [Collecte de données de mémoire .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Collecter des données concurrentielles** : utilisez la méthode d’accès concurrentiel pour collecter des données de conflit de ressources et des données d’activité de thread montrant l’utilisation du processeur, les conflits de threads, la migration des threads, les délais de synchronisation, les zones d’E/S avec chevauchement, et autres événements système.|-   [Collecte de données de concurrence](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Ajouter des données d’interaction de couche** : vous pouvez ajouter des données de performances relatives aux appels ADO.NET synchrones émis par l’application vers une base de données Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. L’ajout de données d’interaction de couche à une exécution de profilage nécessite que vous utilisiez des procédures spécifiques pour les outils de profilage en ligne de commande.|-   [Collecte de données d’interaction de couche](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Faites un essai** : utilisez des procédures pas à pas pour profiler un exemple d’application cliente à l’aide de la méthode d’échantillonnage ou d’instrumentation.|-   [Procédure pas à pas : profilage de la ligne de commande à l’aide de l’échantillonnage](../profiling/walkthrough-command-line-profiling-using-sampling.md)<br />-   [Procédure pas à pas : profilage de la ligne de commande à l’aide de l’instrumentation](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)|  
  
## <a name="related-tasks"></a>Tâches connexes  
  
|Tâche|Contenu associé|  
|----------|---------------------|  
|**Profiler des applications ASP.NET**|-   [Profilage d’applications web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)|  
|**Profiler des services**|-   [Profilage des services](../profiling/command-line-profiling-of-services.md)|



