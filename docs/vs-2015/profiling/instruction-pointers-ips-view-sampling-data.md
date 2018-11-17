---
title: Pointeurs d’instruction (IP), vue - Données d’échantillonnage | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: c7f647bb-c5a3-4708-9f9d-33c0fd6e2e96
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7bd936d9483469900a679ad08aada4bcf9235e78
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51721963"
---
# <a name="instruction-pointers-ips-view---sampling-data"></a>Pointeurs d’instruction (IP), vue - Données d’échantillonnage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La vue Pointeurs d’instruction des données d’échantillonnage répertorie les données de performance pour les instructions d’assembly qui s’exécutaient directement lors de la collecte des échantillons dans le cadre de l’exécution du profilage.  
  
> [!NOTE]
>  Les fonctionnalités de sécurité renforcée de Windows 8 et Windows Server 2012 ont imposé des changements importants dans la façon dont le profileur Visual Studio collecte les données sur ces plateformes. Les applications Windows Store demandent aussi de nouvelles techniques de collecte. Consultez [Outils d’analyse des performances sur les applications Windows 8 et Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
|Colonne|Description|  
|------------|-----------------|  
|**ID du processus**|ID du processus (PID) de l'exécution du profilage.|  
|**Nom du processus**|Nom du processus.|  
|**Nom du module**|Nom du module qui contient l’instruction.|  
|**Chemin du module**|Chemin du module qui contient l’instruction.|  
|**Fichier source**|Fichier source qui contient l’instruction.|  
|**Nom de la fonction**|Nom de la fonction qui contient l’instruction.|  
|**Numéro de ligne de fonction**|Numéro de ligne du début de cette fonction dans le fichier source.|  
|**Adresse de la fonction**|Adresse mémoire de départ de la fonction dans le fichier binaire chargé.|  
|**Début ligne source**|Numéro de la ligne de début dans le fichier source au niveau duquel cet échantillon a été collecté.|  
|**Fin ligne source**|Numéro de ligne de fin dans le fichier source au niveau duquel cet échantillon a été collecté.|  
|**Début caractère source**|Décalage du caractère de début dans la ligne de fichier source au niveau de laquelle cet échantillon a été collecté.|  
|**Fin du caractère source**|Décalage du caractère de fin dans la ligne de fichier source au niveau de laquelle cet échantillon a été collecté.|  
|**Adresse d’instruction**|Adresse de l’instruction dans le fichier binaire chargé.|  
|**Échantillons exclusifs**|Nombre total d’échantillons collectés pendant l’exécution de l’instruction.|  
|**% d’échantillons exclusifs**|Pourcentage de tous les échantillons collectés pendant l’exécution de l’instruction dans le cadre de l’exécution du profilage.|  
  
## <a name="see-also"></a>Voir aussi  
 [Pointeurs d’instruction (IP), vue - Échantillonnage](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)



