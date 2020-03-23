---
title: 'Ligne de commande Profiler : Lancez une application autonome, obtenez les statistiques de l’application'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 52dcee2b-f178-4a76-bddc-e36c50bfcb78
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: fb6228592115091dc538dbe59c227a180e75aa10
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "74775413"
---
# <a name="how-to-launch-a-stand-alone-application-with-the-profiler-and-collect-application-statistics-by-using-the-command-line"></a>Guide pratique pour lancer une application autonome avec le profileur et collecter des statistiques d’application en utilisant la ligne de commande
Cette rubrique explique comment utiliser les outils en ligne de commande des outils de profilage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pour démarrer une application autonome (cliente) et collecter des statistiques de performances à l’aide de la méthode d’échantillonnage.

> [!NOTE]
> Les fonctionnalités de sécurité renforcée de Windows 8 et Windows Server 2012 ont imposé des changements importants dans la façon dont le profileur Visual Studio collecte les données sur ces plateformes. Les applications UWP nécessitent aussi de nouvelles techniques de collecte. Consultez [Outils d’analyse des performances sur les applications Windows 8 et Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).
>
> Pour ajouter des données d’interaction de couche à une exécution de profilage, vous devez utiliser des procédures spécifiques avec les outils de profilage en ligne de commande. Voir [Collecter les données d’interaction de niveau](../profiling/adding-tier-interaction-data-from-the-command-line.md)

 Pour utiliser les outils en ligne de commande du profileur, vous devez ajouter le chemin à la variable d’environnement PATH dans la fenêtre d’invite de commandes, ou l’ajouter à la commande. Vous pouvez exécuter les outils de profilage sur un ordinateur où est installé Visual Studio, à partir d’une fenêtre Commande Visual Studio.

1. Si vous exécutez les outils de profilage sur un ordinateur où est installé Visual Studio, la fenêtre Commande Visual Studio vous permet de définir les bons chemins. Dans le menu **Outils**, choisissez **Invite de commandes de Visual Studio**

> [!NOTE]
> Pour obtenir le chemin des outils de profilage, consultez [Spécifier le chemin des outils en ligne de commande](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). Les versions 64 bits et 32 bits des outils sont disponibles sur les ordinateurs 64 bits. Pour utiliser les outils en ligne de commande du profileur, vous devez ajouter le chemin des outils à la variable d’environnement PATH dans la fenêtre d’invite de commandes, ou l’ajouter à la commande.

## <a name="start-the-application-with-the-profiler"></a>Démarrer l’application avec le profileur
 Pour démarrer une application cible à l’aide du profileur, utilisez les options **/start** et **/launch** de VSPerfCmd pour initialiser le profileur et démarrer l’application. Vous pouvez spécifier **/start** et **/launch** et leurs options respectives sur une même ligne de commande.

 Vous pouvez également ajouter l’option **/globaloff** pour suspendre la collecte des données au démarrage de l’application cible. Ensuite, utilisez **/globalon** pour commencer à collecter les données.

#### <a name="to-start-an-application-by-using-the-profiler"></a>Pour démarrer une application à l’aide du profileur

1. Ouvrez une fenêtre d’invite de commandes.

2. Démarrez le profileur. Tapez :

    **VSPerfCmd /start:sample /output:** `OutputFile` [ ]`Options`

   - L’option [/start](../profiling/start.md)**:sample** initialise le profileur.

   - La [/sortie](../profiling/output.md)**:** `OutputFile` option est requise avec **/démarrer**. `OutputFile` spécifie le nom et l’emplacement du fichier de données profilage (.vsp).

     Vous pouvez utiliser l’une des options suivantes avec l’option **/start:sample**.

   | Option | Description |
   | - | - |
   | [/wincounter](../profiling/wincounter.md) **:**`WinCounterPath` | Spécifie le compteur de performances Windows dont les données doivent être collectées au cours du profilage. |
   | [/automark](../profiling/automark.md) **:**`Interval` | À utiliser avec **/wincounter** uniquement. Spécifie le nombre de millisecondes écoulées entre les événements de collecte du compteur de performances Windows. La valeur par défaut est de 500 ms. |
   | [/événements](../profiling/events-vsperfcmd.md) **:**`Config` | Spécifie l’événement du Suivi d’événements pour Windows (ETW) qui doit être collecté au cours du profilage. Les événements ETW sont collectés dans un autre (.* etl*) fichier. |

