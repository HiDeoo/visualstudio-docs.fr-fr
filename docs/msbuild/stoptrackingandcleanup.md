---
title: StopTrackingAndCleanup | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- StopTrackingAndCleanup
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StopTrackingAndCleanup
ms.assetid: 9f8c5994-2dfc-43c3-a5fb-89b2f8990429
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1ffbebd651087d9aa877d0e257947352a0d0275e
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39154822"
---
# <a name="stoptrackingandcleanup"></a>StopTrackingAndCleanup
Arrête tout le suivi et libère la mémoire utilisée par la session de suivi.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp 
HRESULT WINAPI StopTrackingAndCleanup(void);  
```  
  
## <a name="return-value"></a>Valeur de retour  
 **HRESULT** avec le bit **SUCCEEDED** défini si le suivi a été arrêté.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** *FileTracker.h*  
  
## <a name="see-also"></a>Voir aussi  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)