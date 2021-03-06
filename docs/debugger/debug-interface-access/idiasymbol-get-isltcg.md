---
title: IDiaSymbol::get_isLTCG | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isLTCG method
ms.assetid: 5f7f05b8-6b71-4958-9e1e-e4924ef9c59b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 009fcf437f56852e324e392f6a5691dd23e23ebc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85463364"
---
# <a name="idiasymbolget_isltcg"></a>IDiaSymbol::get_isLTCG
Récupère un indicateur qui spécifie si le [compiland](../../debugger/debug-interface-access/compiland.md) a été lié au commutateur de l’éditeur de liens [/LTCG (génération de code durant l’édition de liens)](/cpp/build/reference/ltcg-link-time-code-generation), qui facilite l’optimisation de l’ensemble du programme. Ce commutateur s’applique uniquement au code managé.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_iSLTCG(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>Paramètres
 pFlag

à Retourne `TRUE` si le `compiland` a été lié avec le commutateur de l’éditeur de liens/LTCG ; sinon, retourne `FALSE` .

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` ; sinon, retourne `S_FALSE` ou un code d’erreur.

> [!NOTE]
> Une valeur de retour `S_FALSE` signifie que la propriété n’est pas disponible pour le symbole.

## <a name="requirements"></a>Configuration requise

|Condition requise|Description|
|-----------------|-----------------|
|En-tête :|dia2.h|
|Version :|DIA SDK v 8.0|

## <a name="see-also"></a>Voir aussi
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)