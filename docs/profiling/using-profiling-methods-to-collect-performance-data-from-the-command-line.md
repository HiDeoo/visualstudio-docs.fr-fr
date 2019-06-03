---
title: Utiliser des méthodes de profilage de ligne de commande pour obtenir des données de performances
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 5613fafc-f298-4e7a-9a2d-a853b61cdf9c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3c0472fb572aab8559d8cbb571c044f9ef25f8ed
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "66263822"
---
# <a name="use-profiling-methods-to-collect-performance-data-from-the-command-line"></a>Utiliser des méthodes de profilage pour collecter des données de performances à partir de la ligne de commande
Votre choix d’outils et d’options de ligne de commande des outils de profilage de [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dépend de facteurs comme le type d’application que vous profilez, la méthode de profilage que vous voulez utiliser, et de ce que l’application cible est écrite en code natif ou en code [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].

 Cette rubrique classe les rubriques des procédures pour la ligne de commande en fonction de la méthode de profilage que vous choisissez.

## <a name="use-the-sampling-method-to-collect-performance-statistics"></a>Utiliser la méthode d’échantillonnage pour collecter les statistiques de performances
 La méthode d’échantillonnage des outils de profilage collecte les données de performances à des intervalles spécifiés dans une exécution du profilage. L’échantillonnage des données peut fournir des insights sur les problèmes de performances liées à l’UC, et il peut être un bon moyen de commencer à explorer les performances d’une application.

 Vous pouvez démarrer le profileur et l’application en même temps, ou vous pouvez attacher le profileur à une instance d’une application en cours d’exécution.

|Tâche|Type d’application cible|
|----------|-----------------------------|
|**Lancer une application**|-   [Applications autonomes](../profiling/how-to-launch-a-stand-alone-app-and-collect-application-statistics.md)|
|**Attacher à un processus en cours d’exécution**|-   [Applications autonomes .NET Framework](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-application-statistics.md)<br />-   [Applications autonomes natives](../profiling/how-to-attach-the-profiler-to-a-native-app-and-collect-application-statistics.md)<br />-   [Applications web ASP.NET](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [Services .NET](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [Services natifs](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line.md)|

## <a name="use-the-instrumentation-method-to-collect-detailed-timing-data"></a>Utiliser la méthode d’instrumentation pour collecter les données de minutage détaillées
 La méthode d’instrumentation des outils de profilage collecte des données de performances à partir de copies de fichiers binaires de l’application qui contiennent des sondes logicielles pour enregistrer des informations sur les performances. Les données d’instrumentation sont collectées au début et à la fin de chaque fonction instrumentée et à chaque appel à d’autres fonctions depuis la fonction instrumentée. La méthode d’instrumentation est utile pour détecter les problèmes de performances avec les E/S, comme l’utilisation des disques.

 Vous créez le fichier binaire instrumenté avec l’outil [VInstr.exe](../profiling/vsinstr.md). Une fois le profileur initialisé, les données sont collectées automatiquement à partir des fichiers binaires instrumentés quand vous exécutez l’application cible.

 **Type d’application cible**

- [Composants autonomes .NET Framework](../profiling/how-to-instrument-a-dotnet-framework-component-and-collect-timing-data.md)

- [Composants autonomes natifs](../profiling/how-to-instrument-a-native-component-and-collect-timing-data.md)

- [Applications web ASP.NET compilées statiquement](../profiling/how-to-instrument-statically-compiled-aspnet-and-collect-detailed-timing-data.md)

- [Applications web ASP.NET compilées dynamiquement](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-app-and-collect-timing-data.md)

- [Services .NET](../profiling/how-to-instrument-a-dotnet-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)

- [Services natifs](../profiling/how-to-instrument-a-native-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)

## <a name="use-net-memory-methods-to-collect-memory-allocation-and-object-lifetime-data"></a>Utiliser des méthodes de mémoire .NET pour collecter les données d’allocation de mémoire et de durée de vie des objets
 La méthode de mémoire .NET des outils de profilage vous permet de collecter des données d’allocation de mémoire du [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] et des informations sur la durée de vie des objets dans le [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].

 Vous pouvez démarrer l’application cible à l’aide du profileur, vous pouvez attacher le profileur à une instance en cours d’exécution d’une application ou vous pouvez créer des versions instrumentées de l’application pour collecter des informations de minutage détaillées avec les données de mémoire du [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].

|Tâche|Type d’application cible|
|----------|-----------------------------|
|**Lancer une application**|-   [Applications .NET Framework autonomes](../profiling/how-to-launch-a-stand-alone-dotnet-framework-app-to-collect-memory-data.md)|
|**Attacher à un processus en cours d’exécution**|-   [Applications autonomes .NET Framework](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-app-to-collect-memory-data.md)<br />-   [Applications web ASP.NET](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [Services .NET](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-memory-data-by-using-the-command-line.md)|
|**Instrumenter des modules**|-   [Composants autonomes .NET Framework](../profiling/how-to-instrument-a-dotnet-framework-component-and-collect-memory-data.md)<br />-   [Applications web ASP.NET compilées statiquement](../profiling/how-to-instrument-a-statically-compiled-aspnet-app-and-collect-memory-data.md)<br />-   [Applications web ASP.NET compilées dynamiquement](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)<br />-   [Services .NET](../profiling/how-to-instrument-a-dotnet-framework-service-and-collect-memory-data-by-using-the-profiler-command-line.md)|

## <a name="use-the-concurrency-method-to-collect-resource-contention-and-thread-activity-data"></a>Utiliser la méthode de concurrence pour collecter les données de conflit de ressources et d’activité du thread
 La méthode de concurrence des outils de profilage vous permet de collecter des données sur les conflits de ressources et sur l’activité des threads et des processus à partir d’applications multithreads.

 Vous pouvez démarrer l’application à l’aide du profileur, ou vous pouvez attacher le profileur à une instance d’une application en cours d’exécution.

|Tâche|Type d’application cible|
|----------|-----------------------------|
|**Lancer une application**|-   [Application .NET Framework autonome](../profiling/how-to-launch-a-stand-alone-dotnet-framework-app-to-collect-concurrency-data.md)<br />-   [Application native autonome](../profiling/how-to-launch-a-stand-alone-native-application-to-collect-concurrency-data.md)|
|**Attacher à un processus en cours d’exécution**|-   [Application autonome .NET Framework](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-concurrency-data.md)<br />-   [Application autonome native](../profiling/how-to-attach-the-profiler-to-a-native-app-and-collect-concurrency-data.md)<br />-   [Application web ASP.NET](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [Service .NET](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [Service natif](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|

## <a name="add-tier-interaction-data-to-a-profiling-run"></a>Ajouter des données d’interaction de couche à une exécution du profilage
 Pour ajouter des données d’interaction de couche à une exécution de profilage, vous devez utiliser des procédures spécifiques avec les outils de profilage en ligne de commande. Consulter [Collecter les données d’interaction de couche](../profiling/adding-tier-interaction-data-from-the-command-line.md)

## <a name="see-also"></a>Voir aussi
- [Profiler des applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Profiler des applications web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profiler des services](../profiling/command-line-profiling-of-services.md)