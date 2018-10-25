---
title: IDiaSymbol::get_container | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_container method
ms.assetid: 24e832eb-80b3-484c-a41b-11477ec9de99
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d293971cfcd0723485d4a5b21d4e431de64ddd65
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49822733"
---
# <a name="idiasymbolgetcontainer"></a>IDiaSymbol::get_container
Cette fonction récupère un pointeur vers un symbole représentant le conteneur/parent de ce symbole.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_container(  
   IDiaSymbol **pRetVal  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pRetVal`  
 [out] Retourne un pointeur vers un `IDiaSymbol` contenant des informations sur le conteneur de ce symbole.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne S_OK ; Sinon, retourne S_FALSE ou un code d’erreur.  
  
> [!NOTE]
>  Une valeur de retour de S_FALSE signifie que la propriété n’est pas disponible pour le symbole.  
  
## <a name="requirements"></a>Configuration requise  
  
|Spécification|Description|  
|-----------------|-----------------|  
|En-tête :|dia2.h|  
|Version :|DIA SDK 8.0|  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)