---
title: Rechercher des problèmes potentiels à l’aide d’analyseurs de carte de code | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- vs.progression.codemapanalyzers
helpviewer_keywords:
- code analysis, dependency graphs
- dependency graphs, analyzing code
- graph documents, analyzing
ms.assetid: 9dd799a7-f7eb-42ff-8612-b19dde7ff4eb
caps.latest.revision: 13
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: fc5d185640c9623a2213aaf7ad50fa68a088b15c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72669615"
---
# <a name="find-potential-problems-using-code-map-analyzers"></a>Rechercher des problèmes potentiels à l’aide des analyseurs de carte du code
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Exécutez des analyseurs sur des cartes de code pour vous aider à identifier le code susceptible d’être trop complexe ou de devoir être amélioré. Vous pouvez par exemple utiliser ces analyseurs :

|**Pour rechercher du code ayant**|**Examinez ces zones pour voir si**|
|-------------------------------|--------------------------------------------|
|Des boucles ou des dépendances circulaires|Vous pouvez les simplifier et envisager de rompre ces cycles.|
|Trop de dépendances|Elles exécutent trop de fonctions ou pour déterminer l’impact de la modification de ces zones. Une carte de code correcte affiche un nombre minimal de dépendances. Pour que le code soit plus facile à tenir à jour, à modifier, à tester et à réutiliser, essayez de refactoriser ces zones pour qu’elles soient plus clairement définies ou de fusionner du code qui exécute des fonctions similaires.|
|Aucune dépendance|Elles sont nécessaires ou si vous devez supprimer ce code.|

## <a name="analyze-code-maps"></a>Analyser les cartes de code

1. Dans la barre d’outils de carte, choisissez **Disposition**, **Analyseurs**, puis sélectionnez l’analyseur que vous souhaitez exécuter :

   |**Analyseur**|**Pour identifier les nœuds qui**|
   |------------------|--------------------------------|
   |**Analyseur de références circulaires**|Ont des dépendances circulaires les unes envers les autres. **Remarque :**  Les dépendances circulaires qui se trouvent dans le groupe **génériques** ne sont pas affichées sur la carte lorsque vous développez le groupe.|
   |**Rechercher l’analyseur de hubs**|Figurent dans les premiers 25 % des nœuds hautement connectés<br /><br /> **Pour masquer tous les autres nœuds de la carte**<br /><br /> -Ouvrez le menu contextuel de la carte, choisissez **avancé**, **Sélectionner**, **Masquer non sélectionné**.<br />     La carte masque les nœuds non sélectionnés et l’analyseur identifie les nouveaux nœuds en tant que hubs.|
   |**Analyseur de nœuds non référencés**|N’ont pas de références d’autres nœuds. **Attention :**  Vérifiez chacun de ces cas avant de supposer que le code n’est pas utilisé. Certaines dépendances, telles que les dépendances XAML et d’exécution, sont introuvables statiquement dans le code.|

   Les analyseurs de carte de code continuent de s’exécuter après leur application. Si vous modifiez la carte, les analyseurs appliqués retraitent automatiquement la carte mise à jour. Pour arrêter l’exécution d’un analyseur, dans la barre d’outils de la carte, sélectionnez **Disposition**, **Analyseurs**. Désactivez l’analyseur sélectionné.

> [!TIP]
> Si votre carte est très grande, l’exécution d’un analyseur peut provoquer une exception en raison de mémoire insuffisante. Si cela se produit, modifiez la carte pour réduire sa portée ou générez-en une plus petite, puis exécutez l’analyseur.

## <a name="see-also"></a>Voir aussi
 [Mapper les dépendances dans vos solutions](../modeling/map-dependencies-across-your-solutions.md) [utiliser des cartes de code pour déboguer vos applications](../modeling/use-code-maps-to-debug-your-applications.md) [mapper des méthodes sur la pile des appels pendant le débogage](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
