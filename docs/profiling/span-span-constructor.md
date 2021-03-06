---
title: span::span, constructeur | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::span::span
helpviewer_keywords:
- Concurrency::diagnostic::span constructor
ms.assetid: 8b5578aa-5e5c-4ac7-87c7-ce87c4246e2c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f761e87c1658c11bfdfd93a4f4e22299d88575a8
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "62979820"
---
# <a name="spanspan-constructor"></a>span::span, constructeur

Initialise une nouvelle instance de la classe `span`.

## <a name="syntax"></a>Syntaxe

```cpp
span(
   const marker_series& _Series,
   _In_ LPCTSTR _Format,
   ...
);
span(
   const marker_series& _Series,
   marker_importance _Importance,
   _In_ LPCTSTR _Format,
   ...
);
span(
   const marker_series& _Series,
   int _Category,
   _In_ LPCTSTR _Format,
   ...
);
span(
   const marker_series& _Series,
   marker_importance _Importance,
   int _Category,
   _In_ LPCTSTR _Format,
   ...
);
```

#### <a name="parameters"></a>Paramètres

`_Series` Contexte valide de la série de marqueurs.

`_Format` Chaîne de mise en forme composite contenant du texte associé à zéro, un ou plusieurs éléments de mise en forme qui correspondent aux objets de la liste d’arguments.

`_Importance` Niveau d’importance.

`_Category` Catégorie.

## <a name="requirements"></a>Configuration requise

**En-tête :** *cvmarkersobj.h*

**Espace de noms** : Concurrency::diagnostic

## <a name="see-also"></a>Voir aussi

- [span, classe](../profiling/span-class.md)