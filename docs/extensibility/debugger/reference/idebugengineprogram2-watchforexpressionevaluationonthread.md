---
title: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
titleSuffix: ''
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
helpviewer_keywords:
- IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
ms.assetid: 01d05e77-8cac-4d1b-b19f-25756767ed27
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4f36431ef7a190e98d35e795ffd8213781553dfc
ms.sourcegitcommit: 4ae5e9817ad13edd05425febb322b5be6d3c3425
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/11/2020
ms.locfileid: "90036117"
---
# <a name="idebugengineprogram2watchforexpressionevaluationonthread"></a>IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
Autorise (ou interdit) l’évaluation d’une expression sur le thread donné, même si le programme s’est arrêté.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT WatchForExpressionEvaluationOnThread( 
   IDebugProgram2*       pOriginatingProgram,
   DWORD                 dwTid,
   DWORD                 dwEvalFlags,
   IDebugEventCallback2* pExprCallback,
   BOOL                  fWatch
);
```

```csharp
int WatchForExpressionEvaluationOnThread( 
   IDebugProgram2       pOriginatingProgram,
   uint                  dwTid,
   uint                  dwEvalFlags,
   IDebugEventCallback2 pExprCallback,
   int                   fWatch
);
```

## <a name="parameters"></a>Paramètres
`pOriginatingProgram`\
dans Objet [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) qui représente le programme qui évalue une expression.

`dwTid`\
dans Spécifie l’identificateur du thread.

`dwEvalFlags`\
dans Combinaison d’indicateurs de l’énumération [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) qui spécifie le mode d’exécution de l’évaluation.

`pExprCallback`\
dans Objet [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) à utiliser pour envoyer les événements de débogage qui se produisent pendant l’évaluation de l’expression.

`fWatch`\
dans Si différent de zéro ( `TRUE` ), autorise l’évaluation de l’expression sur le thread identifié par `dwTid` ; sinon, zéro ( `FALSE` ) interdit l’évaluation de l’expression sur ce thread.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.

## <a name="remarks"></a>Remarques
 Quand le gestionnaire de débogage de session (SDM) demande à un programme, identifié par le `pOriginatingProgram` paramètre, d’évaluer une expression, il avertit tous les autres programmes attachés en appelant cette méthode.

 L’évaluation d’une expression dans un programme peut entraîner l’exécution du code dans un autre programme, en raison de l’évaluation de la fonction ou de l’évaluation de toutes les `IDispatch` Propriétés. Pour cette raison, cette méthode permet l’exécution et la finalisation de l’évaluation des expressions même si le thread peut être arrêté dans ce programme.

## <a name="see-also"></a>Voir aussi
- [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)
- [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
