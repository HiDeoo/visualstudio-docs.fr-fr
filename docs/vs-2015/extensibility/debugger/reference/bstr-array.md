---
title: BSTR_ARRAY | Microsoft Docs
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
- BSTR_ARRAY
helpviewer_keywords:
- BSTR_ARRAY structure
ms.assetid: 48da37f7-a237-48a9-9ff9-389c1a00862c
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fac2e8c26af14c40bff90d26b02e33662fde6862
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47504295"
---
# <a name="bstrarray"></a>BSTR_ARRAY
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [BSTR_ARRAY](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bstr-array).  
  
Une structure qui décrit un tableau de chaînes.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
typedef struct tagBSTR_ARRAY {  
   DWORD dwCount;  
   BSTR* Members;  
} BSTR_ARRAY;  
```  
  
```csharp  
struct BSTR_ARRAY {  
   DWORD    dwCount;  
   string[] Members;  
}  
```  
  
## <a name="terms"></a>Termes  
 dwCount  
 Nombre de chaînes dans `Members` tableau.  
  
 Membres  
 Tableau de chaînes.  
  
## <a name="remarks"></a>Notes  
 Cette structure est retournée à partir de la [EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md) (méthode).  
  
 (C++ uniquement) Chaque chaîne individuelle doit être libérée à l’aide de `SysFreeString`et le `Members` tableau doit être libéré avec `CoTaskMemFree`.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Structures et Unions](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md)

