---
title: Nœuds du programme | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- program nodes, debugging context
- debugging [Debugging SDK], program nodes
- program nodes, adding
- program nodes, superceding
ms.assetid: 1c5a5c13-c14d-42c3-af11-4c63f1032c8d
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3fa7e0969c9d45ae07280a8648036bd07c000974
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51774482"
---
# <a name="program-nodes"></a>Nœuds de programme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

En termes d’architecture du débogueur, une **nœud du programme**:  
  
- Est une description léger d’un programme.  
  
- Peut identifier lui-même et le processus est en cours d’exécution, elle peut être attaché pour être détaché et décrivent le moteur de débogage (dé) qui l’a créé, le cas échéant.  
  
- Est représenté par un [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) interface, généralement créée par un port ou DE. Nœuds de programme sont ajoutés à un port en appelant [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Lorsqu’un nœud de programme est ajouté à un port, il est ajouté au processus contenant le programme qui représente ce nœud de programme.  
  
  Un certain temps après le démarrage d’une session de débogage, selon l’implémentation du package de débogage, les nœuds de programme sont utilisés pour créer des programmes correspondants. Lorsqu’un processus est interrogé pour ses programmes, les programmes sont énumérées, une pour chaque nœud du programme.  
  
  Avant qu’un programme est associé à, l’IDE doit seulement une légère description du programme. Ces informations peuvent être obtenues à partir du nœud de programme. Une fois que le programme est attaché au, l’IDE doit afficher des informations plus détaillées, telles qu’une liste de tous les threads en cours d’exécution dans le programme. Ces informations sont obtenues à partir du programme lui-même.  
  
## <a name="see-also"></a>Voir aussi  
 [Programmes](../../extensibility/debugger/programs.md)   
 [Processus](../../extensibility/debugger/processes.md)   
 [Moteur de débogage](../../extensibility/debugger/debug-engine.md)   
 [Concepts du débogueur](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)

