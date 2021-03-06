---
title: Counter | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: aa4b4cdb-e6ea-433a-9579-56f3785e1385
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5da78c33af599accf5ff3a2e09a9afb52982573a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68149280"
---
# <a name="counter"></a>Compteur
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

L’option **Counter** collecte les données des compteurs de performance de processeur (matériels).  
  
- Quand vous utilisez la méthode de profilage par échantillonnage, **Counter** spécifie le compteur de performance de processeur et le nombre d’événements de compteur à utiliser comme intervalle d’échantillonnage. Vous ne pouvez spécifier qu’un seul compteur si vous utilisez l’échantillonnage.  
  
- Quand vous utilisez la méthode de profilage par instrumentation, le nombre d’événements de compteur qui se sont produits dans l’intervalle entre les événements de collecte précédent et actuel est répertorié sous la forme de champs distincts dans les rapports du profileur. Vous pouvez spécifier plusieurs options **Counter** si vous utilisez l’instrumentation.  
  
  Chaque type de processeur dispose de son propre jeu de compteurs de performance matériels. Le profileur définit un jeu de compteurs de performance génériques qui sont communs à presque tous les processeurs. Pour répertorier les compteurs génériques et spécifiques au processeur sur votre ordinateur, utilisez la commande VSPerfCmd **QueryCounters**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe {/Launch:AppName | /Attach PID} /Counter:Name[,Reload[,FriendlyName]][Options]  
```  
  
```  
VSPerfCmd.exe /Start:Method /Counter:Name[,Reload[,FriendlyName]][/Counter:Name[,Reload[,FriendlyName]]][Options]  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Name`  
 Nom du compteur. Utilisez l’option VSPerfCmd.exe **/QueryCounters** pour répertorier les noms des compteurs disponibles sur l’ordinateur.  
  
 `Reload`  
 Nombre d’événements de compteur dans l’intervalle d’échantillonnage. N’utilisez pas ce paramètre avec la méthode par instrumentation.  
  
 `FriendlyName`  
 (Facultatif) Chaîne à utiliser à la place de `Name` dans les en-têtes de colonnes des rapports et des vues du profileur.  
  
## <a name="required-options"></a>Options obligatoires  
 L’option Counter peut uniquement être utilisée avec l’une des options suivantes :  
  
 **Démarrer :**`Trace`  
 Initialise le profileur pour utiliser la méthode d’instrumentation.  
  
 **Lancer :**`AppName`  
 Démarre l’application spécifiée et le profileur. Le profileur doit être initialisé pour utiliser la méthode par échantillonnage.  
  
 **Attacher :**`PID`  
 Démarre le profileur et l’attache au processus spécifié par l’ID de processus. Le profileur doit être initialisé pour utiliser la méthode par échantillonnage.  
  
## <a name="example"></a>Exemple  
 L’exemple de méthode par échantillonnage montre comment échantillonner une application toutes les 1 000 occurrences du compteur de profileur générique NonHaltedCycles.  
  
 L’exemple de méthode par instrumentation montre comment initialiser le profileur pour collecter les événements de compteur L2InstructionFetches. Le nom de compteur L2InstructionFetches est spécifique au processeur.  
  
```  
; Sample Method Example  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Counter:NonHaltedCycles,1000,"Non-Halted Cycles"  
  
;INSTRUMENTATION METHOD EXAMPLE  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /Counter:L2InstructionFetches,,"L2 Cache Instruction Fetches"  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Option](../profiling/vsperfcmd.md)   
 [Profilage d’applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilage d’applications Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilage des services](../profiling/command-line-profiling-of-services.md)
