---
title: 'IDebugSessionProvider :: StartDebugSession | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugSessionProvider.StartDebugSession
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugSessionProvider::StartDebugSession
ms.assetid: 47697dfb-d4e1-492c-a14f-753e28195a76
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0fc4bdade94401d5fc7b5756eb61fddd166fe49b
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574908"
---
# <a name="idebugsessionproviderstartdebugsession"></a>IDebugSessionProvider::StartDebugSession
Lance une session de débogage avec l’application spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT StartDebugSession(  
   IRemoteDebugApplication*  pda  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pda`  
 dans Spécifie l’application de débogage.  
  
## <a name="return-value"></a>Valeur de retour  
 La méthode retourne `HRESULT`. Les valeurs possibles sont notamment celles figurant dans le tableau suivant.  
  
|valeur|Description|  
|-----------|-----------------|  
|`S_OK`|La méthode a réussi.|  
  
## <a name="remarks"></a>Notes  
 Cette méthode lance une session de débogage avec l’application spécifiée. Le débogueur doit appeler `IRemoteDebugApplication::ConnectDebugger` avant de retourner à partir de cet appel.  
  
## <a name="see-also"></a>Voir aussi  
 @No__t_1 de l' [interface IDebugSessionProvider](../../winscript/reference/idebugsessionprovider-interface.md)  
 [IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md)