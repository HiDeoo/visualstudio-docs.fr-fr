---
title: GETHOSTNAME_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- GETHOSTNAME_TYPE
helpviewer_keywords:
- GETHOSTNAME_TYPE enumeration
ms.assetid: 2be92bea-8133-412b-9015-1833baf16e1b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f158cdaba17c030ce830c8adf26b6985c9b86dad
ms.sourcegitcommit: 7153e2fc717d32e0e9c8a9b8c406dc4053c9fd53
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2019
ms.locfileid: "56413434"
---
# <a name="gethostnametype"></a>GETHOSTNAME_TYPE
Spécifie le type du nom d’hôte.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_GETHOSTNAME_TYPE {
    GHN_FRIENDLY_NAME = 0,
    GHN_FILE_NAME     = 1
};
typedef DWORD GETHOSTNAME_TYPE;
```

```csharp
public enum enum_GETHOSTNAME_TYPE {
    GHN_FRIENDLY_NAME = 0,
    GHN_FILE_NAME     = 1
};
```

## <a name="members"></a>Membres
GHN_FRIENDLY_NAME  
Spécifie un nom convivial de l’hôte.

GHN_FILE_NAME  
Spécifie un nom de fichier de l’hôte.

## <a name="remarks"></a>Notes
Ces valeurs sont passées en tant qu’argument à la [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) méthode pour récupérer un nom d’hôte dans différents formats.

## <a name="requirements"></a>Spécifications
En-tête : msdbg.h

Espace de noms : Microsoft.VisualStudio.Debugger.Interop

Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
[Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)
