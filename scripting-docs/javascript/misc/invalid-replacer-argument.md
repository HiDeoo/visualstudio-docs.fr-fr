---
title: Argument de remplacement non valide | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5035
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4727186f-facd-4aa6-9447-bbefbae83f07
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 640eefb53304de48e4ad2398a02910a1cff1b57d
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56841284"
---
# <a name="invalid-replacer-argument"></a>Argument de remplacement incorrect
Une tentative a été effectuée pour appeler `JSON.stringify` avec un argument qui n’est pas valide. Le `replacer` argument doit être une fonction ou un tableau.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Modifier le `replacer` argument à une fonction ou un tableau.  
  
## <a name="example"></a>Exemple  
 Le code dans cet exemple génère une erreur d’exécution, car `memberfilter` est un objet au lieu d’une fonction ou un tableau.  
  
```JavaScript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
var memberfilter = new Object();  
  
// This line will cause a runtime error.  
var jsontext = JSON.stringify(contact, memberfilter, "\t");  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Objet JSON](../../javascript/reference/json-object-javascript.md)   
 [Fonction JSON.parse](../../javascript/reference/json-parse-function-javascript.md)   
 [Erreurs d’exécution JavaScript](../../javascript/reference/javascript-run-time-errors.md)