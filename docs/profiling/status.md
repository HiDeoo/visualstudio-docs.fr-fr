---
title: Status | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ba656fa4-ef9d-4d8c-a3b6-739c3b5d23ae
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: bf5e0fdf478e067f61b1d0e259cb1624380e4f02
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "74778243"
---
# <a name="status"></a>État
L’option **État** de la *VSPerfCmd.exe* affiche des informations sur l’état du profileur et les processus en cours de profilage.

 L’option **Status** doit être la seule option spécifiée sur la ligne de commande. Le profileur doit être initialisé avec l’option *VSPerfCmd.exe* **Start** avant de pouvoir afficher un État.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Status
```

#### <a name="parameters"></a>Paramètres
 None

## <a name="remarks"></a>Notes
 L’option **Status** affiche les informations d’état suivantes pour le profileur.

 **Nom du fichier de sortie** Chemin et nom du fichier de données du profileur actif.

 **Mode de collecte** SAMPLE ou TRACE

 **Nombre maximal de processus** Nombre maximal de processus qui peuvent être profilés simultanément, et nombre de processus actifs.

 **Nombre maximal de threads** Nombre maximal de threads qui peuvent être profilés simultanément.

 **Nombre de mémoires tampons** Nombre de mémoires tampons dédiées à l’écriture des données de profilage.

 **Taille des mémoires tampons** Taille en octets d’une mémoire tampon.

 L’option **Status** affiche les informations d’état suivantes pour chaque processus en cours de profilage.

 **Processus** Nom du processus profilé.

 **ID de processus** Identificateur système du processus.

 **Nombre de threads** Nombre de threads en cours d’exécution.

 **Nombre Start/Stop global** Compteur interne principal du profileur pour contrôler la collecte des données de ce processus. Le compteur doit être égal à un pour collecter des données. Le nombre de Start/Stop peut être manipulé par les API du profileur et les options de VSPerfCmd **GlobalOn**, **GlobalOff**, **ProcessOn**, **ProcessOff**, **ThreadOn** et **ThreadOff**.

 **Nombre de Suspend/Resume** Compteur interne secondaire du profileur pour contrôler la collecte de données de ce processus. Le compteur doit être inférieur ou égal à zéro pour que des données soient collectées. Le nombre de **Suspend/Resume** peut être manipulé seulement par les API du profileur.

 **Utilisateurs avec droits d’accès au gestionnaire** Liste les noms des utilisateurs qui ont accès au profileur. Vous pouvez accorder l’accès à des utilisateurs supplémentaires en utilisant l’option **Admin** de VSPerfCmd.exe

## <a name="see-also"></a>Voir aussi
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Profiler des applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Profiler des applications Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profiler des services](../profiling/command-line-profiling-of-services.md)
