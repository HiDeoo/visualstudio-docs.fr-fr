---
title: CvCreateMarkerSeriesWithCodePageA, fonction | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cvmakers/CvCreateMarkerSeriesWithCodePageA
helpviewer_keywords:
- CvCreateMarkerSeriesWithCodePageA method
ms.assetid: 3d7ed601-2222-4be9-a557-f217db008753
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e17083c48db1ba1aa6b7ff45ee467ac97900e101
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85332425"
---
# <a name="cvcreatemarkerserieswithcodepagea-function"></a>CvCreateMarkerSeriesWithCodePageA, fonction
Crée des séries de marqueurs pour un fournisseur donné et une page de codes spécifiée. Cette fonction peut être utilisée pour spécifier explicitement la page de codes pour le texte écrit par les fonctions ANSI API de marqueur. Il peut être utile de définir la page de codes lorsque la trace est capturée puis analysée sur plusieurs ordinateurs ayant des langues et des paramètres régionaux différents. Par défaut, c’est la page de codes retournée par la fonction GetACP() qui est utilisée.

## <a name="syntax"></a>Syntaxe

```C
HRESULT CvCreateMarkerSeriesWithCodePageA(
   _In_ PCV_PROVIDER pProvider,
   _In_ LPCSTR pSeriesName,
   _In_ UINT nTextCodePage,
   _Out_ PCV_MARKERSERIES* ppMarkerSeries
);
```

#### <a name="parameters"></a>Paramètres
 `pProvider` Objet fournisseur initialisé par CvInitProvider. Ne peut pas avoir la valeur NULL.

 `pSeriesName` Nom de la série de marqueurs. Ne peut pas être Null, mais une chaîne vide est acceptée.

 `nTextCodePage` Page de codes valide.

 `ppMarkerSeries` Adresse d’une variable de sortie qui doit stocker le contexte de la série de marqueurs. Ne peut pas avoir la valeur NULL.

## <a name="return-value"></a>Valeur retournée
 S_OK lorsque la série de marqueurs est correctement créée, ou code d’erreur en cas d’erreur. Utilisez les macros SUCCEEDED/FAILED pour vérifier la condition d’erreur.

## <a name="requirements"></a>Spécifications
 **En-tête :** *cvmarkers.h*

## <a name="see-also"></a>Voir aussi
- [Informations de référence sur la bibliothèque C++](../profiling/cpp-library-reference.md)