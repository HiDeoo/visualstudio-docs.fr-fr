---
title: IActiveScriptAuthor::AddNamedItem | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.AddNamedItem
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::AddNamedItem
ms.assetid: 951003b6-1c4a-4086-b7ce-2f128e007280
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 85c434ea17d41fb98300289c3161349f9d9f5a2f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094859"
---
# <a name="iactivescriptauthoraddnameditem"></a>IActiveScriptAuthor::AddNamedItem
Ajoute le nom d’un élément de niveau racine pour la création d’espace de noms du moteur de script. Un *élément de niveau racine* est un objet qui peut contenir des méthodes et propriétés, et qui peut également contenir une source d’événement.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT AddNamedItem(  
   LPCOLESTR          pszName,  
   DWORD              dwFlags,  
   IDispatch          *pdisp  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pszName`  
 [in] Le nom de l’élément tel qu’affiché à partir du script. Le nom doit être unique et persistante.  
  
 `dwFlags`  
 [in] Les indicateurs associés à l’élément nommé. Peut être une combinaison des valeurs suivantes :  
  
|Constante|Value|Description|  
|--------------|-----------|-----------------|  
|SCRIPTITEM_ISVISIBLE|0x00000002|Indique que le nom de l’élément est disponible dans l’espace de noms du script. Cela permet d’accéder aux propriétés, les méthodes et les événements de l’élément.<br /><br /> Par convention, les propriétés de l’élément incluent des membres enfants de l’élément. Par conséquent, toutes les propriétés de l’objet enfant et les méthodes (et leurs membres enfants, de manière récursive) sont accessibles.|  
|SCRIPTITEM_ISSOURCE|0x00000004|Indique les événements de la source de l’élément que le script peut avoir des gestionnaires d’événements de script.|  
|SCRIPTITEM_GLOBALMEMBERS|0x00000008|Indique que l’élément est une collection de propriétés globales et des méthodes qui sont associées au script. Ses membres sont créés en tant que les méthodes et variables globales.|  
|SCRIPTITEM_ISPERSISTENT|0x00000040|Indique que l’élément doit être enregistré si le moteur de création de script est enregistré.|  
|SCRIPTITEM_CODEONLY|0x00000200|Indique que l’élément nommé représente un objet de code uniquement, et il n’a pas un membre à créer.|  
|SCRIPTITEM_NOCODE|0x00000400|Indique que l’élément nommé est simplement un nom en cours d’ajout, et il n’a rien à créer.|  
  
 `pdisp`  
 [in] Le `IDispatch` de la `NamedItem` objet qui est utilisé pour collecter des méthodes, propriétés ou la source d’événements.  
  
## <a name="return-value"></a>Valeur de retour  
 Élément `HRESULT`. Les valeurs possibles sont notamment celles figurant dans le tableau suivant.  
  
|Value|Description|  
|-----------|-----------------|  
|`S_OK`|La méthode a réussi.|  
  
## <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [IActiveScriptAuthor (Interface)](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IActiveScriptAuthor::RemoveNamedItem](../../winscript/reference/iactivescriptauthor-removenameditem.md)