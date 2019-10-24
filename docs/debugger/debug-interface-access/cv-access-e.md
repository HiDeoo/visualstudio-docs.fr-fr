---
title: CV_access_e | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bbe338ba9d3aa6cbc795606c3fa285526afdfd36
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745370"
---
# <a name="cv_access_e"></a>CV_access_e
Spécifie la portée de la visibilité (niveau d’accès) des variables et des fonctions membres.

## <a name="syntax"></a>Syntaxe

```C++
typedef enum CV_access_e {
    CV_private   = 1,
    CV_protected = 2,
    CV_public    = 3
} CV_access_e;
```

## <a name="elements"></a>Éléments
Le membre CV_private a un accès privé.

Le membre CV_protected a un accès protégé.

Le membre CV_public a un accès public.

## <a name="remarks"></a>Notes
Le spécificateur d’accès `friend` n’est pas inclus ici, car il est généralement utilisé par les fonctions non-membres qui ont accès aux éléments privés et protégés de la classe. Utilisez la méthode [IDiaSymbol :: get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) pour rechercher des symboles avec accès `SymTagFriend`.

## <a name="requirements"></a>spécifications
En-tête : cvconst. h

## <a name="see-also"></a>Voir aussi
- [Énumérations et structures](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)
- [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)
