---
title: IDispError::GetSource | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetSource
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetSource
ms.assetid: 20def54c-a67c-4102-babf-6f0704e5fc5c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 629ecb8427539069bb9e235e733140331875288c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091817"
---
# <a name="idisperrorgetsource"></a>IDispError::GetSource
Retourne le ProgID dépendants de la langue pour la classe ou d’une application qui a généré l’erreur.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetSource(  
   BSTR*  pbstrSource  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pbstrSource`  
 [out] Chaîne qui contient un identificateur programmatique, sous la forme `progname.objectname`.  
  
## <a name="return-value"></a>Valeur de retour  
 La méthode retourne `HRESULT`. Les valeurs possibles sont notamment celles figurant dans le tableau suivant.  
  
|Value|Description|  
|-----------|-----------------|  
|`S_OK`|La méthode a réussi.|  
  
## <a name="remarks"></a>Notes  
 Cette méthode est utilisée pour déterminer la classe ou une application où l’exception s’est produite. L’identificateur programmatique peut-être être retournée dans la langue spécifiée par l’identificateur de paramètres régionaux (LCID) fourni au moment de l’appel.  
  
> [!NOTE]
>  Cette méthode n’est pas implémentée.  
  
## <a name="see-also"></a>Voir aussi  
 [Interface IDispError](../../winscript/reference/idisperror-interface.md)