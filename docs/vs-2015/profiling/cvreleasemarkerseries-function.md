---
title: CvReleaseMarkerSeries, fonction | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- cvmarkers/CvReleaseMarkerSeries
helpviewer_keywords:
- CvReleaseMarkerSeries method
ms.assetid: 3b4711ee-e534-411d-9128-f69cd7932a48
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6bfa9952a834110ef0fea36568ea210b637547aa
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68177750"
---
# <a name="cvreleasemarkerseries-function"></a>CvReleaseMarkerSeries, fonction
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Libère la série de marqueurs. N’utilisez pas l’objet de série de marqueurs après sa libération, car cela peut entraîner le blocage de l’application. Si la libération de la série de marqueurs échoue, une fuite de mémoire se produit.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CvReleaseMarkerSeries(  
   _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pMarkerSeries`  
 Adresse de variable objet de fournisseur. L’adresse ne peut pas être Null et la variable peut avoir n’importe quelle valeur.  
  
## <a name="return-value"></a>Valeur renvoyée  
 S_OK lorsque la série de marqueurs est correctement libérée, ou code d’erreur en cas d’erreur. Utilisez les macros SUCCEEDED/FAILED pour vérifier la condition d’erreur.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête** : cvmarkers.h  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur la bibliothèque C++](../profiling/cpp-library-reference.md)
