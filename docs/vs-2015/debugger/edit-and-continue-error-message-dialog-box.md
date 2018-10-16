---
title: Modifier et continuer, boîte de dialogue erreur Message | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.ENC.SupportedButNotAvaiable
- vs.debug.ENC.CannotEditWhileException
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Edit and Continue Error Message dialog box
ms.assetid: f98c91c0-447a-4533-85b6-87170a0dc4c3
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b6252fbaf67a9a5b4173c0fee3f65607e9cc462
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49227231"
---
# <a name="edit-and-continue-error-message-dialog-box"></a>Message d'erreur de Modifier & Continuer, boîte de dialogue
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette boîte de dialogue s’affiche lorsque vous déboguez dans un langage qui prend en charge Modifier & Continuer, mais **Modifier & Continuer** n’est pas disponible pour le type de modifications du code que vous avez apportées. Le message d'erreur affiché dans la boîte de dialogue fournit une explication plus détaillée. Les raisons pouvant justifier l'affichage de cette boîte de dialogue sont les suivantes :  
  
-   Vous avez essayé de modifier un code managé alors que le débogage non managé était activé. Modifier & Continuer ne fonctionne pas en débogage en mode mixte.  
  
-   Vous avez essayé de modifier le code SQL Server.  
  
-   Vous avez essayé de modifier le code en déboguant un Dr. Dr. Watson.  
  
-   Vous avez essayé de modifier le code après une exception non gérée s’est produite et l’option «**dérouler la pile des appels sur les exceptions non gérées**» n’a été sélectionné.  
  
-   Vous avez essayé de modifier le code pendant le débogage d'une application d'exécution incorporée.  
  
-   Vous avez essayé de modifier le code dans un programme que vous avez attaché à plutôt que de commencer le **déboguer** menu.  
  
-   Vous avez essayé de modifier un code optimisé.  
  
-   Vous avez essayé de modifier du code managé alors que la cible est une application 64 bits. Pour utiliser Modifier & Continuer, vous devez affecter x86 à la cible. (*Projet* **propriétés**, **compiler** onglet, **paramètres avancés du compilateur** paramètre.).  
  
-   Vous avez tenté de modifier le code d'un assembly qui a été modifié pendant le débogage et a été rechargé.  
  
-   Vous avez tenté de modifier le code d'un assembly qui n'a pas été chargé.  
  
-   Vous avez commencé à déboguer une version ancienne de votre application (étant donné que la nouvelle version comporte des erreurs de build).  
  
-   Vous avez tenté de modifier le code d'édition pendant son exécution.  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **OK**  
 Fermez la boîte de dialogue et annulez la tentative de modification précédente.  
  
## <a name="see-also"></a>Voir aussi  
 [Modifications de code prises en charge (C++)](../debugger/supported-code-changes-cpp.md)



