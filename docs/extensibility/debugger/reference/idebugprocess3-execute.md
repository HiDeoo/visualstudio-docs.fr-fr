---
title: 'IDebugProcess3 :: Execute | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess3::Execute
helpviewer_keywords:
- IDebugProcess3::Execute
ms.assetid: d831cd81-d7bf-4172-8517-aa699867791f
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: baa607e62732cdf0e04413e07966658bb6a0b8f4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "86386509"
---
# <a name="idebugprocess3execute"></a>IDebugProcess3::Execute
Poursuit l’exécution de ce processus à partir d’un état arrêté. Tout état d’exécution précédent (par exemple, une étape) est effacé et le processus recommence à s’exécuter.

> [!NOTE]
> Cette méthode doit être utilisée à la place de [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md).

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Execute(
   IDebugThread2* pThread
);
```

```csharp
int Execute(
   IDebugThread2 pThread
);
```

## <a name="parameters"></a>Paramètres
`pThread`\
dans Objet [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) qui représente le thread à exécuter.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` ; sinon, retourne le code d’erreur.

## <a name="remarks"></a>Notes
 Lorsque l’utilisateur commence l’exécution à partir d’un état arrêté dans le thread d’un autre processus, cette méthode est appelée sur ce processus. Cette méthode est également appelée lorsque l’utilisateur sélectionne la commande **Démarrer** dans le menu **Déboguer** de l’IDE. L’implémentation de cette méthode peut être aussi simple que l’appel de la méthode [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md) sur le thread actuel dans le processus.

> [!WARNING]
> N’envoyez pas d’événement d’arrêt ou d’événement immédiat (synchrone) à un [événement](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) lors de la gestion de cet appel ; dans le cas contraire, le débogueur peut cesser de répondre.

## <a name="see-also"></a>Voir aussi
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [Reprendre](../../../extensibility/debugger/reference/idebugthread2-resume.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
