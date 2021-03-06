---
title: IDiaAddressMap::set_addressMap | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_addressMap method
ms.assetid: 81e82073-089b-43d5-af39-49d7a4907c7a
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 693ecf6e8fd4f0b55936bde371b7baa6975b8f2c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68198648"
---
# <a name="idiaaddressmapset_addressmap"></a>IDiaAddressMap::set_addressMap
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Fournit un mappage d’adresses pour prendre en charge les traductions de disposition d’image.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT set_addressMap (   
   DWORD                     cbData,  
   struct DiaAddressMapEntry data[],  
   BOOL                      imagetoSymbols  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `cbData`  
 dans Nombre d’éléments dans le `data` paramètre.  
  
 `data[]`  
 dans Tableau de structures de [structure DiaAddressMapEntry](../../debugger/debug-interface-access/diaaddressmapentry.md) qui définissent le mappage de la traduction.  
  
 `imagetoSymbols`  
 [in] `TRUE` Si le `data` paramètre définit un mappage de la nouvelle disposition d’image à la disposition d’origine (comme décrit par les symboles de débogage). `FALSE` Si `data` est une carte à laquelle la nouvelle disposition d’image provient de la disposition d’origine.  
  
## <a name="return-value"></a>Valeur renvoyée  
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.  
  
## <a name="remarks"></a>Notes  
 En règle générale, le DIA récupère les mappages de traduction d’adresses à partir du fichier de base de données du programme (. pdb). Si ces valeurs sont manquantes, la méthode [IDiaAddressMap :: set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) est appelée deux fois, une fois avec le `imagetoSymbols` paramètre défini sur `TRUE` et une fois avec le `imagetoSymbols` paramètre défini sur `FALSE` . Les traductions de mappage d’adresses ne peuvent pas être activées à l’aide de la méthode [IDiaAddressMap ::p ut_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md) , sauf si les deux mappages de traduction sont fournis.  
  
## <a name="see-also"></a>Voir aussi  
 [DiaAddressMapEntry, structure](../../debugger/debug-interface-access/diaaddressmapentry.md)   
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap ::p ut_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)
