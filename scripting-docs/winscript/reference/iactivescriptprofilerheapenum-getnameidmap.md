---
title: IActiveScriptProfilerHeapEnum::GetNameIdMap | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 88514c93-850b-48d4-9a68-1e27d7411f0d
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cdff1983524b9234d536a23378d300a0b815522d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092636"
---
# <a name="iactivescriptprofilerheapenumgetnameidmap"></a>IActiveScriptProfilerHeapEnum::GetNameIdMap
Retourne les noms de chaîne correspondant à [profiler_heap_object_name_id, Type](../../winscript/reference/profiler-heap-object-name-id-type.md) valeurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetNameIdMap (    [out, size_is(,*pcelt)] LPCWSTR* pNameList[],     [out] UINT *pcelt);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pNameList`  
 [out] Un tableau de noms associés [profiler_heap_object_name_id, Type](../../winscript/reference/profiler-heap-object-name-id-type.md) valeurs.  
  
 `pcelt`  
 [out] Le nombre de noms dans le tableau.  
  
## <a name="return-value"></a>Valeur de retour  
 La valeur HRESULT.