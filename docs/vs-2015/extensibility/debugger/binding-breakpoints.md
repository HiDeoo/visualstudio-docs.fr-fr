---
title: Liaison des points d’arrêt | Microsoft Docs
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
- breakpoints, binding
ms.assetid: 70737387-c52f-4dae-8865-77d4b203bf25
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f8061b8d9a9cf3f29889405ea8004a79a0af8216
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51807366"
---
# <a name="binding-breakpoints"></a>Liaison de points d’arrêt
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Si l’utilisateur définit un point d’arrêt, peut-être en appuyant sur F9, l’IDE formule la demande et vous invite à entrer la session de débogage pour créer le point d’arrêt.  
  
## <a name="setting-a-breakpoint"></a>Définition d'un point d'arrêt  
 Définir un point d’arrêt d’est un processus en deux étapes, car le code ou les données affectées par le point d’arrêt encore peut-être pas disponibles. Tout d’abord, le point d’arrêt doit être décrit, et ensuite, comme le code ou données devient disponibles, il doit être lié à ce code ou de données, comme suit :  
  
1.  Le point d’arrêt est demandé par les moteurs de débogage pertinentes (DEs), et ensuite le point d’arrêt est lié au code ou des données qu’il est disponible.  
  
2.  La demande de point d’arrêt est envoyée à la session de débogage, ce qui les envoie à tous les DEs pertinentes. N’importe quel DE qui choisit de gérer le point d’arrêt crée un correspondant en attente de point d’arrêt.  
  
3.  La session de débogage collecte les points d’arrêt en attente et les envoie vers le package de débogage (le composant de débogage de Visual Studio).  
  
4.  Le package de débogage vous invite à la session de débogage pour lier le point d’arrêt en attente à du code ou des données. La session de débogage envoie cette demande à tous les DEs pertinentes.  
  
5.  Si le D’est en mesure de lier le point d’arrêt, il envoie qu'un point d’arrêt lié un événement à la session de débogage. Si ce n’est pas le cas, il envoie un événement d’erreur de point d’arrêt à la place.  
  
## <a name="pending-breakpoints"></a>Points d’arrêt en attente  
 Un point d’arrêt en attente peut lier à plusieurs emplacements de code. Par exemple, une ligne de code source pour un modèle C++ peut lier à chaque séquence de code généré à partir du modèle. La session de débogage peut utiliser un événement lié du point d’arrêt pour énumérer les contextes de code liés à un point d’arrêt au moment de que l’événement a été envoyé. Plusieurs contextes de code peuvent être liés ultérieurement, donc le DE peut envoyer que plusieurs point d’arrêt lié des événements pour chaque demande de liaison. Toutefois, un DE doit envoyer uniquement un événement d’erreur de point d’arrêt par demande de liaison.  
  
## <a name="implementation"></a>Implémentation  
 Par programme, le package de débogage appelle le débogage de session manager (SDM) et lui donne un [IDebugBreakpointRequest2](../../extensibility/debugger/reference/idebugbreakpointrequest2.md) interface qui encapsule un [BP_REQUEST_INFO](../../extensibility/debugger/reference/bp-request-info.md) structure qui décrit le point d’arrêt à définir. Bien que les points d’arrêt peuvent être de différentes formes, elles sont finalement réduites à un contexte de code ou de données.  
  
 Le SDM passe cet appel pour chaque DE pertinentes en appelant son [CreatePendingBreakpoint](../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md) (méthode). Si le DE choisit de gérer le point d’arrêt, il crée et retourne un [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) interface. Le SDM collecte ces interfaces et les repasse à déboguer le package en tant qu’un seul `IDebugPendingBreakpoint2` interface.  
  
 Jusqu’ici, aucun événement n’a été généré.  
  
 Le package de débogage puis tente de lier le point d’arrêt en attente à du code ou des données en appelant [lier](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md), qui est implémentée par l’Allemagne.  
  
 Si le point d’arrêt est lié, l’Allemagne envoie un [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) interface d’événement pour le package de débogage. Les utilisations de package de débogage cette interface pour énumérer tous les contextes de code (ou le contexte de données unique) est liée au point d’arrêt en appelant [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md), qui retourne un ou plusieurs [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) interfaces. Le [GetBreakpointResolution](../../extensibility/debugger/reference/idebugboundbreakpoint2-getbreakpointresolution.md) interface retourne un [IDebugBreakpointResolution2](../../extensibility/debugger/reference/idebugbreakpointresolution2.md) interface, et [GetResolutionInfo](../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) retourne un [BP_ RESOLUTION_INFO](../../extensibility/debugger/reference/bp-resolution-info.md) union qui contient le contexte de code ou de données.  
  
 Si le D’est impossible de lier le point d’arrêt, il envoie un seul [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) interface d’événement pour le package de débogage. Le package de débogage récupère le type d’erreur (erreur ou avertissement) et le message d’information en appelant [GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md), suivie [GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) et [ GetResolutionInfo](../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md). Cette commande renvoie un [BP_ERROR_RESOLUTION_INFO](../../extensibility/debugger/reference/bp-error-resolution-info.md) structure qui contient le type d’erreur et le message.  
  
 Si un DE gère un point d’arrêt, mais ne peut pas lier, elle retourne une erreur de type `BPET_TYPE_ERROR`. Le package de débogage répond en affichant une boîte de dialogue d’erreur, et l’IDE place un glyphe de point d’exclamation à l’intérieur du glyphe de point d’arrêt à gauche de la ligne de code source.  
  
 Si un DE gère un point d’arrêt, ne peut pas lier, mais un autre dé peut lier, elle retourne un avertissement. L’IDE répond en plaçant un glyphe de question à l’intérieur du glyphe de point d’arrêt à gauche de la ligne de code source.  
  
## <a name="see-also"></a>Voir aussi  
 [Tâches de débogage](../../extensibility/debugger/debugging-tasks.md)

