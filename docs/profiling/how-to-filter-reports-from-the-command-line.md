---
title: Filtrer des rapports à partir de la ligne de commande | Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 1b6408975e8a3d7189db26913f3de75ad1c7c595
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90851136"
---
# <a name="how-to-filter-reports-from-the-command-line"></a>Guide pratique pour filtrer des rapports à partir de la ligne de commande
En utilisant les options de la commande **VSPerfReport**, vous pouvez filtrer des rapports sur un segment de temps spécifique du fichier de données de profilage, ou restreindre les données à un ou plusieurs processus ou threads. Pour plus d’informations sur cette commande, consultez [VSPerfReport](../profiling/vsperfreport.md).

|Options|Description|
|-------------|-----------------|
|**StartTime:**[*Valeur*]|Affiche uniquement les données collectées après la valeur (en millisecondes).|
|**EndTime:**[*Valeur*]|Affiche uniquement les données collectées avant la valeur (en millisecondes).|
|**FilterFile:** `VSPFFile`|Spécifie l’emplacement d’un fichier de filtre qui a été généré à partir de la fenêtre **Rapport de performances de Visual Studio**.|
|**MsFilter:**[*StartTime,Duration*]|Affiche uniquement les données de `StartTime` jusqu’à la fin de `Duration` (en millisecondes).|
|**Process:**[*Pid*]|Affiche uniquement les données du processus spécifié.|
|**Thread:**[*ThreadID*]|Affiche uniquement les données du thread spécifié.|
|**Thread:**[*ThreadID,ProcessID*]|Affiche uniquement les données du thread spécifié qui est associé au processus spécifié.|
