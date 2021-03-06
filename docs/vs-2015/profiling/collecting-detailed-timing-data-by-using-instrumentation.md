---
title: Collecte de données de minutage détaillées à l’aide de l’instrumentation | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,instrumentation method
- instrumentation profiling method
ms.assetid: e9deb370-c459-45ac-84d3-14d646590d05
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c129ddf016e02fe6c29d5cf63fe57ba07fbd4e95
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68176645"
---
# <a name="collecting-detailed-timing-data-by-using-instrumentation"></a>Collecte de données de minutage détaillées à l’aide de l’instrumentation
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La méthode d’instrumentation des outils de profilage [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] injecte le code de profilage dans une copie d’un module. Le code enregistre chaque entrée, sortie et appel des fonctions dans le module pendant une exécution du profilage. La méthode d’instrumentation est utile pour rassembler des informations de temporisation détaillées sur une section de votre code et comprendre l’impact des opérations d’entrée et de sortie sur les performances de l’application.  
  
 Vous pouvez spécifier la méthode d’instrumentation à l’aide de l’une des procédures suivantes :  
  
- Dans la première page de l’Assistant Profilage, sélectionnez **Instrumentation**.  
  
- Dans la barre d’outils de l’ **Explorateur de performances** , dans la liste **Méthode** , cliquez sur **Instrumentation**.  
  
- Dans la page **Général** de la boîte de dialogue Propriétés de la session de performance, sélectionnez **Instrumentation**.  
  
## <a name="common-tasks"></a>Tâches courantes  
 Vous pouvez spécifier des options supplémentaires dans la boîte de dialogue des _pages de propriétés_**session de performance** . Pour ouvrir la boîte de dialogue :  
  
- Dans **Explorateur de performances**, cliquez avec le bouton droit sur le nom de la session de performance, puis cliquez sur **Propriétés**.  
  
  Les tâches du tableau suivant décrivent les options que vous pouvez spécifier dans la boîte de dialogue des**pages de propriétés** de la _session de performance_lorsque vous profilez à l’aide de la méthode d’instrumentation.  
  
|Tâche|Contenu associé|  
|----------|---------------------|  
|Dans la page **Général** , ajoutez l’allocation de mémoire .NET et les données de durée de vie, et spécifiez les détails d’affectation de noms pour le fichier de données de profilage (.vsp) généré.|-   [Collecte de données liées à l’allocation et à la durée de vie de la mémoire .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Procédure : définir les options de nom de fichier de données de performances](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Dans la page **Lancer** , si vous avez plusieurs projets .exe dans votre solution, spécifiez l’application à démarrer et l’ordre de démarrage.|-   [Comment : spécifier le binaire à démarrer](../profiling/how-to-specify-the-binary-to-start.md)|  
|Dans la page **Fichiers binaires** , spécifiez un emplacement pour les copies instrumentées des modules. Par défaut, les fichiers binaires d’origine sont déplacés vers un dossier de sauvegarde.|-   [Comment : déplacer des binaires instrumentés](../profiling/how-to-relocate-instrumented-binaries.md)|  
|Dans la page **Interaction de couche** , ajoutez les données d’appel ADO.NET à l’exécution du profilage.|-   [Collecte des données d’interaction de couche](../profiling/collecting-tier-interaction-data.md)|  
|Dans la page **Instrumentation** , excluez les petites fonctions du profilage pour réduire les surcharges de profilage, profilez le code JavaScript dans des pages web ASP.NET et spécifiez les commandes à exécuter dans une invite de commandes avant et après le processus d’instrumentation.|-   [Comment : exclure ou inclure les fonctions courtes de l’instrumentation](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)<br />-   [Comment : profiler du code JavaScript dans des pages Web](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [Comment : spécifier des commandes de pré-instrumentation et de publication](../profiling/how-to-specify-pre-and-post-instrument-commands.md)|  
|Dans la page **Compteurs UC** , spécifiez un ou plusieurs compteurs de performance du processeur à ajouter aux données de profilage.|-   [Procédure : collecter les données des compteurs UC](../profiling/how-to-collect-cpu-counter-data.md)|  
|Dans la page **Événements Windows** , sélectionnez un ou plusieurs événements de suivi d’événements pour Windows (ETW) à collecter avec les données d’échantillonnage.|-   [Comment : collecter des données Suivi d’v nements pour Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|  
|Dans la page **Compteurs Windows** , spécifiez un ou plusieurs compteurs de performance de système d’exploitation à ajouter aux données de profilage en tant que marques.|-   [Guide pratique pour collecter les données des compteurs Windows](../profiling/how-to-collect-windows-counter-data.md)|  
|Dans la page **Avancé** , spécifiez les options supplémentaires que vous voulez passer au programme d’instrumentation VSInstr, notamment les options permettant d’inclure ou d’exclure des fonctions spécifiques.|-   [Comment : spécifier des options d’instrumentation supplémentaires](../profiling/how-to-specify-additional-instrumentation-options.md)<br />-   [Comment : limiter l’instrumentation à des fonctions spécifiques](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [VSInstr](../profiling/vsinstr.md)|
