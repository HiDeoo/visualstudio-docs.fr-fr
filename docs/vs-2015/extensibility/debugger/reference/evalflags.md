---
title: EVALFLAGS | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- EVALFLAGS
helpviewer_keywords:
- EVALFLAGS enumeration
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9e6ee00402c13b2a79e4e6757a127211eda9c3c0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68149388"
---
# <a name="evalflags"></a>EVALFLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Spécifie les indicateurs qui contrôlent l’évaluation de l’expression.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
};  
typedef DWORD EVALFLAGS;  
```  
  
```csharp  
public enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
}  
```  
  
## <a name="members"></a>Membres  
 EVAL_RETURNVALUE  
 Spécifie que la valeur de retour, le cas échéant, doit être évaluée.  
  
 EVAL_NOSIDEEFFECTS  
 Spécifie que les effets secondaires ne sont pas autorisés.  
  
 EVAL_ALLOWBPS  
 Spécifie l’arrêt sur les points d’arrêt.  
  
 EVAL_ALLOWERRORREPORT  
 Spécifie les rapports d’erreurs à autoriser pour l’hôte. Principalement utilisé pour l’évaluation de l’expression dans le script dans Internet Explorer.  
  
 EVAL_FUNCTION_AS_ADDRESS  
 Force les fonctions à être évaluées en tant qu’adresses, au lieu d’appeler la fonction.  
  
 EVAL_NOFUNCEVAL  
 Empêche l’évaluation de la fonction. Par exemple, considérez le `int` jeton dans l’expression `myExpression(int) + 10` . Cette fonction peut être correctement évaluée en tant qu’adresse, mais pas en tant que valeur.  
  
 EVAL_NOEVENTS  
 Indicateur qui spécifie que les événements qui se produisent pendant l’évaluation de l’expression ne doivent pas être envoyés au gestionnaire de débogage de session (SDM) ou à l’IDE.  
  
## <a name="remarks"></a>Notes  
 Ces indicateurs sont passés comme argument aux méthodes [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) et [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) .  
  
 Ces indicateurs peuvent être combinés avec une opération or au niveau du bit.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg. h  
  
 Espace de noms : Microsoft. VisualStudio. Debugger. Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)
