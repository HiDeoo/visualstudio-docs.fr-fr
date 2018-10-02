---
title: Outils d’analyse des performances sur les applications Windows 8 et Windows Server 2012 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a704215d-d252-4087-921b-ac81ebe2a9c9
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8138129c928a02ed5fb6684bc6ee06282435860e
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/05/2018
ms.locfileid: "47590882"
---
# <a name="performance-tools-on-windows-8-and-windows-server-2012-applications"></a>Outils d’analyse des performances sur les applications Windows 8 et Windows Server 2012
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [outils de performances sur les applications Windows 8 et Windows Server 2012](https://docs.microsoft.com/visualstudio/profiling/performance-tools-on-windows-8-and-windows-server-2012-applications).  
  
Les fonctionnalités de sécurité renforcée de Windows 8 et Windows Server 2012 ont imposé des modifications importantes dans la façon dont les outils d’analyse des performances Visual Studio collectent les données sur ces plateformes. Les applications Windows Store demandent aussi de nouvelles techniques de collecte. Cette rubrique décrit les modifications concernant les outils d’analyse des performances sur les plateformes Windows 8 et Windows Server 2012.  
  
> [!NOTE]
>  Les outils d’analyse des performances des autres versions prises en charge de Windows (Windows 7, Windows Server 2008 R2) n’ont pas changé.  
  
##  <a name="BKMK_In_this_topic"></a> Dans cette rubrique  
 [Collecte de données dans des applications du Windows Store à partir de l’IDE de Visual Studio](#BKMK_Profiling_Windows_Store_apps_from_the_Visual_Studio_IDE)  
  
 [Collecte de données dans des applications qui s’exécutent sur les postes de travail Windows 8 ou sur Windows Server 2012 à partir de l’IDE de Visual Studio](#BKMK_Profiling_apps_running_on_the_Windows_8_desktop_or_on_Windows_Server_2012_from_the_Visual_Studio_IDE)  
  
-   [Collecte de données dans des applications qui s’exécutent sur les postes de travail Windows 8 ou sur Windows Server 2012 à l’aide de l’échantillonnage de l’IDE de Visual Studio](#BKMK_Profiling_apps_running_on_the_Windows_8_desktop_or_on_Windows_Server_2012_by_using_sampling_from_the_Visual_Studio_IDE)  
  
 [Profilage à partir de la ligne de commande](#BKMK_Profiling_from_the_command_line)  
  
 [Collecte de données d’interaction de couche (TIP)](#BKMK_Collecting_tier_interaction__TIP__data)  
  
##  <a name="BKMK_Profiling_Windows_Store_apps_from_the_Visual_Studio_IDE"></a> Collecte de données dans des applications du Windows Store à partir de l’IDE de Visual Studio  
 Quand vous profilez une application du Windows Store écrite en JavaScript et HTML 5, vous collectez des données d’instrumentation pour le code JavaScript. Quand vous profilez une application ou un composant du Windows Store écrit en Visual C++, Visual C# ou Visual Basic, vous collectez des données d’échantillonnage pour le code natif et managé. Vous pouvez profiler votre application localement ou sur un ordinateur distant.  
  
 Ces fonctionnalités et options de profilage ne sont pas prises en charge quand il s’agit de profiler des applications du Windows Store :  
  
-   profilage d’applications JavaScript à l’aide de la méthode d’échantillonnage ;  
  
-   profilage de code managé et natif à l’aide de la méthode d’instrumentation ;  
  
-   profilage d’accès concurrentiel ;  
  
-   profilage de mémoire .NET ;  
  
-   profilage d’interaction de couche (TIP) ;  
  
-   options d’échantillonnage, telles que la définition de l’événement d’échantillonnage et l’intervalle de temporisation, ou la collecte de données de compteurs de performances supplémentaires ;  
  
-   options d’instrumentation, telles que la collecte de données de compteurs de performances et Windows, ou définition d’options de ligne de commande supplémentaires.  
  
 Pour plus d’informations sur le profilage d’applications du Windows Store, consultez les rubriques suivantes dans le Centre de développement Windows :  
  
 [Exécuter des applications du Windows Store sur un ordinateur local](../debugger/run-windows-store-apps-on-the-local-machine.md)  
  
 [Exécuter des applications du Windows Store sur un ordinateur distant](../debugger/run-windows-store-apps-on-a-remote-machine.md)  
  
 [Analyser les performances de l’application](http://msdn.microsoft.com/library/58acb30b-8428-41a6-b195-b0fdedb89575)  
  
-   [Minutage de fonction JavaScript](http://msdn.microsoft.com/library/b2bf49fc-aea7-4d9c-8fcf-cff8b8dd0c03)  
  
-   [Minutage de fonction JavaScript sur un périphérique distant](http://msdn.microsoft.com/library/d78812b6-a97e-46dc-8d99-e724d1d725d8)  
  
-   [Analyser les données de minutage de fonction JavaScript](http://msdn.microsoft.com/library/b5aea8d8-36df-47ba-a7ca-95406700ca9b)  
  
-   [Profiler du code Visual C++, Visual C# et Visual Basic dans des applications du Windows Store sur un ordinateur local](http://msdn.microsoft.com/en-us/2d0c939e-0bac-48c5-b727-46f6c6113060)  
  
-   [Profiler le code Visual C++, Visual C# et Visual Basic des applications Windows Store sur un périphérique distant](http://msdn.microsoft.com/en-us/b932a2be-11b0-40fd-b996-75c6b6a79d22)  
  
-   [Analyser les données de performances du code Visual C++, Visual C# et Visual Basic dans des applications Windows Store](http://msdn.microsoft.com/en-us/5de4a413-d924-425f-afc4-e1ecfb0fca18)  
  
 [Dans cette rubrique](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Profiling_apps_running_on_the_Windows_8_desktop_or_on_Windows_Server_2012_from_the_Visual_Studio_IDE"></a>Collecte de données dans des applications qui s’exécutent sur les postes de travail Windows 8 ou sur Windows Server 2012 à partir de l’IDE de Visual Studio  
 Le profilage à l’aide de la méthode d’instrumentation n’a pas évolué pour Windows 8.  
  
 Le profilage d’interaction de couche (TIP) n’est pas pris en charge en utilisant la méthode d’échantillonnage.  
  
###  <a name="BKMK_Profiling_apps_running_on_the_Windows_8_desktop_or_on_Windows_Server_2012_by_using_sampling_from_the_Visual_Studio_IDE"></a>Collecte de données dans des applications qui s’exécutent sur les postes de travail Windows 8 ou sur Windows Server 2012 à l’aide de l’échantillonnage de l’IDE de Visual Studio  
 Ces fonctionnalités et options de profilage ne sont pas prises en charge quand il s’agit de profiler des applications de bureau Windows 8 ou des applications Windows Server 2012 à l’aide de la méthode d’échantillonnage :  
  
-   Profilage d’interaction de couche (TIP). La collecte de données de TIP est prise en charge en utilisant l’instrumentation.  
  
-   Options d’échantillonnage, telles que la définition de l’événement d’échantillonnage et l’intervalle de temporisation, ou la collecte de données de compteurs de performances supplémentaires.  
  
##  <a name="BKMK_Profiling_from_the_command_line"></a> Profilage à partir de la ligne de commande  
 Pour collecter les données de profilage sur les appareils Windows 8 et Windows Server 2012, y compris les appareils qui n’ont pas d’installation de Visual Studio, vous pouvez utiliser deux outils de ligne de commande :  
  
|Nom de l’outil|Description|  
|---------------|-----------------|  
|[VSPerf](../profiling/vsperf.md)|Collecte les données de profilage à partir des applications du Windows Store et collecte les données de profilage d’échantillon à partir des applications de bureau Windows 8 et des applications Windows Server 2012.|  
|[VSPerfCmd](../profiling/vsperfcmd.md)|Collecte les données de profilage d’instrumentation, d’accès concurrentiel et d’interaction de couche à partir d’applications qui s’exécutent sur le bureau Windows 8 ou Windows Server 2012. Collecte tous les types de données de profilage à partir des versions précédentes de Windows.|  
  
 Les deux outils sont installés avec Visual Studio pour être utilisés sur l’ordinateur local.  
  
 Pour profiler des applications sur les appareils dépourvus de Visual Studio, procédez de l’une des façons suivantes :  
  
-   Téléchargez les outils dans le cadre des Outils de contrôle à distance pour Visual Studio à partir du [site web MSDN](http://go.microsoft.com/fwlink/?LinkID=219549).  
  
-   Copiez et exécutez le programme d’installation des outils de profilage autonomes à partir de votre ordinateur Visual Studio. Les programmes d’installation se trouvent dans le dossier *VSInstallDir%* **\Team Tools\Performance Tools\Setups** . Choisissez le programme d’installation correspondant au système d’exploitation (x86/x64) de l’ordinateur distant.  
  
> [!NOTE]
>  Pour collecter les données de profilage TIP, vous devez installer le profileur autonome de votre ordinateur Visual Studio sur l’ordinateur distant.  
  
 Ces fonctionnalités et options de profilage ne sont pas prises en charge quand il s’agit de profiler des applications Windows 8 et Windows Server 2012 à partir de la ligne de commande :  
  
-   Collecte de données à partir d’applications web Windows 8 et Windows Server 2012 en utilisant le mode d’échantillonnage avec [VSPerfASPNetCmd](../profiling/vsperfaspnetcmd.md).  
  
-   Collecte des données d’échantillonnage à l’aide de VsPerfCmd.exe.  
  
-   Options d’échantillonnage, telles que la définition de l’événement d’échantillonnage et l’intervalle de temporisation, ou la collecte de données de compteurs de performances supplémentaires.  
  
##  <a name="BKMK_Collecting_tier_interaction__TIP__data"></a> Collecte des données d'interaction de couche (TIP)  
 Le profilage d’interaction de couche fournit des informations supplémentaires sur les temps d’exécution des fonctions d’applications multicouches qui communiquent avec des bases de données via les services ADO.NET. Les données sont collectées uniquement pour les appels de fonctions synchrones.  
  
 **Éditions Visual Studio**  
  
 Les données de profilage d’interaction de couche peuvent être collectées en utilisant [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)]ou [!INCLUDE[vs_pro_current_short](../includes/vs-pro-current-short-md.md)]. Cependant, les données de profilage d’interaction de couche ne peuvent être affichées que dans [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)] et [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)].  
  
 **Windows 8 et Windows Server 2012**  
  
1.  Pour collecter des données d’interaction de couche à partir d’applications qui s’exécutent sur le bureau Windows 8 ou Windows Server 2012, vous devez utiliser la méthode d’instrumentation.  
  
2.  Vous ne pouvez pas collecter de données d’interaction de couche pour les applications du Windows Store.  
  
3.  Vous pouvez inclure des données d’interaction de couche dans toutes les méthodes de profilage sur les autres versions prises en charge de Windows.  
  
 **Assistant Performance et Explorateur de performances**  
  
 Vous devez ajouter l’option de collecte de données d’interaction de couche à une exécution du profilage à partir de l’Explorateur de performances. Vous devez aussi ajouter le projet, l’exécutable ou le site web au nœud cible de l’Explorateur de performances. Consultez [Collecte de données d’interaction de couche](../profiling/collecting-tier-interaction-data.md).  
  
 **Collecte de données TIP sur un ordinateur distant**  
  
 Pour collecter des données d’interaction de couche sur un ordinateur distant, vous devez copier le **vs\_profileur\_**_\<plateforme >_ **\_**  _\<Langue >_**.exe** de fichiers à partir de la _VSInstallDir%_**\Team Tools\Setups**dossier de Visual Studio de l’ordinateur à l’ordinateur distant et l’installer. Vous ne pouvez pas utiliser les outils de profilage dans le [outils distants Visual Studio](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c) télécharger le package.  
  
 Vous pouvez utiliser [VSPerfCmd](../profiling/vsperfcmd.md) ou [VSPerfASPNetCmd](../profiling/vsperfaspnetcmd.md) pour collecter les données de profilage.  
  
 **Rapports TIP**  
  
 Les données d’interaction de couche ne peuvent être affichées que dans l’IDE [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)] ou [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)] . Les rapports d’interaction de couche basés sur des fichiers générés à l’aide de [VSPerfReport](../profiling/vsperfreport.md) ne sont pas disponibles.  
  
## <a name="see-also"></a>Voir aussi  
 [Explorateur de performances](../profiling/performance-explorer.md)   
 [Configuration de sessions de performance](../profiling/configuring-performance-sessions.md)   
 [Profilage à partir de la ligne de commande](../profiling/using-the-profiling-tools-from-the-command-line.md)



