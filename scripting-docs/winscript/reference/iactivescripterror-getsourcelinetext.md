---
title: IActiveScriptError::GetSourceLineText | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptError.GetSourceLineText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptError_GetSourceLineText
ms.assetid: 64f7f37f-7288-4dbe-b626-a35d90897f36
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 702f1655b244116e1bb7dca3d5fc90de3d1f5bdf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955004"
---
# <a name="iactivescripterrorgetsourcelinetext"></a>IActiveScriptError::GetSourceLineText
Récupère la ligne dans le fichier source où une erreur s’est produite pendant l’exécution d’un moteur de script un script.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetSourceLineText(  
    BSTR *pbstrSourceLine  // address of buffer for source line  
);  
```  
  
## <a name="parameter"></a>Paramètre  
 `pbstrSourceLine`  
 [out] Adresse d’une mémoire tampon qui reçoit la ligne de code source dans lequel l’erreur s’est produite.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` en cas de réussite, ou `E_FAIL` si la ligne dans le fichier source n’a pas été récupérée.  
  
## <a name="see-also"></a>Voir aussi  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)