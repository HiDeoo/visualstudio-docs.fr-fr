---
title: IDebugProcess3::GetENCAvailableState | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProcess3::GetENCAvailableState
helpviewer_keywords:
- IDebugProcess3::GetENCAvailableState
ms.assetid: 98a5d527-8a72-476c-8e92-0bff3d97c195
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 17bf401b9992d156fdaba60ae46bffde6f8ce8cc
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58938451"
---
# <a name="idebugprocess3getencavailablestate"></a>IDebugProcess3::GetENCAvailableState
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette méthode obtient l’état actuel de modifier & Continuer du processus. Un fournisseur de port personnalisé doit toujours retourner `E_NOTIMPL`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetENCAvailableState(  
   EncUnavailableReason* pReason  
);  
```  
  
```csharp  
int GetENCAvailableState(  
   EncUnavailableReason[] pReason  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pReason`  
 [out] Une valeur comprise entre le [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md) énumération.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne le code d’erreur.  
  
> [!NOTE]
>  Un fournisseur de port personnalisé doit toujours retourner `E_NOTIMPL`.  
  
## <a name="remarks"></a>Notes  
 Cet état peut être affecté par [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)   
 [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)
