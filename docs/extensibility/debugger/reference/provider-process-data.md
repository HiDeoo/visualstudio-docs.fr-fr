---
title: PROVIDER_PROCESS_DATA | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROVIDER_PROCESS_DATA
helpviewer_keywords:
- PROVIDER_PROCESS_DATA structure
ms.assetid: ec2362ed-4a0c-4a09-9d66-8ff04e4f41ee
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: bdaf15d09af3199d026155cf7667f063f5bbe858
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80713776"
---
# <a name="provider_process_data"></a>PROVIDER_PROCESS_DATA
Cette structure fournit des informations sur les processus qui s’exécutent sur un ordinateur.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct tagPROVIDER_PROCESS_DATA {
   PROVIDER_FIELDS    Fields;
   PROGRAM_NODE_ARRAY ProgramNodes;
   BOOL               fIsDebuggerPresent;
} PROVIDER_PROCESS_DATA;
```

```csharp
public struct PROVIDER_PROCESS_DATA {
   public uint               Fields;
   public PROGRAM_NODE_ARRAY ProgramNodes;
   public int                fIsDebuggerPresent;
}
```

## <a name="members"></a>Membres
 `Fields`\
 Combinaison d’indicateurs de l’énumération [PROVIDER_FIELDS](../../../extensibility/debugger/reference/provider-fields.md) , indiquant les champs qui sont remplis.

 `ProgramNodes`\
 Structure [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md) qui contient un tableau de nœuds de programme.

 `fIsDebuggerPresent`\
 Différent de zéro ( `TRUE` ) si le [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] débogueur est en cours d’exécution, zéro ( `FALSE` ) si ce n’est pas le cas.

## <a name="remarks"></a>Notes
 Cette structure est transmise à la méthode [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) où elle est remplie.

## <a name="requirements"></a>Configuration requise
 En-tête : msdbg. h

 Espace de noms : Microsoft. VisualStudio. Debugger. Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Structures et unions](../../../extensibility/debugger/reference/structures-and-unions.md)
- [PROVIDER_FIELDS](../../../extensibility/debugger/reference/provider-fields.md)
- [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md)
- [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)
