---
title: 'IDebugProgramNodeAttach2 :: OnAttach | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords:
- IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: dfb8a39af3c030dadddcb148a79a96b57f20e183
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80721879"
---
# <a name="idebugprogramnodeattach2onattach"></a>IDebugProgramNodeAttach2::OnAttach
Joint au programme associé ou diffère le processus d’attachement à la méthode d' [attachement](../../../extensibility/debugger/reference/idebugengine2-attach.md) .

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT OnAttach(
   [in] REFGUID guidProgramId
);
```

```csharp
int OnAttach(
   ref Guid guidProgramId
};
```

## <a name="parameters"></a>Paramètres
`guidProgramId`\
[in] `GUID` à assigner au programme associé.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK`. Retourne `S_FALSE` si la méthode d' [attachement](../../../extensibility/debugger/reference/idebugengine2-attach.md) ne doit pas être appelée. Sinon, retourne un code d'erreur.

## <a name="remarks"></a>Notes
 Cette méthode est appelée pendant le processus d’attachement, avant l’appel de la méthode [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) . La `OnAttach` méthode peut exécuter le processus d’attachement lui-même (dans ce cas, cette méthode retourne `S_FALSE` ) ou différer le processus d’attachement à la `IDebugEngine2::Attach` méthode (la `OnAttach` méthode retourne `S_OK` ). Dans les deux cas, la `OnAttach` méthode peut définir le `GUID` du programme en cours de débogage dans le donné `GUID` .

## <a name="see-also"></a>Voir aussi
- [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)
- [Attacher](../../../extensibility/debugger/reference/idebugengine2-attach.md)
