---
title: Comment puis-je déboguer les violations d'accès lorsque mon programme fonctionne hors du débogueur ? | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ce5b21f92eecf2e8929c142bc1ee32e20d386335
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "74299251"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Comment puis-je déboguer les violations d'accès lorsque mon programme fonctionne hors du débogueur ?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Description du problème  
 Mon programme fonctionne correctement dans l'environnement Visual Studio, mais lorsque je l'exécute de façon autonome avec le système d'exploitation Windows, il génère une violation d'accès. Comment puis-je corriger cette erreur ?  
  
## <a name="solution"></a>Solution  
 Paramétrez l’option [Débogage juste-à-temps](../debugger/just-in-time-debugging-in-visual-studio.md) et exécutez votre programme de façon autonome jusqu’à ce que la violation d’accès se produise. Dans la boîte de dialogue **Violation d’accès**, vous pouvez ensuite cliquer sur **Annuler** afin de démarrer le débogueur.  
  
 Consultez également, dans la Base de connaissances, l'article Q133174, « How to Locate Where a General Protection (GP) Fault Occurs ». Vous pouvez trouver des Articles de la base de connaissances sur le CD-ROM MSDN Library ou en effectuant une recherche [http://support.microsoft.com/](https://support.microsoft.com/) .  
  
## <a name="see-also"></a>Voir aussi  
 [FAQ sur le débogage du code natif](../debugger/debugging-native-code-faqs.md)   
 [Débogage du code natif](../debugger/debugging-native-code.md)
