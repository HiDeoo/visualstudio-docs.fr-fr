---
title: PF | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: cdc0a094-a986-4629-bd1c-dd5fdca323dc
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 243d5fada7342bc05d8768a7e33cca6f55e309ef
ms.sourcegitcommit: fb8babf5cd72f1fc2f97ffe4ad7b62d91f325f61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2020
ms.locfileid: "90839810"
---
# <a name="pf"></a>PF
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

L’option **PF** de VSPerfCmd.exe définit l’événement de profilage qui est échantillonné lors des défauts de page. Elle peut changer le nombre de défauts de page dans un intervalle d’échantillonnage (la valeur par défaut est 10).  
  
> [!NOTE]
> Vous ne pouvez pas utiliser PF sur les systèmes 64 bits.  
  
 **Notez que PF** n’est pas pris en charge sur les ordinateurs 64 bits. **PF** peut être utilisé seulement dans une ligne de commande qui contient également l’option **Launch** ou **Attach**.  
  
 Par défaut, l’événement d’échantillonnage du profileur est défini sur les cycles d’horloge du processeur hors interruption, et l’intervalle d’échantillonnage est défini sur 10 000 000. Les options **Timer**, **PF**, **Sys** et **Counter** vous permettent de définir l’événement d’échantillonnage et l’intervalle d’échantillonnage. L’option **GC** collecte les données de mémoire .NET à chaque événement d’allocation et de garbage collection. Vous ne pouvez spécifier qu'une seule de ces options sur une ligne de commande.  
  
 Vous pouvez définir l’événement d’échantillonnage et l’intervalle d’échantillonnage seulement sur la première ligne de commande qui contient une option **Launch** ou **Attach**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe {/Launch:AppName|/Attach:PID} /PF[:Events] [Options]  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Events`  
 Valeur entière qui spécifie le nombre d’événements de défaut de page dans un intervalle d’échantillonnage. Si `Events` n’est pas spécifié, l’intervalle est défini sur 10.  
  
## <a name="required-options"></a>Options obligatoires  
 Vous pouvez spécifier **PF** seulement sur une ligne de commande qui contient une des options suivantes.  
  
 **Lancer :**`AppName`  
 Démarre le profileur et l’application spécifiée par AppName.  
  
 **Attacher :**`PID`  
 Attache le profileur au processus spécifié par AppName.  
  
## <a name="invalid-options"></a>Options non valides  
 Vous ne pouvez pas spécifier les options suivantes sur la même ligne de commande que **PF**.  
  
 **Minuteur**[**:** `Cycles` ]  
 Définit l’événement d’échantillonnage sur les cycles d’horloge du processeur et définit éventuellement l’intervalle d’échantillonnage sur `Cycles`. L’intervalle de Timer par défaut est 10,000,000.  
  
 **Sys**[**:** `Events` ]  
 Définit l’événement d’échantillonnage comme étant des appels de l’application profilée au noyau du système d’exploitation (syscalls), et définit éventuellement l’intervalle d’échantillonnage sur `Events`. L'intervalle Sys par défaut est 10.  
  
 **Compteur :** `Name` [`,Reload`[`,FriendlyName`]]  
 Définit l'événement d'échantillonnage sur le compteur de performance d'UC spécifié par `Name` et définit l'intervalle d'échantillonnage sur `Reload`.  
  
 **GC**[**:**{**Allocation**&#124;**Lifetime**}]  
 Recueille des données de mémoire .NET. Par défaut (**allocation**), les données sont collectées à chaque événement d’allocation de mémoire. Quand le paramètre **Lifetime** est spécifié, les données sont également collectées à chaque événement garbage collection.  
  
## <a name="example"></a> Exemple  
 Cet exemple montre comment définir l’événement d’échantillonnage du profilage sur les défauts de page, et comment définir l’intervalle d’échantillonnage sur 20 défauts de page.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /PF:20  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Option](../profiling/vsperfcmd.md)   
 [Profilage d’applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilage d’applications Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilage des services](../profiling/command-line-profiling-of-services.md)
