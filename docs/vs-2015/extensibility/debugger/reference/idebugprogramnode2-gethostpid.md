---
title: 'IDebugProgramNode2 :: GetHostPid | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgramNode2::GetHostPid
helpviewer_keywords:
- IDebugProgramNode2::GetHostPid
ms.assetid: e65b4b15-46d8-4ca7-9456-2b4c078f7cf9
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 38b2889689f45127e507147da0d5488e9e4a8f9f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68148581"
---
# <a name="idebugprogramnode2gethostpid"></a>IDebugProgramNode2::GetHostPid
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Obtient l’identificateur de processus système pour le processus qui héberge le programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetHostPid (   
   AD_PROCESS_ID * pdwHostPid  
);  
```  
  
```csharp  
int GetHostPid (   
   out AD_PROCESS_ID pdwHostPid  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pdwHostPid`  
 à Retourne l’identificateur de processus système pour le processus d’hébergement.  
  
## <a name="return-value"></a>Valeur renvoyée  
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment implémenter cette méthode pour un `CProgram` objet simple qui implémente l’interface [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) .  
  
```cpp#  
HRESULT CProgram::GetHostPid(DWORD* pdwHostPid) {    
    // Check for valid argument.    
   if (pdwHostPid)    
    {    
        // Get the process identifier of the calling process.    
      *pdwHostPid = GetCurrentProcessId();    
  
        return S_OK;    
    }    
  
    return E_INVALIDARG;    
}    
```  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
