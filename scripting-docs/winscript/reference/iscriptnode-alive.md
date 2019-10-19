---
title: 'IScriptNode :: Alive | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.Alive
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::Alive
ms.assetid: d2755c83-e9b9-4c0a-acb7-25b554fc9fe8
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b7e0216824506ee942b42a42d5c3c4475f63f9e2
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573626"
---
# <a name="iscriptnodealive"></a>IScriptNode::Alive
Indique si un objet est toujours actif.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Alive();  
```  
  
#### <a name="parameters"></a>Paramètres  
 La méthode n’accepte aucun paramètre.  
  
## <a name="return-value"></a>Valeur de retour  
 Élément `HRESULT`. Les valeurs possibles sont notamment celles figurant dans le tableau suivant.  
  
|valeur|Description|  
|-----------|-----------------|  
|`S_OK`|Le nœud de script est toujours actif.|  
  
## <a name="remarks"></a>Notes  
 Si l’objet n’est pas actif, le modèle COM (Component Object Model) retourne une erreur du proxy de marshaling pour les appels à cette méthode.  
  
## <a name="see-also"></a>Voir aussi  
 [Interface IScriptNode](../../winscript/reference/iscriptnode-interface.md)