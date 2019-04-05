---
title: Énumération SCRIPTTRACEINFO | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: cb8a4767-8c8e-4fa0-a735-038767a8c500
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ed2c6566db8209280be7f102a55c7de8cf85c44
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155808"
---
# <a name="scripttraceinfo-enumeration"></a>SCRIPTTRACEINFO, énumération
Représente l’événement de script qui est tracée. Utilisé dans le [iactivescriptsitetraceinfo::sendscripttraceinfo, méthode](../../winscript/reference/iactivescriptsitetraceinfo-sendscripttraceinfo-method.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef enum tagSCRIPTTRACEINFO {      SCRIPTTRACEINFO_SCRIPTSTART = 0,      SCRIPTTRACEINFO_SCRIPTEND   = 1,      SCRIPTTRACEINFO_COMCALLSTART    = 2,      SCRIPTTRACEINFO_COMCALLEND  = 3,      SCRIPTTRACEINFO_CREATEOBJSTART  = 4,      SCRIPTTRACEINFO_CREATEOBJEND    = 5,      SCRIPTTRACEINFO_GETOBJSTART = 6,      SCRIPTTRACEINFO_GETOBJEND   = 7,  } SCRIPTTRACEINFO ;  
```  
  
## <a name="enumeration-values"></a>Valeurs d’énumération  
  
|||  
|-|-|  
|SCRIPTTRACEINFO_SCRIPTSTART|Le début d’un script.|  
|SCRIPTTRACEINFO_SCRIPTEND|La fin du script.|  
|SCRIPTTRACEINFO_COMCALLSTART|Le début d’un appel COM.|  
|SCRIPTTRACEINFO_COMCALLEND|La fin d’un appel COM.|  
|SCRIPTTRACEINFO_CREATEOBJSTART|Début de la création d’objets.|  
|SCRIPTTRACEINFO_CREATEOBJEND|La fin de la création d’objets.|  
|SCRIPTTRACEINFO_GETOBJSTART|Le début d’un appel de GetObject.|  
|SCRIPTTRACEINFO_GETOBJEND|La fin d’un appel de GetObject.|