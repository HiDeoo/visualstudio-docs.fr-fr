---
title: Chiffre hexadécimal attendu | Microsoft Docs
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
- VS.WebClient.Help.SCRIPT1023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 67a86df7-49f9-43cb-99c6-99b1a427827a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9e29131c4ecf4f476a30da94ec67676d6bea347
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49836175"
---
# <a name="expected-hexadecimal-digit"></a>Chiffre hexadécimal attendu
Vous avez créé une séquence d’échappement Unicode incorrecte. Séquences d’échappement Unicode commencent par \u, suivie de quatre chiffres hexadécimaux (plus n’et pas moins). Les chiffres hexadécimaux Unicode peuvent contenir uniquement les chiffres 0-9, les lettres majuscules A-F et les minuscules des lettres a-f. L’exemple suivant montre une séquence d’échappement Unicode correctement formée.  
  
```JavaScript  
z = "\u1A5F";  
```  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Vérifiez que vos chiffres hexadécimaux Unicode commencent par \u, contient uniquement les nombres 0-9, les lettres majuscules A-F, les minuscules des lettres a-f ; et sont regroupés en quatre chiffres.  
  
    > [!NOTE]
    >  Si vous souhaitez utiliser le texte littéral \u dans une chaîne, puis utilisez deux barres obliques inverses - (\\\u)-un à la séquence d’échappement de la première barre oblique inverse.  
  
## <a name="see-also"></a>Voir aussi  
 [Types de données](../../javascript/data-types-javascript.md)