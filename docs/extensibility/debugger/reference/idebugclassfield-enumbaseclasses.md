---
title: IDebugClassField::EnumBaseClasses | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugClassField::EnumBaseClasses
helpviewer_keywords:
- IDebugClassField::EnumBaseClasses method
ms.assetid: 78749674-ef75-46d3-a1f4-ff33afd90e32
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3001dab0528a0a21ed11befe75b9d2ef4b314ed1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53986490"
---
# <a name="idebugclassfieldenumbaseclasses"></a>IDebugClassField::EnumBaseClasses
Crée un énumérateur pour les classes de base de cette classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumBaseClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumBaseClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `ppEnum`  
 [out] Retourne un [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objet représentant la liste des classes de base. Retourne une valeur null si aucune classe de base.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne S_OK, renvoie la valeur S_SH_NO_BASE_CLASSES si aucune classe de base (et le `ppEnum` paramètre est défini sur une valeur null) ; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Les classes de base dans l’objet énumérateur sont spécifiés dans l’ordre de la classe de base plus immédiate (ou la plus dérivée) à la classe de base plus à distance. Par exemple, étant donné les classes C++ :  
  
```  
class Root { }  
class Level1 : Root { }  
class Level2 : Level1 { }  
class MyClass : Level2 { }  
```  
  
 L’énumération retournerait les classes de base dans l’ordre `Level2`, `Level1`, `Root`.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)