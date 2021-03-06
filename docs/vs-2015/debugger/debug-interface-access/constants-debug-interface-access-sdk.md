---
title: Constantes (kit de développement logiciel de debug interface Access) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- constants, DIA SDK
- DIA SDK, constants
ms.assetid: aca4ec77-bc08-4cdd-a6ce-8d4a28ea5ea3
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 931e1ab46793a5ff7e0434949330eaf4dbc820e8
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68164429"
---
# <a name="constants-debug-interface-access-sdk"></a>Constantes (Kit de développement logiciel Debug Interface Access)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ces constantes de chaîne peuvent être utilisées pour identifier les différentes sections d’un fichier de base de données de débogage de programme (PDB) via le kit de développement DIA (SDK).  
  
## <a name="constants"></a>Constantes  
 Les éléments suivants sont déclarés en tant que macros C/C++.  
  
|Macro|Valeur|  
|-----------|-----------|  
|`DiaTable_Symbols`|L"Symbols"|  
|`DiaTable_Sections`|L"Sections"|  
|`DiaTable_SrcFiles`|L"SourceFiles"|  
|`DiaTable_LineNums`|L"LineNumbers"|  
|`DiaTable_SegMap`|L"SegmentMap"|  
|`DiaTable_Dbg`|L"Dbg"|  
|`DiaTable_InjSrc`|L"InjectedSource"|  
|`DiaTable_FrameData`|L"FrameData"|  
  
## <a name="example"></a>Exemple  
 Voici un exemple utilisant l’un de ces symboles :  
  
```cpp#  
HRESULT GetSymbolTable(IDiaEnumTables *pEnumTables, IDiaTable **pTable)  
{  
    HRESULT hr;  
    VARIANT var;  
    var.vt      = VT_BSTR;  
    var.bstrVal = SysAllocString( DiaTable_Symbols );  
    hr = pEnumTables->Item( var, pTable );  
    return(hr);  
}  
```  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : Dia2. h  
  
## <a name="see-also"></a>Voir aussi  
 [Faire](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)   
 [Énumérations et structures](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Interfaces (kit de développement logiciel de debug interface Access)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)
