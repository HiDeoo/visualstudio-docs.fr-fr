---
title: Énumérateur de code de commande | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- command code enumerator
- source control plug-ins, command code enumeration
ms.assetid: 5d2c360c-59e4-4da8-bcb4-dd07c7441e40
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 15916d26ac0120417205af0bb9117a45ec0397c6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80739788"
---
# <a name="command-code-enumerator"></a>Énumérateur de code de commande
Cet énumérateur est utilisé dans les options pour [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) et [SccPopulateList](../extensibility/sccpopulatelist-function.md)pour indiquer la commande pour laquelle les options sont spécifiées.

## <a name="syntax"></a>Syntaxe

```
enum SCCCOMMAND {
   SCC_COMMAND_GET,
   SCC_COMMAND_CHECKOUT,
   SCC_COMMAND_CHECKIN,
   SCC_COMMAND_UNCHECKOUT,
   SCC_COMMAND_ADD,
   SCC_COMMAND_REMOVE,
   SCC_COMMAND_DIFF,
   SCC_COMMAND_HISTORY,
   SCC_COMMAND_RENAME,
   SCC_COMMAND_PROPERTIES,
   SCC_COMMAND_OPTIONS
};
```

## <a name="members"></a>Membres
SCC_COMMAND_GET correspond à [SccGet](../extensibility/sccget-function.md).

SCC_COMMAND_CHECKOUT correspond à [SccCheckout](../extensibility/scccheckout-function.md).

SCC_COMMAND_CHECKIN correspond à [SccCheckin](../extensibility/scccheckin-function.md).

SCC_COMMAND_UNCHECKOUT correspond à [SccUncheckout](../extensibility/sccuncheckout-function.md).

SCC_COMMAND_ADD correspond à [SccAdd](../extensibility/sccadd-function.md).

SCC_COMMAND_REMOVE correspond à [SccRemove](../extensibility/sccremove-function.md).

SCC_COMMAND_DIFF correspond à [SccDiff](../extensibility/sccdiff-function.md).

SCC_COMMAND_HISTORY correspond à [SccHistory](../extensibility/scchistory-function.md).

SCC_COMMAND_RENAME correspond à [SccRename](../extensibility/sccrename-function.md).

SCC_COMMAND_PROPERTIES correspond à [SccProperties](../extensibility/sccproperties-function.md).

SCC_COMMAND_OPTIONS correspond à [SccSetOption](../extensibility/sccsetoption-function.md).

## <a name="see-also"></a>Voir aussi
- [Plug-ins de contrôle de code source](../extensibility/source-control-plug-ins.md)
- [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)
- [SccPopulateList](../extensibility/sccpopulatelist-function.md)
