---
title: FRAMEINFO | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- FRAMEINFO
helpviewer_keywords:
- FRAMEINFO structure
ms.assetid: 95001b89-dddb-45bb-889d-8327994e38a5
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 07bb205649b286f3e9ed98d0d0f59c217bf0b96f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51797134"
---
# <a name="frameinfo"></a>FRAMEINFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Décrit un frame de pile.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
typedef struct tagFRAMEINFO {   
   FRAMEINFO_FLAGS    m_dwValidFields;  
   BSTR               m_bstrFuncName;  
   BSTR               m_bstrReturnType;  
   BSTR               m_bstrArgs;  
   BSTR               m_bstrLanguage;  
   BSTR               m_bstrModule;  
   UINT64             m_addrMin;  
   UINT64             m_addrMax;  
   IDebugStackFrame2* m_pFrame;  
   IDebugModule2*     m_pModule;  
   BOOL               m_fHasDebugInfo;  
   BOOL               m_fStaleCode;  
   BOOL               m_fAnnotatedFrame;  
} FRAMEINFO;  
```  
  
```csharp  
public struct FRAMEINFO {   
   public uint              m_dwValidFields;  
   public string            m_bstrFuncName;  
   public string            m_bstrReturnType;  
   public string            m_bstrArgs;  
   public string            m_bstrLanguage;  
   public string            m_bstrModule;  
   public ulong             m_addrMin;  
   public ulong             m_addrMax;  
   public IDebugStackFrame2 m_pFrame;  
   public IDebugModule2     m_pModule;  
   public int               m_fHasDebugInfo;  
   public int               m_fStaleCode;  
   public int               m_fAnnotatedFrame;  
} FRAMEINFO;  
```  
  
## <a name="members"></a>Membres  
 m_dwValidFields  
 Une combinaison d’indicateurs de la [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) énumération qui spécifie quels champs sont renseignés.  
  
 m_bstrFuncName  
 Le nom de fonction associé au frame de pile.  
  
 m_bstrReturnType  
 Le type de retour associé au frame de pile.  
  
 m_bstrArgs  
 Arguments à la fonction associée le frame de pile.  
  
 m_bstrLanguage  
 Le langage dans lequel la fonction est implémentée.  
  
 m_bstrModule  
 Le nom du module associé au frame de pile.  
  
 m_addrMin  
 L’adresse physique minimale de la pile.  
  
 m_addrMAX  
 L’adresse de la pile physique maximale.  
  
 m_pFrame  
 Le [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) objet qui représente ce frame de pile.  
  
 m_pFrame  
 Le [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) objet qui représente le module qui contient ce frame de pile.  
  
 m_fHasDebugInfo  
 Valeur différente de zéro (`TRUE`) si les informations de débogage existent dans le frame donné.  
  
 m_fHasDebugInfo  
 Valeur différente de zéro (`TRUE`) si le frame de pile est associé au code qui n’est plus valide.  
  
 m_fHasDebugInfo  
 Valeur différente de zéro (`TRUE`) si le frame de pile est annoté par le Gestionnaire de session de débogage (SDM).  
  
## <a name="remarks"></a>Notes  
 Cette structure est passée à la [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) méthode doit être renseigné. Cette structure est également contenue dans une liste qui est contenue dans le [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) interface qui, à son tour, est retourné à partir d’un appel à la [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) (méthode).  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Structures et Unions](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)   
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)

