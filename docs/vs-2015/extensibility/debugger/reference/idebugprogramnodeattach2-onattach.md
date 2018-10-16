---
title: IDebugProgramNodeAttach2::OnAttach | Microsoft Docs
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
- IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords:
- IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
caps.latest.revision: 4
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 424bcc9299103139de292f405d4f162b35347425
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49171728"
---
# <a name="idebugprogramnodeattach2onattach"></a>IDebugProgramNodeAttach2::OnAttach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Est attaché au programme associé ou diffère le processus d’attachement à la [attacher](../../../extensibility/debugger/reference/idebugengine2-attach.md) (méthode).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT OnAttach(  
   [in] REFGUID guidProgramId  
);  
```  
  
```csharp  
int OnAttach(  
   ref Guid guidProgramId  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 `guidProgramId`  
 [in] `GUID` à affecter au programme associé.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`. Retourne `S_FALSE` si le [attacher](../../../extensibility/debugger/reference/idebugengine2-attach.md) méthode ne doit pas être appelée. Sinon, retourne un code d'erreur.  
  
## <a name="remarks"></a>Notes  
 Cette méthode est appelée pendant le processus d’attachement, avant le [attacher](../../../extensibility/debugger/reference/idebugengine2-attach.md) méthode est appelée. Le `OnAttach` méthode peut exécuter le processus d’attachement lui-même (dans ce cas, cette méthode retourne `S_FALSE`) ou différer le processus d’attachement à la `IDebugEngine2::Attach` (méthode) (le `OnAttach` retourne de la méthode `S_OK`). Dans les deux cas, le `OnAttach` méthode peut définir le `GUID` du programme en cours de débogage à la donnée `GUID`.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [Attacher](../../../extensibility/debugger/reference/idebugengine2-attach.md)

