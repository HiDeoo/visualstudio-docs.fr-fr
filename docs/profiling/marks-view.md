---
title: Marques, vue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.view.marks
helpviewer_keywords:
- profiling tools, Marks view
- profiling tools reports, Marks view
ms.assetid: b2773344-8081-4116-85a1-58f770448f6a
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 4d7483f309a3d7edb92d25c34e9665a6212c8038
ms.sourcegitcommit: 4ae5e9817ad13edd05425febb322b5be6d3c3425
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/11/2020
ms.locfileid: "90037515"
---
# <a name="marks-view"></a>Marques, vue
La vue Marques affiche l’échantillonnage et les événements ETW qui ont été insérés dans l’application.

 Les marques par défaut qui sont préremplies dans le rapport indiquent le démarrage du programme et la fin du programme.

 Les données des compteurs Windows provenant de marques générées automatiquement sont également présentées dans cette vue. Pour plus d’informations, consultez [Comment : collecter des données de compteur Windows](../profiling/how-to-collect-windows-counter-data.md).

 Pour créer un filtre entre deux marques, sélectionnez les marques, cliquez avec le bouton droit puis cliquez sur **Ajouter un filtre par marques** ou **Ajouter un filtre par horodatage**.

 Le tableau suivant contient les définitions des colonnes qui sont disponibles dans la vue Marques.

 **ID de marque** Identificateur unique de la marque de profilage.

 **Nom de marque** Nom de l’événement.

 **Horodatage** Durée entre l’heure de début du profilage et l’heure à laquelle l’événement est enregistré.

 Données du compteur de performances Quand des données de compteur de performances Windows sont collectées, les valeurs sont affichées dans une colonne portant le même nom que le compteur.

## <a name="see-also"></a>Voir aussi
- [Présentation du rapport de performances](../profiling/performance-report-overview.md)
- [Comment : collecter les données des compteurs Windows](../profiling/how-to-collect-windows-counter-data.md)
- [&#91;fenêtre de contrôle de la collecte de données&#93; de plume](/previous-versions/bb385767(v=vs.110))