---
title: DEBUG_ADDRESS_UNION | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DEBUG_ADDRESS_UNION
helpviewer_keywords:
- DEBUG_ADDRESS_UNION union
ms.assetid: e3d11aab-de0d-4109-b5dc-11e07e64382d
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3d33c7b81f077fe95294ead2a89a607a4b9e1a11
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47494379"
---
# <a name="debugaddressunion"></a>DEBUG_ADDRESS_UNION
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [DEBUG_ADDRESS_UNION](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/debug-address-union).  
  
Décrit les différents types d’adresses.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _tagDEBUG_ADDRESS_UNION {  
   ADDRESS_KIND dwKind;  
   union {  
      NATIVE_ADDRESS                  addrNative;  
      UNMANAGED_ADDRESS_THIS_RELATIVE addrThisRel;  
      UNMANAGED_ADDRESS_PHYSICAL      addrUPhysical;  
      METADATA_ADDRESS_METHOD         addrMethod;  
      METADATA_ADDRESS_FIELD          addrField;  
      METADATA_ADDRESS_LOCAL          addrLocal;  
      METADATA_ADDRESS_PARAM          addrParam;  
      METADATA_ADDRESS_ARRAYELEM      addrArrayElem;  
      METADATA_ADDRESS_RETVAL         addrRetVal;  
      DWORD                           unused;  
   } addr;  
} DEBUG_ADDRESS_UNION;  
```  
  
```csharp  
public struct DEBUG_ADDRESS_UNION {  
   public ADDRESS_KIND dwKind;  
   public IntPtr       unionmember;  
}  
```  
  
## <a name="terms"></a>Termes  
 dwKind  
 Une valeur comprise entre le [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) énumération qui spécifie comment interpréter l’union.  
  
 addr.addrNative  
 (C++ uniquement) Contient le [NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md) structure si `dwKind` = ADDRESS_KIND_NATIVE.  
  
 addr.addrThisRel  
 (C++ uniquement) Contient le[UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md) structure si `dwKind` = ADDRESS_KIND_UNMANAGED_THIS_RELATIVE.  
  
 addr.addUPhysical  
 (C++ uniquement) Contient le[UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md) structure si `dwKind` = ADDRESS_KIND_UNMANAGED_PHYSICAL.  
  
 addr.addrMethod  
 (C++ uniquement) Contient le[METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md) structure si `dwKind` = ADDRESS_KIND_METHOD.  
  
 addr.addrField  
 (C++ uniquement) Contient le[METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md) structure si `dwKind` = ADDRESS_KIND_FIELD.  
  
 addr.addrLocal  
 (C++ uniquement) Contient le[METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md) structure si `dwKind` = ADDRESS_KIND_LOCAL.  
  
 addr.addrParam  
 (C++ uniquement) Contient le[METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md) structure si `dwKind` = ADDRESS_KIND_PARAM.  
  
 addr.addrArrayElem  
 (C++ uniquement) Contient le[METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md) structure si `dwKind` = ADDRESS_KIND_ARRAYELEM.  
  
 addr.addrRetVal  
 (C++ uniquement) Contient le[METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md) structure si `dwKind` = ADDRESS_KIND_RETVAL.  
  
 addr.Unused  
 Marge intérieure (C++ uniquement).  
  
 Addr  
 (C++ uniquement) Le nom de l’union.  
  
 unionmember  
 (C# uniquement) Cette valeur doit être marshalé vers le type de structure appropriée selon `dwKind`. Consultez la section Notes pour l’association entre `dwKind` et l’interprétation de l’union.  
  
## <a name="remarks"></a>Notes  
 Cette structure fait partie de la [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) structurer et représente un d’un nombre de différents types d’adresses (la `DEBUG_ADDRESS` structure est remplie par un appel à la [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) méthode).  
  
 (C# uniquement) Le tableau suivant indique comment interpréter le `unionmember` membre pour chaque type d’adresse. L’exemple montre comment procéder pour un type d’adresse.  
  
|`dwKind`|`unionmember` interprété en tant que|  
|--------------|----------------------------------|  
|`ADDRESS_KIND_NATIVE`|[NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md)|  
|`ADDRESS_KIND_UNMANAGED_THIS_RELATIVE`|[UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md)|  
|`ADDRESS_KIND_UNMANAGED_PHYSICAL`|[UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md)|  
|`ADDRESS_KIND_METHOD`|[METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md)|  
|`ADDRESS_KIND_FIELD`|[METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md)|  
|`ADDRESS_KIND_LOCAL`|[METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md)|  
|`ADDRESS_KIND_PARAM`|[METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md)|  
|`ADDRESS_KIND_ARRAYELEM`|[METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md)|  
|`ADDRESS_KIND_RETVAL`|[METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md)|  
  
## <a name="example"></a>Exemple  
 Cet exemple montre comment interpréter un type d’adresse (`METADATA_ADDRESS_ARRAYELEM`) de la `DEBUG_ADDRESS_UNION` structure en c#. Les éléments restants peuvent être interprétées de la même façon.  
  
```csharp  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(DEBUG_ADDRESS_UNION dau)  
        {  
            if (dau.dwKind == (uint)enum_ADDRESS_KIND.ADDRESS_KIND_METADATA_ARRAYELEM)  
            {  
                 METADATA_ADDRESS_ARRAYELEM arrayElem =  
                     (METADATA_ADDRESS_ARRAYELEM)Marshal.PtrToStructure(dau.unionmember,  
                                 typeof(METADATA_ADDRESS_ARRAYELEM));  
            }  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : sh.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Structures et Unions](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)

