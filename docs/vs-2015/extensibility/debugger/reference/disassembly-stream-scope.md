---
title: DISASSEMBLY_STREAM_SCOPE | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- DISASSEMBLY_STREAM_SCOPE
helpviewer_keywords:
- DISASSEMBLY_STREAM_SCOPE enumeration
ms.assetid: 43e2b364-cbbe-4755-a7e6-a03f3054c965
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0132aad5ad6e37e7bb811693afde7ebfe80b272d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68198837"
---
# <a name="disassembly_stream_scope"></a>DISASSEMBLY_STREAM_SCOPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Spécifie la portée du flux de code machine.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
typedef DWORD DISASSEMBLY_STREAM_SCOPE;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
```  
  
## <a name="members"></a>Membres  
 DSS_HUGE  
 Spécifie que le désassemblage du contexte de code génère plus de sortie qu’un client souhaitant généralement récupérer dans un appel unique.  
  
 DSS_FUNCTION  
 Spécifie que la fonction contenue dans le contexte de code doit être désassemblée. Spécifie que le flux de code machine représente une fonction, quand elle est retournée par la méthode [GetScope,](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) .  
  
 DSS_MODULE  
 Quand elle est retournée par la `IDebugDisassemblyStream2::GetScope` méthode, spécifie que le flux de code machine représente un module.  
  
 DSS_ALL  
 Spécifie le code machine pour l’intégralité de l’espace d’adressage.  
  
## <a name="remarks"></a>Notes  
 Passé comme argument à la méthode [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) et retourné par la méthode [GetScope,](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) .  
  
 Ces valeurs peuvent être combinées avec une opération de bits `OR` .  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg. h  
  
 Espace de noms : Microsoft. VisualStudio. Debugger. Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)
