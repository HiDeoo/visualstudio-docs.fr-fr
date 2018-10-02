---
title: Guide pratique pour définir les options de nom de fichier de données de profilage | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7a8d6b9-ab23-46fb-98ed-774781157860
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 19a29c143ecc2ce413e6f6480b2c49e52277af3f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47501776"
---
# <a name="how-to-set-performance-data-file-name-options"></a>Guide pratique pour définir les options de nom de fichier de données de profilage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [Comment : définir les Options Nom performances données fichier](https://docs.microsoft.com/visualstudio/profiling/how-to-set-performance-data-file-name-options).  
  
Par défaut, vous enregistrez un fichier de données de profilage (.vsp) à l’aide de la syntaxe suivante :  
  
 *Chemin\Fichier_VSP\AAMMJJ(N)* **.vsp**  
  
 Vous pouvez modifier tout paramètre d’attribution de nom dans la page Général de la boîte de dialogue des propriétés pour la session de performance.  
  
 **Spécifications**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
|||  
|-|-|  
|*Chemin*|Répertoire qui contient le rapport. L’emplacement par défaut est le dossier de solution ou l’emplacement par défaut pour les projets et solutions de l’utilisateur.|  
|*Fichier_VSP*|Nom du fichier de données de profilage. Le nom par défaut est le nom de la solution ou du fichier exécutable profilés.|  
|*AAMMJJ*|Horodatage qui affiche l’année, le mois et le jour auxquels les données de profilage ont été collectées.|  
|*(N)*|S’il existe plusieurs fichiers de données de profilage, un nombre incrémenté est ajouté entre parenthèses au nom du fichier.|  
  
### <a name="to-change-the-naming-syntax-of-the-profiling-data-files-of-a-performance-session"></a>Pour modifier la syntaxe d’attribution de noms des fichiers de données de profilage d’une session de performance  
  
1.  Dans l’**Explorateur de performances**, cliquez avec le bouton droit sur le nom de la session de performance, puis cliquez sur **Propriétés**.  
  
2.  Cliquez sur **Général**.  
  
3.  Sous **Rapport**, modifiez les paramètres suivants :  
  
    |||  
    |-|-|  
    |**Emplacement du rapport**|Spécifiez un répertoire pour le stockage des fichiers de données de profilage.|  
    |**Nom du rapport**|Spécifiez un nom de base pour les fichiers.|  
    |**Ajouter automatiquement de nouveaux rapports à la session**|Cochez la case pour ajouter automatiquement le fichier de données à la session de performance.|  
    |**Ajouter un numéro à incrémentation aux rapports générés**|Cochez la case pour ajouter un numéro à incrémentation au nom du fichier quand il existe plusieurs fichiers du même nom. Décochez la case pour remplacer un fichier existant.|  
    |**Utiliser un horodatage pour le nombre**|Cochez la case pour ajouter un horodatage au nom du fichier.|



