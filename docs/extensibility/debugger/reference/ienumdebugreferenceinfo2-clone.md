---
title: 'IEnumDebugReferenceInfo2 :: Clone | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugReferenceInfo2::Clone
helpviewer_keywords:
- IEnumDebugReferenceInfo2::Clone
ms.assetid: 49c5a301-a33a-428f-b83b-e734c71af4ef
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d522fb7a9b63f634f312924e3c0b0337688aa430
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80715311"
---
# <a name="ienumdebugreferenceinfo2clone"></a>IEnumDebugReferenceInfo2::Clone
Retourne une copie de l'énumération actuelle comme un objet distinct.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Clone(
   IEnumDebugReferenceInfo2** ppEnum
);
```

```csharp
int Clone(
   out IEnumDebugReferenceInfo2 ppEnum
);
```

## <a name="parameters"></a>Paramètres
`ppEnum`\
[out] Retourne une copie de cette énumération en tant qu'objet distinct.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.

## <a name="remarks"></a>Notes
 La copie de l’énumération a le même État que l’original au moment où cette méthode est appelée. Toutefois, le de la copie et les États de l’original sont séparés et peuvent être modifiés individuellement.

## <a name="see-also"></a>Voir aussi
- [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)
