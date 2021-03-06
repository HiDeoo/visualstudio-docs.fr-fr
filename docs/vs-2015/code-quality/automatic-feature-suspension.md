---
title: Suspension automatique des fonctionnalités | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.topic: conceptual
helpviewer_keywords:
- full solution analysis
- performance
- low-memory
ms.assetid: 572c15aa-1fd0-468c-b6be-9fa50e170914
caps.latest.revision: 8
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 1dddc235131322a61cdb0106d866b138040d8c18
ms.sourcegitcommit: 5caad925ca0b5d136416144a279e984836d8f28c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2020
ms.locfileid: "89508195"
---
# <a name="automatic-feature-suspension"></a>Suspension automatique de fonctionnalités
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
Si la mémoire système disponible tombe à 200 Mo ou moins, Visual Studio affiche le message suivant dans l’éditeur de code.

 ![Texte d’alerte interruption de l’analyse complète de la solution](../code-quality/media/fsa-alert.png "FSA_Alert")

 Lorsque Visual Studio détecte une condition de mémoire insuffisante, il suspend automatiquement certaines fonctionnalités avancées pour l’aider à rester stable. Lorsque cet avertissement de suspension de fonctionnalité avancée s’affiche, Visual Studio continue de fonctionner comme avant, mais ses performances seront légèrement détériorées.

 Dans une condition de mémoire insuffisante, voici ce qui se produit :

- L’analyse complète de la solution pour Visual C# et Visual Basic est désactivée.

- Le mode de latence faible de [garbage collection](https://msdn.microsoft.com/library/22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9) (GC) pour Visual C# et Visual Basic sont désactivés.

- Les caches Visual Studio sont vidés.

## <a name="improve-visual-studio-performance"></a>Améliorer les performances de Visual Studio
 Pour obtenir des conseils et des astuces sur la façon d’améliorer les performances de Visual Studio quand vous travaillez avec des solutions volumineuses ou des conditions de mémoire insuffisante, consultez [Considérations sur les performances pour les grandes solutions](https://github.com/dotnet/roslyn/blob/master/docs/wiki/Performance-considerations-for-large-solutions.md).

## <a name="full-solution-analysis-suspended"></a>Analyse complète de la solution suspendue
 Par défaut, l’analyse complète de la solution est activée pour Visual Basic et désactivée pour Visual C#. Toutefois, dans une condition de mémoire insuffisante, l’analyse complète de la solution est automatiquement désactivée pour Visual Basic et Visual C#, quels que soient les paramètres de la boîte de dialogue Options. Toutefois, vous pouvez réactiver l’analyse complète de la solution en choisissant le bouton **réactiver** dans la barre d’informations quand elle apparaît, en activant la case à cocher **activer l’analyse complète** de la solution dans la boîte de dialogue Options ou en redémarrant Visual Studio. La boîte de dialogue Options affiche toujours les paramètres d’analyse complète de la solution en cours. Pour plus d’informations, consultez [Comment : activer et désactiver l’analyse complète de la solution](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md).

## <a name="gc-low-latency-disabled"></a>Faible latence GC désactivée
 Pour réactiver le mode de faible latence GC, redémarrez Visual Studio.  Par défaut, Visual Studio active le mode de faible latence GC chaque fois que vous tapez pour vous assurer que votre saisie ne bloque pas les opérations GC. Toutefois, si une condition de mémoire insuffisante entraîne l’affichage de l’avertissement de suspension automatique par Visual Studio, le mode de latence faible GC est désactivé pour cette session. Le redémarrage de Visual Studio réactivera le comportement de GC par défaut. Pour plus d'informations, consultez <xref:System.Runtime.GCLatencyMode>.

## <a name="visual-studio-caches-flushed"></a>Caches Visual Studio vidés

Tous les caches Visual Studio sont immédiatement vidés, mais ils commencent à être remplis si vous continuez votre session de développement actuelle ou si vous redémarrez Visual Studio. Les caches vidés incluent des caches pour les fonctionnalités suivantes.

- Rechercher toutes les références

- Naviguer vers

- Ajouter using

En outre, les caches utilisés pour les opérations internes de Visual Studio sont également effacés.

> [!NOTE]
> L’avertissement de suspension automatique des fonctionnalités ne se produit qu’une seule fois par solution, et non par session. Cela signifie que si vous passez de Visual Basic à Visual C# (ou vice versa) et que vous exécutez dans une autre condition de mémoire insuffisante, vous pouvez éventuellement recevoir un autre avertissement de suspension automatique de fonctionnalité.

## <a name="see-also"></a>Voir aussi

- [Guide pratique pour activer et désactiver l’analyse de solution complète](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)
- [Principes de base du Garbage Collection](https://msdn.microsoft.com/library/67c5a20d-1be1-4ea7-8a9a-92b0b08658d2)
- [Considérations sur les performances pour les grandes solutions](https://github.com/dotnet/roslyn/blob/master/docs/wiki/Performance-considerations-for-large-solutions.md)