---
title: ADDRESS_KIND | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- ADDRESS_KIND
helpviewer_keywords:
- ADDRESS_KIND enumeration
ms.assetid: 3a12fbec-7088-4cf9-8f6f-ad8ddec6009a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ce0328e3ddae1f58717fd831f64c0131c3e6beba
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56317196"
---
# <a name="addresskind"></a>ADDRESS_KIND
Spécifie les types d’adresses.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_ADDRESS_KIND {
    ADDRESS_KIND_NATIVE                  = 0x0001,
    ADDRESS_KIND_UNMANAGED_THIS_RELATIVE = 0x0002,
    ADDRESS_KIND_UNMANAGED_PHYSICAL      = 0x0005,
    ADDRESS_KIND_METADATA_METHOD         = 0x0010,
    ADDRESS_KIND_METADATA_FIELD          = 0x0011,
    ADDRESS_KIND_METADATA_LOCAL          = 0x0012,
    ADDRESS_KIND_METADATA_PARAM          = 0x0013,
    ADDRESS_KIND_METADATA_ARRAYELEM      = 0x0014,
    ADDRESS_KIND_METADATA_RETVAL         = 0x0015,
};
typedef DWORD ADDRESS_KIND;
```

```csharp
public enum enum_ADDRESS_KIND {
    ADDRESS_KIND_NATIVE                  = 0x0001,
    ADDRESS_KIND_UNMANAGED_THIS_RELATIVE = 0x0002,
    ADDRESS_KIND_UNMANAGED_PHYSICAL      = 0x0005,
    ADDRESS_KIND_METADATA_METHOD         = 0x0010,
    ADDRESS_KIND_METADATA_FIELD          = 0x0011,
    ADDRESS_KIND_METADATA_LOCAL          = 0x0012,
    ADDRESS_KIND_METADATA_PARAM          = 0x0013,
    ADDRESS_KIND_METADATA_ARRAYELEM      = 0x0014,
    ADDRESS_KIND_METADATA_RETVAL         = 0x0015,
};
```

## <a name="terms"></a>Termes
ADDRESS_KIND_NATIVE  
Une adresse native, représentée par le [NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md) structure.

ADDRESS_KIND_UNMANAGED_THIS_RELATIVE  
Une adresse non managée relatif à un `this` (`Me` en Visual Basic) pointeur et représenté par le [UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md) structure.

ADDRESS_KIND_UNMANAGED_PHYSICAL  
Une adresse physique non managée, représentée par le [UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md) structure.

ADDRESS_KIND_METHOD  
Une méthode d’une classe, représentée par le [METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md) structure.

ADDRESS_KIND_FIELD  
Un champ d’une classe, représenté par le [METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md) structure.

ADDRESS_KIND_LOCAL  
L’adresse est d’une variable locale et est représenté par le [METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md) structure.

ADDRESS_KIND_PARAM  
Un paramètre de méthode ou fonction, représenté par le [METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md) structure.

ADDRESS_KIND_ARRAYELEM  
Un élément de tableau, représenté par le [METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md) structure.

ADDRESS_KIND_RETVAL  
Une valeur de retour, représentée par le [METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md) structure.

## <a name="remarks"></a>Notes
Le [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) méthode retourne le [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) structure qui contient une union de structures possible, le [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) structure. Le `dwKind` champ la `DEBUG_ADDRESS_UNION` structure contient la `ADDRESS_KIND` valeur et explique comment interpréter le champ union.

## <a name="requirements"></a>Spécifications
En-tête : sh.h

Espace de noms : Microsoft.VisualStudio.Debugger.Interop

Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
[Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)  
[DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)  
[DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)
