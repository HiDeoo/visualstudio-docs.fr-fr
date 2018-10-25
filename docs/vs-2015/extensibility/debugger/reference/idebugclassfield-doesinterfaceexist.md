---
title: IDebugClassField::DoesInterfaceExist | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugClassField::DoesInterfaceExist
helpviewer_keywords:
- IDebugClassField::DoesInterfaceExist method
ms.assetid: cc0c8642-1a76-4fda-a309-7018a34883c9
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b386e3a64c05829ab2e5b6ac9f16a438eee5e625
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49925576"
---
# <a name="idebugclassfielddoesinterfaceexist"></a>IDebugClassField::DoesInterfaceExist
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Détermine si une interface spécifique est définie dans la classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT DoesInterfaceExist(   
   LPCOLESTR pszInterfaceName  
);  
```  
  
```csharp  
int DoesInterfaceExist(  
   [In] string pszInterfaceName  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pszInterfaceName`  
 [in] Chaîne contenant le nom de l’interface à rechercher.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne S_OK, retourne S_FALSE si l’interface n’existe pas ; Sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Notes  
 En effet, cette méthode obtient une énumération de toutes les interfaces et recherche dans la liste pour une interface correspondant.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)

