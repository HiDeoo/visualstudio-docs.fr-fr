---
title: IDebugArrayField::GetRank | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6921da02b2df62509dd820795581e3ce6dae92d6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49846237"
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
Obtient le rang ou le nombre de dimensions du tableau.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pdwRank`  
 [out] Retourne le rang.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne S_OK ; Sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Le rang d’un tableau correspond au nombre de dimensions. Dans C++ et c#, les tableaux multidimensionnels sont vraiment les tableaux de tableaux et peut donc être considéré comme simplement un tableau unidimensionnel (et le `GetRank` méthode retourne toujours 1). Dans [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)], quant à eux, des tableaux multidimensionnels sont gérés différemment et le classement d’un tel tableau reflète le nombre de dimensions (et le `GetRank` méthode retourne toujours le nombre de dimensions).  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)