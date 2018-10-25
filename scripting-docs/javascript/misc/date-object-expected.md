---
title: Objet date attendu | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5006
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d6ab82e6-ca64-46b4-a06c-5c6b0aa057cb
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 05e27b822f933ade811084552f6f0379257ae82e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49947639"
---
# <a name="date-object-expected"></a>Objet date attendu
Vous avez tenté d’appeler le **Date.prototype.toString** ou **Date.prototype.valueOf** méthode sur un objet d’un type autre que `Date`. L’objet de ce type d’appel doit être de type `Date`. Exemple :  
  
```JavaScript  
var o = new Object;  
o.f = Date.prototype.toString;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Appelez le **Date.prototype.toString** ou **Date.prototype.valueOf** méthodes sur des objets de type `Date`.  
  
## <a name="see-also"></a>Voir aussi  
 [Objet Date](../../javascript/reference/date-object-javascript.md)   
 [GETDATE, méthode (Date)](../../javascript/reference/getdate-method-date-javascript.md)   
 [Objets intrinsèques](../../javascript/intrinsic-objects-javascript.md)