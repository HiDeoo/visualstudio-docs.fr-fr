---
title: Processus, vue - Données de conflit | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Process view
ms.assetid: 8821d98c-0771-43b2-a38b-e9039a3abd75
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 30c938088538bcecc71e3a7e37d5ae403dd476e1
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "74778399"
---
# <a name="process-view---contention-data"></a>Processus, vue - données de conflit
La vue Processus affiche les données de conflit pour les processus et les threads exécutés pendant l’exécution du profilage.

 Quand des symboles sont disponibles, les processus sont répertoriés par nom. Si aucun symbole n’est disponible, les processus sont répertoriés par adresse mémoire, au format hexadécimal. Les threads sont répertoriés en tant qu’enfants du processus qui les a créés.

 Le tableau suivant explique les valeurs des colonnes dans la vue Processus.

|Colonne|Description|
|------------|-----------------|
|**Heure de début**|Nombre de millisecondes ou de cycles processeur entre le début du profilage et le début du processus ou du thread.|
|**Temps de blocage**|Durée totale pendant laquelle l’exécution des fonctions du processus ou du thread a été bloquée.|
|**% de temps bloqué**|Pourcentage de la durée de vie du processus ou du thread pendant laquelle l’exécution des fonctions du processus ou du thread a été bloquée.|
|**Conflits**|Nombre de fois où l’exécution des fonctions du processus ou du thread a été bloquée.|
|**% de conflits**|Pourcentage de tous les conflits dans l’exécution du profilage qui étaient des conflits du processus ou du thread.|
|**Heure de fin**|Nombre de millisecondes ou de cycles processeur entre le début du profilage et la fin du processus ou du thread.|
|**Identifiant**|Identificateur du processus ou du thread généré par le système.|
|**Durée de vie**|Nombre de millisecondes ou de cycles processeur entre le début du processus ou du thread et soit la fin du processus ou du thread, soit la fin du profilage.|
|**Type**|Type de ligne (processus ou thread).<br /><br /> Uniquement dans les rapports en ligne de commande **VSReport**. Pour plus d’informations, consultez [VSPerfReport](../profiling/vsperfreport.md).|
|**Name**|Nom du processus ou du thread.|
|**ID unique**|Identificateur généré par le profileur unique pour le processus ou le thread.|

## <a name="see-also"></a>Voir aussi
- [Guide pratique pour personnaliser les colonnes de la vue de rapport](../profiling/how-to-customize-report-view-columns.md)
- [Vue Processus](../profiling/process-view.md)
