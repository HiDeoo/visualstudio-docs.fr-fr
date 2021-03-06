---
title: ProcessOn et ProcessOff | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: d3dc6a7e-bc0f-48a6-a4ec-f386348bb296
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 77e21a280700520b6861dd42e01a4aefa4faa704
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68180201"
---
# <a name="processon-and-processoff"></a>ProcessOn et ProcessOff
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Les sous commandes **ProcessOff** et **ProcessOn** de VSPerfCmd.exe permettent de suspendre et de reprendre le profilage pour le processus spécifié dans une session de profilage en ligne de commande. **ProcessOff** arrête le profilage du processus et **ProcessOn** le démarre.  
  
 Dans la plupart des cas, vous spécifiez **ProcessOn** ou **ProcessOff** comme seule option d’une ligne de commande VSPerfCmd.exe, mais elles peuvent aussi être combinées avec les sous-commandes **GlobalOn**, **GlobalOff**, **ThreadOn** et **ThreadOff**.  
  
 Les sous-commandes **ProcessOn** et **ProcessOff** interagissent avec les sous-commandes **GlobalOn** et **GlobalOff** qui contrôlent la collecte de données pour tous les processus dans une session de profilage en ligne de commande, et avec les sous-commandes **ThreadOn** et **ThreadOff** qui contrôlent la collecte de données pour un thread spécifié.  
  
 Les sous-commandes **ProcessOff** et **ProcessOn** affectent également le nombre de démarrage/arrêt de processus qui est manipulé par les fonctions d’API du profileur.  
  
- **ProcessOff** définit immédiatement le nombre de démarrage/arrêt de processus sur 0 et suspend ainsi le profilage.  
  
- **ProcessOn** définit immédiatement le nombre de démarrage/arrêt de processus sur 1 et reprend ainsi le profilage.  
  
  Pour plus d’informations, consultez [outils de profilage des API](../profiling/profiling-tools-apis.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /{ProcessOff|ProcessOn}:PID [Options]  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `PID`  
 L’identificateur entier du processus à démarrer ou à arrêter. Les ID de processus sont répertoriés sous l’onglet Processus du Gestionnaire des tâches de Windows.  
  
## <a name="required-subcommands"></a>Sous-commandes obligatoires  
 None  
  
## <a name="valid-subcommands"></a>Sous-commandes valides  
 Vous pouvez spécifier **ProcessOn** et **ProcessOff** sur des lignes de commande qui contiennent également les sous-commandes suivantes.  
  
 **Démarrer :**`Method`  
 Initialise la session de profilage en ligne de commande et définit la méthode de profilage spécifiée.  
  
 **Lancer :**`AppName`  
 Démarre l’application spécifiée et commence le profilage avec la méthode d’échantillonnage.  
  
 **Attacher :**`PID`  
 Démarre le profilage du processus spécifié.  
  
 **GlobalOff**&#124;**GlobalOn**  
 Arrête ou démarre le profilage de tous les processus d’une session de profilage en ligne de commande.  
  
 {**Threadoff**&#124;**ThreadOn**} **:**`TID`  
 Arrête ou démarre le profilage pour le thread spécifié (méthode d’instrumentation uniquement).  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, la sous-commande **ProcessOff** est utilisé pour collecter des données de profilage pour le démarrage de l’application.  
  
```  
; Initialize the profiler.  
VSPerfCmd.exe /Start:Trace /Output:Instrument.vsp   
; Start the instrumented application.  
; Stop profiling the process after startup.  
VSPerfCmd.exe /ProcessOff:12345  
; Shut down the target application.  
; Close the profiler.  
VSPerfCmd /Shutdown  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Option](../profiling/vsperfcmd.md)   
 [Profilage d’applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilage d’applications Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilage des services](../profiling/command-line-profiling-of-services.md)
