---
title: Gestionnaire de débogage de session | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- session debug manager, unifying session views
- session debug manager, broadcasting
- debugging [Debugging SDK], session debug manager
- session debug manager
- session debug manager, debug engine multiplexing
- session debug manager, delegating
ms.assetid: fbb1928d-dddc-43d1-98a4-e23b0ecbae09
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9fd7c7555c19f850a15161f6fba00b1184621a9e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68157827"
---
# <a name="session-debug-manager"></a>Gestionnaire du débogage de session
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Le gestionnaire de débogage de session (SDM) gère un nombre quelconque de moteurs de débogage déboguant un nombre quelconque de programmes dans plusieurs processus sur un nombre quelconque d’ordinateurs. En plus d’être un multiplexeur de moteur de débogage, le SDM fournit une vue unifiée de la session de débogage à l’IDE.  
  
## <a name="session-debug-manager-operation"></a>Opération du gestionnaire de débogage de session  
 Le gestionnaire DE débogage DE session (SDM) gère le. Il peut y avoir plus d’un moteur de débogage en cours d’exécution sur un ordinateur en même temps. Pour multiplexer le DEs, le SDM encapsule un certain nombre d’interfaces du et les expose à l’IDE sous la forme d’une interface unique.  
  
 Pour améliorer les performances, certaines interfaces ne sont pas multiplexées. Au lieu de cela, ils sont utilisés directement à partir de la, et les appels à ces interfaces ne passent pas par le SDM. Par exemple, les interfaces utilisées avec la mémoire, le code et les contextes de document ne sont pas multiplexées, car elles font référence à une instruction, une mémoire ou un document spécifique dans un programme spécifique qui est débogué par un DE. Aucun autre DE ne doit être impliqué dans ce niveau de communication.  
  
 Ce n’est pas le cas de tous les contextes. Les appels à l’interface de contexte d’évaluation de l’expression passent par le SDM. Lors de l’évaluation de l’expression, le SDM encapsule l’interface [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) qu’il donne à l’IDE, car lorsque cette expression est évaluée, il peut impliquer plusieurs des programmes de débogage du même processus qui peuvent s’exécuter sur le même thread.  
  
 Le SDM agit généralement comme un mécanisme de délégation, mais il peut agir comme un mécanisme de diffusion. Par exemple, lors de l’évaluation de l’expression, le SDM agit comme un mécanisme de diffusion pour notifier à tous les qu’ils peuvent exécuter du code sur un thread spécifié. De même, lorsque le SDM reçoit un événement d’arrêt, il diffuse à tous les programmes qu’ils doivent arrêter d’être en cours d’exécution. Quand une étape est appelée, le SDM diffuse à tous les programmes qu’il peut continuer à exécuter. Les points d’arrêt sont également diffusés à chaque DE.  
  
 Le SDM n’effectue pas le suivi du programme, du thread ou du frame de pile en cours. Les informations de processus, de programme et de thread sont envoyées au SDM conjointement avec des événements de débogage spécifiques.  
  
## <a name="see-also"></a>Voir aussi  
 [Moteur de débogage](../../extensibility/debugger/debug-engine.md)   
 [Composants du débogueur](../../extensibility/debugger/debugger-components.md)   
 [Contextes du débogueur](../../extensibility/debugger/debugger-contexts.md)
