---
title: CompilandEnv | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CompilandEnv symbol
ms.assetid: 808404bb-ece1-47f1-b9ea-c76d4d86ddd9
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9dfa9f1efa266a95e0580717b06cee4b9d2a7725
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68164443"
---
# <a name="compilandenv"></a>CompilandEnv
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Le compilateur peut inclure des variables d’environnement supplémentaires avec des symboles. Il y a un `SymTagCompilandEnv` symbole pour chacune de ces variables.  
  
## <a name="properties"></a>Propriétés  
 Le tableau suivant présente les propriétés qui sont valides pour ce type de symbole.  
  
|Propriété|Type de données|Description|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbole du compiland parent.|  
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID du symbole parent lexical.|  
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Nom de la variable.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID d’index du symbole.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Retourne `SymTagCompilandEnv` (l’une des valeurs d' [énumération SymTagEnum](../../debugger/debug-interface-access/symtagenum.md) ).|  
|[IDiaSymbol::get_value](../../debugger/debug-interface-access/idiasymbol-get-value.md)|`VARIANT`|Contenu à valeur de chaîne de la variable ( `VT_BSTR` ).|  
  
## <a name="see-also"></a>Voir aussi  
 [Compiland](../../debugger/debug-interface-access/compiland.md)   
 [Hiérarchie lexicale des types de symboles](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)
