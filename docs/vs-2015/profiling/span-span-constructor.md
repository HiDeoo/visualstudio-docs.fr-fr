---
title: span::span, constructeur | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::span::span
helpviewer_keywords:
- Concurrency::diagnostic::span constructor
ms.assetid: 8b5578aa-5e5c-4ac7-87c7-ce87c4246e2c
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: df6df731de90a9aad9e6cc637b3f218e481b66b7
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68198297"
---
# <a name="spanspan-constructor"></a>span::span, constructeur

[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Initialise une nouvelle instance de la classe `span`.

## <a name="syntax"></a>Syntaxe

```
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

**En-tête** : cvmarkersobj.h

**Espace de noms** : Concurrency::diagnostic

## <a name="see-also"></a>Voir aussi

[span, classe](../profiling/span-class.md)
