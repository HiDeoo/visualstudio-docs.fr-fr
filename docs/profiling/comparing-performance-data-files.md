---
title: Comparaison des fichiers de données de performances | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, comparing profiling tools report files
- profiling tools reports, comparing
ms.assetid: e6fda144-f21d-4912-9d16-1b8d3555a210
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 64842c5b4f622a1f76aa528360f79403ec92cb42
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "74777853"
---
# <a name="compare-performance-data-files"></a>Comparer des fichiers de données de performances

Outils de profilage fonctionnalité de comparaison de fichiers de données vous permet de sélectionner deux fichiers de rapport (.* vsp* /. *vsps*) fichiers et générer un rapport qui affiche les différences, les régressions de performances et les améliorations qui se sont produites d’une session de profilage à l’autre.

Dans un rapport de comparaison de fichiers de données des outils de profilage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], les résultats d’une analyse d’un fichier de données de profilage sont comparés aux résultats d’une analyse de base de référence d’un autre fichier de données. Les deux fichiers de données doivent avoir été générés à l’aide de la même méthode de profilage. Le rapport des comparaisons analysées est enregistré sous la forme d’un. fichier *vsps* .

La vue du rapport de comparaison présente les données modifiées sous la forme d’un tableau. Le tableau présente les données delta, c’est-à-dire ce qui a été modifié par rapport à la base de référence. Les données delta sont calculées en déterminant la différence entre l’ancienne valeur, la valeur de base de référence et la valeur résultant de la nouvelle analyse.

Les comparaisons des données du profileur peuvent être basées sur les fonctions du code, les modules de l’application, les lignes, les pointeurs d’instruction et les types.

Les données de profilage qui peuvent être utilisées pour la comparaison comprennent des informations qui sont affichées dans les colonnes. Pour obtenir les définitions de ces noms de colonnes, consultez [vues des rapports de performances](../profiling/performance-report-views.md).

Vous pouvez définir un seuil pour réduire le bruit et exclure de l’affichage les lignes du tableau de comparaison dont la valeur n’a pas changé de manière significative.

## <a name="in-this-section"></a>Contenu de cette section

[Comment : comparer des fichiers de données de performances](../profiling/how-to-compare-performance-data-files.md)
