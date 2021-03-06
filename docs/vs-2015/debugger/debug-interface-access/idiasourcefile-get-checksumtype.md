---
title: IDiaSourceFile::get_checksumType | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_checksumType method
ms.assetid: 4c363e61-a6a9-409a-9cc0-d06eb2bee645
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f859bce63e2976b23ab613e249dad41b2bc63486
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68190699"
---
# <a name="idiasourcefileget_checksumtype"></a>IDiaSourceFile::get_checksumType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Récupère le type de somme de contrôle.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_checksumType (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pRetVal`  
 à Retourne le type de somme de contrôle.  
  
## <a name="return-value"></a>Valeur renvoyée  
 En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.  
  
## <a name="remarks"></a>Notes  
 Le type de somme de contrôle est une valeur qui peut être mappée à un algorithme de somme de contrôle. Par exemple, le format de fichier PDB standard peut généralement avoir l’une des valeurs suivantes :  
  
|Type de checksum|Étiquette CryptoAPI|Description|  
|-------------------|---------------------|-----------------|  
|0|\<none>|Aucun checksum présent.|  
|1|`CALG_MD5`|somme de contrôle générée avec l’algorithme de hachage MD5.|  
|2|`CALG_SHA1`|somme de contrôle générée avec l’algorithme de hachage SHA1.|  
  
 Les `CryptoAPI` étiquettes proviennent de l' `ALG_ID` énumération. Pour plus d’informations sur les algorithmes de hachage, consultez la `CryptoAPI` section de Microsoft [!INCLUDE[winsdkshort](../../includes/winsdkshort-md.md)] .  
  
 Pour obtenir les octets de somme de contrôle réels pour le fichier source, appelez la méthode [IDiaSourceFile :: get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md) .  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)
