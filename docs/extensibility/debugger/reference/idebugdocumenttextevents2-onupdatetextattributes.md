---
title: IDebugDocumentTextEvents2::onUpdateTextAttributes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocumentTextEvents2::OnUpdateTextAttributes
helpviewer_keywords:
- IDebugDocumentTextEvents2::onUpdateTextAttributes
ms.assetid: eb68d69a-1ad9-4ce4-84e1-40979ef16634
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 21ceb40f54c4af0285576545efb0d228e65af493
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49876072"
---
# <a name="idebugdocumenttextevents2onupdatetextattributes"></a>IDebugDocumentTextEvents2::onUpdateTextAttributes
Informe le package de débogage que les attributs de texte ont été mis à jour dans le document.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT onUpdateTextAttributes(   
   TEXT_POSITION pos,  
   DWORD         dwNumToUpdate  
);  
```  
  
```csharp  
int onUpdateTextAttributes(   
   enum_TEXT_POSITION pos,  
   uint               dwNumToUpdate  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pos`  
 [in] Un [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) structure qui indique où les attributs de texte ont été mis à jour.  
  
 `dwNumToUpdate`  
 [in] Spécifie le nombre de caractères de texte qui ont été mis à jour.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)