3. Démarrez l’application cible. Type:**VSPerfCmd /lancement:** `appName` [`Options`] ]`Sample Event`

    Vous pouvez utiliser une ou plusieurs des options suivantes avec l’option **/launch**.

   |Option|Description|
   |------------|-----------------|
   |[/args](../profiling/args.md) **:**`Arguments`|Spécifie une chaîne qui contient les arguments de ligne de commande à passer à l’application cible.|
   |[/console](../profiling/console.md)|Démarre l’application en ligne de commande cible dans une fenêtre distincte.|

    Par défaut, les données de performances sont échantillonnées tous les 10 000 000 cycles d’horloge ininterrompus du processeur. Cela correspond environ à une fois toutes les 10 secondes sur un processeur de 1 GHz. Vous pouvez spécifier l’une des options suivantes pour modifier l’intervalle de cycle d’horloge ou pour spécifier un autre événement d’échantillonnage.

   |Exemple d’événement|Description|
   |------------------|-----------------|
   |[/timer](../profiling/timer.md) **:**`Interval`|Remplace l’intervalle d’échantillonnage par le nombre de cycles d’horloge ininterrompus spécifiés par `Interval`.|
   |[/pf](../profiling/pf.md)[**:**`Interval`]|Remplace l’événement d’échantillonnage par les erreurs de page. Si `Interval` est spécifié, définit le nombre d’erreurs de page entre chaque échantillon. La valeur par défaut est 10.|
   |[/sys](../profiling/sys-vsperfcmd.md)[**:**`Interval`]|Remplace l’événement d’échantillonnage par des appels système du processus vers le noyau du système d’exploitation (syscalls). Si `Interval` est spécifié, définit le nombre d’appels entre chaque échantillon. La valeur par défaut est 10.|
   |[/contre](../profiling/counter.md) **:**`Config`|Remplace l’événement et l’intervalle d’échantillonnage par le compteur de performances du processeur et l’intervalle spécifié dans `Config`.|

## <a name="control-data-collection"></a>Contrôler la collecte des données
 Pendant l’exécution de l’application cible, vous pouvez contrôler la collecte des données en démarrant et en arrêtant l’écriture des données dans le fichier de données du profileur à l’aide des options de *VSPerfCmd.exe*. Le fait de pouvoir contrôler la collecte vous permet de collecter des données pour une phase spécifique de l’exécution du programme, telle que le démarrage ou l’arrêt de l’application.

#### <a name="to-start-and-stop-data-collection"></a>Pour démarrer et arrêter la collecte de données

- Les paires d’options suivantes permettent de démarrer et d’arrêter la collecte des données. Spécifiez chaque option sur une ligne de commande distincte. Vous pouvez activer et désactiver la collecte de données à plusieurs reprises.

    |Option|Description|
    |------------|-----------------|
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Démarre (**/globalon**) ou arrête (**/globaloff**) la collecte des données pour tous les processus.|
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:**  `PID`|Démarre (**/processon**) ou arrête (**/processoff**) la collecte des données pour le processus spécifié par l’ID de processus (`PID`).|
    |[/attacher](../profiling/attach.md) **:**:`PID`&#124;`ProcName`'/détache '**' '** `ProcName`' ' ' ' ' '&#124;' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' [' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '](../profiling/detach.md)`PID`|**/attach** commence à collecter des données pour le processus spécifié par le `PID` ou le nom de processus (ProcName). **/détacher** arrête la collecte de données pour le processus spécifié ou pour tous les processus si un processus spécifique n’est pas spécifié.|

## <a name="end-the-profiling-session"></a>Arrêter la session de profilage
 Pour que vous puissiez mettre fin à une session de profilage, le profileur ne doit plus être attaché à un processus profilé et doit être arrêté explicitement. Vous pouvez détacher le profileur d’une application profilée avec la méthode d’échantillonnage en fermant l’application ou en appelant l’option **VSPerfCmd /detach**. Vous devez alors appeler l’option **VSPerfCmd /shutdown** pour désactiver le profileur et fermer le fichier de données de profilage. La commande **VSPerfClrEnv /off** efface les variables d’environnement de profilage.

#### <a name="to-end-a-profiling-session"></a>Pour terminer une session de profilage

1. Effectuez l’une des opérations suivantes pour détacher le profileur de l’application cible :

    - Fermez l’application cible.

         -ou-

    - Type **VSPerfCmd /detach**

2. Fermez le profileur. Tapez :

     **VSPerfCmd**  [/shutdown](../profiling/shutdown.md)

## <a name="see-also"></a>Voir aussi
- [Profiler des applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Vues de données sur les méthodes d’échantillonnage](../profiling/profiler-sampling-method-data-views.md)
