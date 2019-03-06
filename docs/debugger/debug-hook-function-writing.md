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
ms.openlocfilehash: 82145d39adc519bfd1324cc36805cea7b97b1664
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56628921"
---
# <a name="debug-hook-function-writing"></a>Écriture de fonctions de raccordement de débogage
Cette section décrit plusieurs fonctions de raccordement de débogage personnalisées que vous pouvez écrire pour vous permettre d'insérer votre code dans quelques points prédéfinis du traitement normal du débogueur.

## <a name="in-this-section"></a>Dans cette section
 [Fonctions de raccordement de bloc client](../debugger/client-block-hook-functions.md) fournit des conseils et un prototype pour l’écriture de fonctions qui valident ou reportent le contenu des données stockées dans les blocs _CLIENT_BLOCK.

 [Fonctions de raccordement d’allocation](../debugger/allocation-hook-functions.md) définit une fonction de raccordement d’allocation, étudie ses différentes utilisations, souligne les restrictions et fournit un prototype.

 [Raccordements d’allocation et Allocations de mémoire CRT](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md) décrit la restriction des fonctions de raccordement d’allocation d’ignorer de façon explicite `_CRT_BLOCK` bloque si elles passent des appels aux fonctions de bibliothèque Runtime C qui allouent la mémoire interne. Cette rubrique répertorie également les conséquences si votre raccordement d’allocation n’ignore pas les blocs `_CRT_BLOCK` (avec exemples) et la façon de modifier la fonction de raccordement d’allocation par défaut, **CrtDefaultAllocHook**.

 [Fonctions de raccordement de rapport](../debugger/report-hook-functions.md) présente `_CrtSetReportHook`, que vous pouvez utiliser pour filtrer des rapports pour vous concentrer sur les types d’allocations spécifiques. Cette rubrique fournit également un prototype.

## <a name="related-sections"></a>Rubriques connexes

- [Techniques de débogage CRT](../debugger/crt-debugging-techniques.md) -des liens vers des techniques de débogage pour la bibliothèque Runtime C, y compris à l’aide de la bibliothèque de débogage CRT, les macros pour la création de rapports, les différences entre `malloc` et `_malloc_dbg`, écriture de fonctions de raccordement de débogage et la bibliothèque CRT tas de débogage.