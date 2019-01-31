---
title: Écriture de fonctions de raccordement de débogage | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vc.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], CRT debug support
- debug hook functions
- hooks, debug
- hooks
- debugging [CRT], debug hook functions
ms.assetid: 5510635f-cf69-4907-b72d-ae27af1f19af
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1ff144a30646ec29c022ba8e55c950e086179337
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54941951"
---
# <a name="debug-hook-function-writing"></a>Écriture de fonctions de raccordement de débogage
Cette section décrit plusieurs fonctions de raccordement de débogage personnalisées que vous pouvez écrire pour vous permettre d'insérer votre code dans quelques points prédéfinis du traitement normal du débogueur.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Fonctions de raccordement de bloc client](../debugger/client-block-hook-functions.md)  
 Fournit des conseils et un prototype pour l'écriture de fonctions qui valident ou reportent le contenu des données stockées dans les blocs _CLIENT_BLOCK.  
  
 [Fonctions de raccordement d’allocation](../debugger/allocation-hook-functions.md)  
 Définit une fonction de raccordement d'allocation, étudie ses différentes utilisations, souligne les restrictions et fournit un prototype.  
  
 [Raccordements d’allocation et allocations de la mémoire CRT](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)  
 Décrit la restriction des fonctions de raccordement d'allocation qui doivent ignorer de façon explicite les blocs `_CRT_BLOCK` si elles passent des appels aux fonctions de la bibliothèque Runtime C qui allouent la mémoire interne. Cette rubrique répertorie également les conséquences si votre raccordement d’allocation n’ignore pas les blocs `_CRT_BLOCK` (avec exemples) et la façon de modifier la fonction de raccordement d’allocation par défaut, **CrtDefaultAllocHook**.  
  
 [Fonctions de raccordement de rapport](../debugger/report-hook-functions.md)  
 Décrit `_CrtSetReportHook`, que vous pouvez utiliser pour filtrer les rapports de façon à vous concentrer sur des types d'allocations spécifiques. Cette rubrique fournit également un prototype.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Techniques de débogage CRT](../debugger/crt-debugging-techniques.md)  
 Renvoie à des techniques de débogage pour la bibliothèque Runtime C, parmi lesquelles l'utilisation de la bibliothèque de débogage CRT, les macros pour la création de rapports, les différences entre `malloc` et `_malloc_dbg`, l'écriture de fonctions de raccordement de débogage et le tas de débogage CRT.