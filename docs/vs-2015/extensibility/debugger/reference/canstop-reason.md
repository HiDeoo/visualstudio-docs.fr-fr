---
title: CANSTOP_REASON | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CANSTOP_REASON
helpviewer_keywords:
- CANSTOP_REASON enumeration
ms.assetid: 6da944eb-36cd-4a8c-8d71-544c775cfcc1
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6ea8242e4c7bdd820dd30cfb2c86cde60cda8bcd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47505132"
---
# <a name="canstopreason"></a>CANSTOP_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [CANSTOP_REASON](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/canstop-reason).  
  
Utilisé pour déterminer si un programme peut arrêter l’exécution après avoir atteint un point particulier dans l’exécution.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
typedef DWORD CANSTOP_REASON;  
```  
  
```csharp  
public enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
```  
  
## <a name="members"></a>Membres  
 CANSTOP_ENTRYPOINT  
 Spécifie le point d’entrée du programme donné.  
  
 CANSTOP_STEPIN  
 Spécifie le pas à pas détaillé dans une fonction.  
  
## <a name="remarks"></a>Notes  
 Passé en tant qu’argument à la [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) méthode pour vérifier avec le Gestionnaire de Session de débogage (SDM) s’il s’agit OK arrêter après avoir atteint le point d’entrée du programme ou après l’exécution pas à pas dans une fonction ou méthode.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)

