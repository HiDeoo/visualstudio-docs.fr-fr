---
title: IDebugCodeContext3 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e3f81168d9af7fbbb93b5c59f3ab19a17107b56b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80734189"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
Étend l’interface [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) pour permettre la récupération d’interfaces de module et de processus.

## <a name="syntax"></a>Syntaxe

```
IDebugCodeContext3 : IDebugCodeContext2
```

## <a name="notes-for-implementers"></a>Notes pour les implémenteurs
 Implémenté par les moteurs de débogage et consommé par le [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] package de débogage.

## <a name="methods"></a>Méthodes
 Outre les méthodes sur l' `IDebugCodeContext2` interface, cette interface implémente les méthodes suivantes :

|Méthode|Description|
|------------|-----------------|
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|Récupère une référence à l’interface du module de débogage.|
|[GetProcess,](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|Récupère une référence à l’interface du processus de débogage.|

## <a name="remarks"></a>Notes
 Il s’agit d’une interface facultative qui n’a généralement pas besoin d’être implémentée.

## <a name="requirements"></a>Configuration requise
 En-tête : msdbg. h

 Espace de noms : Microsoft. VisualStudio. Debugger. Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll
