---
title: Guide pratique pour attacher le profileur à une application .NET Framework autonome pour collecter des données concurrentielles en utilisant la ligne de commande │ Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdd41576-797e-4312-8520-fee7bb767e4a
caps.latest.revision: 34
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0523b367ec00dd7551dcf30f5002d855a99bf79
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51790407"
---
# <a name="how-to-attach-the-profiler-to-a-net-framework-stand-alone-application-to-collect-concurrency-data-by-using-the-command-line"></a>Guide pratique pour attacher le profileur à une application .NET Framework autonome pour collecter des données concurrentielles en utilisant la ligne de commande
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette rubrique explique comment utiliser les outils de profilage en ligne de commande [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pour attacher le profileur à une application .NET Framework autonome (cliente), et collecter et traiter des données concurrentielles de thread.  
  
> [!NOTE]
>  Les outils en ligne de commande des outils de profilage se trouvent dans le sous-répertoire \Team Tools\Performance Tools du répertoire d’installation de [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)]. Les versions 64 bits et 32 bits des outils sont disponibles sur les ordinateurs 64 bits. Pour utiliser les outils en ligne de commande du profileur, vous devez ajouter le chemin des outils à la variable d’environnement PATH dans la fenêtre d’invite de commandes, ou l’ajouter à la commande. Pour plus d’informations, consultez [Spécification du chemin d’accès aux outils en ligne de commande](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Lorsque le profileur est attaché à l’application, vous pouvez suspendre et reprendre la collecte de données. Pour terminer une session de profilage, le profileur ne doit plus être attaché à l’application et doit être arrêté explicitement.  
  
## <a name="attaching-the-profiler"></a>Attachement du profileur  
  
#### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>Pour attacher le profileur à une application .NET Framework en cours d’exécution  
  
1.  Ouvrez une fenêtre d’invite de commandes.  
  
2.  Démarrez le profileur. Type :  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency  /output:** `OutputFile` [`Options`]  
  
     L’option [/output](../profiling/output.md)**:**`OutputFile` est nécessaire avec **/start**. `OutputFile` spécifie le nom et l’emplacement du fichier de données profilage (.vsp).  
  
     Vous pouvez utiliser l’une des options suivantes avec l’option **/start:concurrency**.  
  
    |Option|Description|  
    |------------|-----------------|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Spécifie le compteur de performances Windows dont les données doivent être collectées au cours du profilage.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|À utiliser avec **/wincounter** uniquement. Spécifie le nombre de millisecondes écoulées entre les événements de collecte du compteur de performances Windows. La valeur par défaut est de 500 ms.|  
    |[/events](../profiling/events-vsperfcmd.md) **:** `Config`|Spécifie l’événement du Suivi d’événements pour Windows (ETW) qui doit être collecté au cours du profilage. Les événements ETW sont collectés dans un fichier séparé (.etl).|  
  
3.  Démarrez l’application cible de manière habituelle.  
  
4.  Attachez le profileur à l’application cible. Type :  
  
     **VSPerfCmd /attach:** `PID` [**/lineoff**] [**/targetclr:**`Version`]  
  
    -   `PID` spécifie l’ID de processus de l’application cible. Vous pouvez afficher les ID de processus de tous les processus en cours d’exécution dans le gestionnaire des tâches de Windows.  
  
    -   [/lineoff](../profiling/lineoff.md) désactive la collecte des données de numéro de ligne.  
  
    -   [/targetclr](../profiling/targetclr.md) **:** `Version` spécifie la version du common language runtime (CLR) à profiler lorsque plusieurs versions du runtime sont chargées dans une application. Facultatif.  
  
## <a name="controlling-data-collection"></a>Contrôle de la collection de données  
 Pendant l’exécution de l’application cible, vous pouvez contrôler la collecte des données en démarrant et en arrêtant l’écriture des données dans le fichier à l’aide des options de VSPerfCmd.exe. En contrôlant la collecte des données, vous pouvez collecter des données pour une phase spécifique de l’exécution du programme, comme le démarrage ou l’arrêt de l’application.  
  
#### <a name="to-start-and-stop-data-collection"></a>Pour démarrer et arrêter la collecte de données  
  
-   Les paires d’options de VSPerfCmd.exe suivantes démarrent et arrêtent la collecte des données. Spécifiez chaque option sur une ligne de commande distincte. Vous pouvez activer et désactiver la collecte de données à plusieurs reprises.  
  
    |Option|Description|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Démarre (**/globalon**) ou arrête (**/globaloff**) la collecte des données pour tous les processus.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Démarre (**/processon**) ou arrête (**/processoff**) la collecte des données pour le processus spécifié par l’ID de processus (`PID`).|  
    |[/attach](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/attach** commence à collecter des données pour le processus spécifié par l’ID de processus (`PID`) ou le nom de processus (ProcName). **/detach** arrête la collecte des données pour le processus spécifié ou pour tous les processus, si aucun processus n’est spécifié.|  
  
## <a name="ending-the-profiling-session"></a>La fin de la session de profilage  
 Pour mettre fin à une session de profilage, le profileur ne doit pas être en train de collecter des données. Vous pouvez arrêter la collecte des données d’une application profilée avec la méthode de concurrence en fermant l’application ou en appelant l’option **VSPerfCmd /detach**. Vous devez alors appeler l’option **VSPerfCmd /shutdown** pour désactiver le profileur et fermer le fichier de données de profilage. La commande **VSPerfClrEnv /off** efface les variables d’environnement de profilage.  
  
#### <a name="to-end-a-profiling-session"></a>Pour terminer une session de profilage  
  
1.  Effectuez l’une des opérations suivantes pour détacher le profileur de l’application cible.  
  
    -   Tapez **VSPerfCmd /detach**  
  
         - ou -  
  
    -   Fermez l’application cible.  
  
2.  Fermez le profileur. Type :  
  
     VSPerfCmd[/shutdown](../profiling/shutdown.md)



