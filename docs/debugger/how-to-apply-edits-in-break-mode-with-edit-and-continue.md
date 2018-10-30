---
title: 'Comment : appliquer des modifications en Mode arrêt avec modifier et continuer | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [Visual Basic], applying edits in break mode
- break mode, applying code changes
- Edit and Continue, applying edits in break mode
- editing, break mode
- coding, editing in break mode
- code, editing in break mode
ms.assetid: 1eef7498-6a1f-4fba-8146-510adc6375c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 263e4bf4505995a4c8eccbe7c33f59115412dda5
ms.sourcegitcommit: d462dd10746624ad139f1db04edd501e7737d51e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50219508"
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue"></a>Comment : appliquer des modifications en mode arrêt à l'aide de la fonctionnalité Modifier & Continuer
Vous pouvez utiliser Modifier & Continuer pour modifier votre code en mode Arrêt, puis continuer sans arrêter et redémarrer l'exécution.  
  
Pour connaître les limitations sur l’utilisation de modifier & Continuer pendant le débogage, consultez [pris en charge les modifications de Code (C# et Visual Basic](../debugger/supported-code-changes-csharp.md)]
  
### <a name="to-edit-code-in-break-mode"></a>Pour modifier du code en mode Arrêt  
  
1.  Passez en mode Arrêt en procédant de l'une des manières suivantes :  
  
    -   Définissez un point d’arrêt dans votre code, puis choisissez **démarrer le débogage** à partir de la **déboguer** menu et attendez que l’application atteindre le point d’arrêt.  
  
         - ou -  
  
    -   Démarrer le débogage, puis sélectionnez **interrompre tout** à partir de la **déboguer** menu.  
  
         - ou -  
  
    -   Lorsqu’une exception se produit, choisissez **activer la modification** sur le **Assistant Exception**.  
  
2.  Apportez les modifications de code souhaitées et pris en charge.  
  
     Pour plus d’informations, consultez [pris en charge les modifications de Code (C# et Visual Basic](../debugger/supported-code-changes-csharp.md).  
  
    > [!NOTE]
    >  Si vous tentez d’effectuer une modification du code qui n’est pas autorisée par l’opération Modifier & Continuer, votre modification est soulignée d’un trait ondulé violet et une tâche s’affiche dans la liste des tâches. Il vous est impossible de continuer l'exécution du code sauf si vous annulez la modification de code non autorisée.  
  
3.  Sur le **déboguer** menu, cliquez sur **continuer** pour reprendre l’exécution.  
  
     Votre code s'exécute désormais avec les modifications que vous avez appliquées dans le projet.  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge des modifications de Code (C# et Visual Basic](../debugger/supported-code-changes-csharp.md)   
 [Modifier & Continuer (Visual Basic)](../debugger/edit-and-continue-visual-basic.md)