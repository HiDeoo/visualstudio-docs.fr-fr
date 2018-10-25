---
title: Modifier & Continuer (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 05/31/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C++]
- debugging [C++], Edit and Continue
- C/C++, Edit and Continue
ms.assetid: 1815251e-a877-433e-9e5e-69bd9ba254c7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 7e468f75abbadbe46ea973a5c04d2e286fcfaca5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49867700"
---
# <a name="edit-and-continue-visual-c"></a>Modifier & Continuer (Visual C++)
Vous pouvez utiliser Modifier et continuer dans les projets Visual C++. Consultez [modifications de Code prises en charge (C++)](../debugger/supported-code-changes-cpp.md) pour plus d’informations sur les limitations de modifier & Continuer.
  
Pour plus d’informations sur les améliorations de Visual Studio 2015 Update 3, consultez [C++ Modifier & Continuer dans Visual Studio 2015 Update 3](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/).  
  
 Le [/Zo (améliorer le débogage optimisé)](/cpp/build/reference/zo-enhance-optimized-debugging) option du compilateur qui a été introduite dans Visual Studio 2013 Update 3 ajoute des informations supplémentaires aux fichiers de symboles (.pdb) pour les fichiers binaires compilés sans le [/Od (désactiver (débogage)) ](https://msdn.microsoft.com/library/aafb762y.aspx) option.  
  
 **/ Zo** désactive Modifier & Continuer. Consultez [Comment : déboguer le Code optimisé](../debugger/how-to-debug-optimized-code.md).  
  
##  <a name="BKMK_Enable_or_disable_automatic_invocation_of_Edit_and_Continue"></a> Activer ou désactiver Modifier & Continuer  
 Vous pouvez désactiver l’appel automatique de Modifier & Continuer si vous apportez des modifications au code que vous ne souhaitez pas appliquer tout de suite, pendant la session de débogage en cours. Vous pouvez également réactiver la fonctionnalité automatique Modifier & Continuer.

> [!IMPORTANT]
> Pour les paramètres de build requis et d’autres informations sur la compatibilité de la fonctionnalité, consultez [C++ Modifier & Continuer dans Visual Studio 2015 Update 3] (https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/.
  
1. Si vous êtes dans une session de débogage, arrêtez le débogage (**MAJ + F5**).

2. Dans le menu **Outils** , choisissez **Options**.
  
3. Dans le **Options** boîte de dialogue, sélectionnez **débogage > Général**.

4. Pour activer, sélectionnez **Activer Modifier & Continuer**. Pour désactiver, désactivez la case à cocher.
  
5. Dans le groupe **Modifier &amp; Continuer** , cochez ou décochez la case **Activer Modifier et Continuer natif** .  
  
   La modification de ce paramètre s’applique à tous vos projets actuels. Après avoir modifié ce paramètre, il n'est pas nécessaire de régénérer l'application. Si vous générez votre application à partir de la ligne de commande ou d’un makefile, mais vous déboguez dans l’environnement Visual Studio, vous pouvez encore utiliser Modifier & Continuer si vous définissez la **/Zi** option.  
  
##  <a name="BKMK_How_to_apply_code_changes_explicitly"></a> Comment appliquer des modifications du code explicitement  
 Dans Visual C++, Modifier & Continuer peut appliquer des modifications de code de deux manières. Les modifications du code peuvent être implicitement appliquées, lorsque vous choisissez une commande d'exécution, ou explicitement, à l'aide de la commande **Appliquer les modifications du code** .  
  
 Lorsque vous appliquez des modifications du code explicitement, votre programme reste en mode arrêt - aucune exécution se produit.  
  
-   Pour appliquer les modifications du code explicitement, dans le menu **Déboguer** , choisissez **Appliquer les modifications du code**.  
  
##  <a name="BKMK_How_to_stop_code_changes"></a> Comment arrêter des modifications de code  
 Pendant que Modifier & Continuer est en train d'appliquer les modifications du code, vous pouvez arrêter l'opération.  
  
 Pour arrêter d'appliquer les modifications du code :  
  
- Dans le menu **Déboguer** , choisissez **Cesser d'appliquer les modifications du code**.  
  
  Cet élément de menu est visible uniquement lorsque les modifications du code sont appliquées.  
  
  Si vous choisissez cette option, aucune modification du code n'est validée.  
  
##  <a name="BKMK_How_to_reset_the_point_of_execution"></a> Comment réinitialiser le point d'exécution  
 Certaines modifications du code peuvent entraîner le déplacement du point d'exécution vers un nouvel emplacement lorsque le mode Modifier & Continuer applique les modifications. Bien que Modifier & Continuer place le point d'exécution aussi précisément que possible, les résultats risquent d'être incorrects dans certains cas.  
  
 Dans Visual C++, une boîte de dialogue vous informe du déplacement du point d'exécution. Vérifiez que le nouvel emplacement est correct avant de poursuivre le débogage. S'il ne l'est pas, utilisez la commande **Définir l'instruction suivante** . Pour plus d’informations, consultez [Définir l’instruction suivante à exécuter](https://msdn.microsoft.com/library/y740d9d3.aspx#BKMK_Set_the_next_statement_to_execute).  
  
##  <a name="BKMK_How_to_work_with_stale_code"></a> Comment utiliser du code périmé  
 Dans certains cas, Modifier & Continuer n'applique pas immédiatement les modifications du code au fichier exécutable, mais peut éventuellement les appliquer ultérieurement si vous poursuivez le débogage. Cela arrive si vous modifiez une fonction qui appelle la fonction actuelle ou si vous ajoutez plus de 64 octets de nouvelles variables à une fonction sur la pile des appels.  
  
 Dans ces cas, le débogueur continue à exécuter le code d’origine jusqu’à ce que les modifications puissent être appliquées. Le code périmé apparaît comme une fenêtre de fichier source temporaire dans une fenêtre source séparée, avec un titre comme `enc25.tmp`. La source modifiée continue à apparaître dans la fenêtre source d'origine. Si vous essayez de modifier le code périmé, un message d'avertissement apparaît.  
  
## <a name="see-also"></a>Voir aussi  
 [Modifications de code prises en charge (C++)](../debugger/supported-code-changes-cpp.md)