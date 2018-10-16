---
title: Guide pratique pour générer un répertoire de sortie commun | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- output directory
- builds [Visual Studio], common directory
- common directory
ms.assetid: 1fcc2c48-07cb-4c4f-9556-36945e7dfc4e
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8e53b6e110040763c93c2786e81d82f105fa5eb2
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49292056"
---
# <a name="how-to-build-to-a-common-output-directory"></a>Comment : générer un répertoire de sortie commun
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Par défaut, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] génère chaque projet dans une solution dans son propre dossier à l’intérieur de la solution. Vous pouvez changer les chemins de sortie de build de vos projets pour imposer que toutes les sorties soient placées dans le même dossier.  
  
### <a name="to-place-all-solution-outputs-in-a-common-directory"></a>Pour placer toutes les sorties de solution dans un répertoire commun  
  
1.  Cliquez sur un projet dans la solution.  
  
2.  Dans le menu **Projet**, cliquez sur **Propriétés**.  
  
3.  En fonction du type de projet, cliquez sur l’onglet **Compiler** ou sur l’onglet **Générer**, puis définissez comme **Chemin de sortie** un dossier à utiliser pour tous les projets de la solution.  
  
4.  Répétez les étapes 1 à 3 pour tous les projets de la solution.  
  
## <a name="see-also"></a>Voir aussi  
 [Compilation et génération](../ide/compiling-and-building-in-visual-studio.md)   
 [Guide pratique pour modifier le répertoire de sortie de la génération](../ide/how-to-change-the-build-output-directory.md)



