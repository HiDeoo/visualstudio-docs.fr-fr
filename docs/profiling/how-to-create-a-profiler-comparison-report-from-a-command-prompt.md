---
title: Créer un rapport de comparaison du profileur (ligne de commande)
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: d370a7465428da4f2582f4f765c1d81ae017af48
ms.sourcegitcommit: 566144d59c376474c09bbb55164c01d70f4b621c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/19/2020
ms.locfileid: "90809386"
---
# <a name="how-to-create-a-profiler-comparison-report-from-a-command-prompt"></a>Guide pratique pour créer un rapport de comparaison du profileur à partir d’une invite de commandes
Vous pouvez générer un rapport des Outils de profilage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] qui compare les données de performances de deux fichiers de données de profilage (.*vsp* ou .*vsps*). Le rapport montre les différences, les régressions de performances et les améliorations qui se sont produites d’une session de profilage à l’autre. Les valeurs du rapport présentent le delta, ou la modification, à partir de la base de référence du premier fichier que vous spécifiez. Le delta est calculé en déterminant la différence entre l’ancienne valeur, qui est la valeur de la base de référence, et la valeur résultant de la nouvelle analyse. Les comparaisons des données du profileur peuvent être basées sur les fonctions du code, les modules de l’application, les lignes, les pointeurs d’instruction et les types.

 Pour lister les identificateurs des catégories et des champs de la comparaison, tapez la ligne de commande suivante :

 **VSPerfReport /querydifftables**  *NomFichierVsp1* *NomFichierVsp2*

 Utilisez la syntaxe suivante pour créer le rapport de comparaison :

 **VSPerfReport/diff** `VspFileName1` *Nomfichiervsp2* [ **/** `Options` ]  

 Vous pouvez ajouter des options du tableau suivant à la ligne de commande **VSPerfReport /diff**.

|Option|Description|
|------------|-----------------|
|**DiffThreshold:**[*Valeur*]|Ignore la différence si elle est inférieure à cette valeur de seuil de pourcentage. De même, les nouvelles données avec des valeurs inférieures à ce seuil n’apparaissent pas.|
|**DiffTable:** *NomTableau*|Utilise ce tableau pour comparer les fichiers. Par défaut, le tableau des fonctions est utilisé. Spécifiez l’identificateur qui est répertorié dans **VSPerfReport /querydifftables**.|
|**DiffColumn:** *NonColonne*|Utiliser cette colonne pour comparer les valeurs. Par défaut, la colonne de pourcentage d’échantillons exclusifs est utilisée. Spécifiez l’identificateur qui est répertorié dans **VSPerfReport /querydifftables**.|
