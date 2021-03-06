---
title: IDebugCoreServer3 ::D iagnoseWebDebuggingError | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
helpviewer_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
ms.assetid: 8c4570ca-ae55-42f2-bbaa-8d8e75d2fa19
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 24f142a631df25cfbff8ed795736c0cbf4e59eaf
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68205275"
---
# <a name="idebugcoreserver3diagnosewebdebuggingerror"></a>IDebugCoreServer3::DiagnoseWebDebuggingError
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tente de déterminer la raison de l’échec de l’attachement automatique.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT DiagnoseWebDebuggingError(  
   LPCWSTR pszUrl  
);  
```  
  
```csharp  
int DiagnoseWebDebuggingError(  
   string pszUrl  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pszUrl`  
 dans Non utilisé actuellement ; doit toujours être défini sur une valeur null.  
  
## <a name="return-value"></a>Valeur renvoyée  
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur. Voici d’autres codes de retour classiques :  
  
|Code|Description|  
|----------|-----------------|  
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|Impossible de déterminer la raison pour laquelle le serveur distant n’a pas pu démarrer le débogage.|  
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|Impossible de déboguer sur le serveur distant, probablement en raison d’autorisations insuffisantes ou parce que le verbe de débogage n’est pas activé.|  
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|Le serveur Web a été verrouillé et bloque le verbe de débogage, qui est requis pour activer le débogage.|  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)
