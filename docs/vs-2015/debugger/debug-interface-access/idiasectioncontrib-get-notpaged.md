---
title: IDiaSectionContrib::get_notPaged | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_notPaged method
ms.assetid: bb6baa40-fece-4a4c-aba9-f4b41f418f8b
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1899e59e6eb11b53757d28f9babc09739b1fdad3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68151883"
---
# <a name="idiasectioncontribget_notpaged"></a>IDiaSectionContrib::get_notPaged
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Récupère un indicateur qui signale si la section ne peut pas être paginée en mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_notPaged (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pRetVal`  
 [out, retval] Retourne `TRUE` si la section ne peut pas être paginée ; sinon, retourne `FALSE` .  
  
## <a name="return-value"></a>Valeur renvoyée  
 En cas de réussite, retourne `S_OK`. Retourne `S_FALSE` si cette propriété n’est pas prise en charge. Sinon, retourne un code d'erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
