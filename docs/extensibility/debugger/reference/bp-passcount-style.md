---
title: BP_PASSCOUNT_STYLE Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_PASSCOUNT_STYLE
helpviewer_keywords:
- BP_PASSCOUNT_STYLE structure
ms.assetid: 0a647047-e2d5-4724-a0b8-68108425ecad
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1633c5e9aa6ff251fedce83a0243664cd9e0e0a7
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80737915"
---
# <a name="bp_passcount_style"></a>BP_PASSCOUNT_STYLE
Spécifie l’état associé au nombre de laissez-passer de point d’arrêt qui provoque l’incendie du point d’arrêt.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_BP_PASSCOUNT_STYLE {
    BP_PASSCOUNT_NONE             = 0x0000,
    BP_PASSCOUNT_EQUAL            = 0x0001,
    BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,
    BP_PASSCOUNT_MOD              = 0x0003
};
typedef DWORD BP_PASSCOUNT_STYLE;
```

```csharp
public enum enum_BP_PASSCOUNT_STYLE {
    BP_PASSCOUNT_NONE             = 0x0000,
    BP_PASSCOUNT_EQUAL            = 0x0001,
    BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,
    BP_PASSCOUNT_MOD              = 0x0003
};
```

## <a name="fields"></a>Champs
`BP_PASSCOUNT_NONE`\
Spécifie aucun style de compte de point de passage.

`BP_PASSCOUNT_EQUAL`\
Définit le style de compte de passage de point d’arrêt à égal. Le point d’arrêt s’allume lorsque le nombre de fois que le point d’arrêt est atteint équivaut au nombre de passes.

`BP_PASSCOUNT_EQUAL_OR_GREATER`\
Définit le style de compte de passage de point d’arrêt à égal ou plus grand. Le point d’arrêt s’allume lorsque le nombre de fois que le point d’arrêt est atteint est égal ou supérieur au nombre de passes.

`BP_PASSCOUNT_MOD`\
Spécifie un nombre de passes modulo. Par exemple, si le nombre de `BP_PASSCOUNT_MOD` laissez-passer est du type et que la valeur de nombre de laissez-passer est de 4, le point de rupture s’allume chaque fois que le nombre de coups est un multiple de 4.

## <a name="remarks"></a>Notes
Utilisé pour `stylePassCount` le membre de la structure [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) qui est à son tour un membre des structures [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) et [BP_REQUEST_INFO2.](../../../extensibility/debugger/reference/bp-request-info2.md)

## <a name="requirements"></a>Spécifications
En-tête: msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assemblage: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)
- [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
