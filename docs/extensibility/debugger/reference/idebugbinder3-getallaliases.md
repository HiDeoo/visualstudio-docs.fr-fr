---
title: IDebugBinder3::GetAllAliases | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugBinder3::GetAllAliases
helpviewer_keywords:
- IDebugBinder3::GetAllAliases method
ms.assetid: 1f9ab2ee-2ab3-4a61-8b99-95dd7fdf3511
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 75c8a916d6b69dbe4c7947e82093595a60cabbfc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49859991"
---
# <a name="idebugbinder3getallaliases"></a>IDebugBinder3::GetAllAliases
Cette méthode récupère une liste d’alias à partir du programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetAllAliases(  
   UINT          uRequest,  
   IDebugAlias** ppAliases,  
   UINT*         puFetched  
);  
```  
  
```csharp  
int GetAllAliases(  
   uint          uRequest,   
   IDebugAlias[] ppAliases,   
   out uint      puFetched  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `uRequest`  
 [in] Le nombre maximal d’alias à retourner (spécifie la longueur du tableau passé dans `ppAliases`).  
  
 `ppAliases`  
 [in, out] Tableau à remplir avec des alias (s’il s’agit d’une valeur null et `uRequest` est 0, le nombre d’alias qui peuvent être retournées est renvoyé par `puFetched`).  
  
 `puFetched`  
 [out] Retourne le nombre d’alias obtenu.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)