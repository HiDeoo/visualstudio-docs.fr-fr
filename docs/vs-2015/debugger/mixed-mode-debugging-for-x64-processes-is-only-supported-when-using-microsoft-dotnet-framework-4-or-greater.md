---
title: Le débogage en mode mixte pour les processus x64 est pris en charge uniquement lors de l’utilisation de Microsoft.NET Framework 4 ou version ultérieure | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e974269cccb65db66ee59735f7acc5de494e2106
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "65697830"
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>Le débogage en mode mixte des processus x64 est pris en charge uniquement lorsque vous utilisez Microsoft .NET Framework 4 ou version ultérieure
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Les versions du .NET Framework antérieures à la version 4 ne fournissent pas de prise en charge du débogage en mode mixte des processus x64. Cela signifie que vous ne pouvez pas passer du code managé au code natif, ou inversement, lorsque vous procédez au débogage.  
  
### <a name="workarounds"></a>Solutions de contournement  
  
- Mettez votre projet à jour de façon à utiliser Microsoft .NET Framework 4 ou version ultérieure.  
  
     –ou–  
  
     Déboguez votre code managé et natif dans des sessions de débogage distinctes.  
  
     –ou–  
  
     Déboguez votre code mixte en tant que processus 32 bits, de la façon décrite dans les procédures suivantes.  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>Pour passer en plateforme 32 bits (Visual Basic ou C#)  
  
1. Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le projet, puis cliquez sur **Propriétés**.  
  
2. Dans les pages de propriétés, cliquez sur l’onglet **Compiler** ou **Déboguer**.  
  
3. Cliquez sur **Plateforme** et sélectionnez x86 dans la liste.  
  
     Par défaut, les compilateurs C# et Visual Basic génèrent du code à exécuter sur n'importe quelle UC. Sur un ordinateur 64 bits, ces fichiers binaires sont exécutés en tant que processus 64 bits. Pour une exécution sur un processus 32 bits, vous devez sélectionner **Win32**, et non pas **AnyCPU**.  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>Pour passer en plateforme 32 bits (C/C++)  
  
1. Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur votre projet, puis sélectionnez **Propriétés**.  
  
2. Dans les pages de propriétés, cliquez sur **Plateforme**, puis sélectionnez Win32 dans la liste.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
- Consultez [configuration du débogage SQL](https://msdn.microsoft.com/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Voir aussi  
 [Déboguer des applications 64 bits](../debugger/debug-64-bit-applications.md)
