---
title: 'Comment : utiliser par programmation les boîtes de dialogue Word en mode masqué'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden dialog boxes
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, hidden mode in Word
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d5b123f1b58e61dffc64b5df912092edfd3fbf53
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35672812"
---
# <a name="how-to-programmatically-use-word-dialog-boxes-in-hidden-mode"></a>Comment : utiliser par programmation les boîtes de dialogue Word en mode masqué
  Vous pouvez effectuer des opérations complexes avec un appel de méthode en appelant les boîtes de dialogue intégrées dans Microsoft Office Word sans les afficher à l’utilisateur. Ce faire, vous pouvez utiliser la <xref:Microsoft.Office.Interop.Word.Dialog.Execute%2A> méthode de la <xref:Microsoft.Office.Interop.Word.Dialog> objet sans appeler le <xref:Microsoft.Office.Interop.Word.Dialog.Display%2A> (méthode).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="examples"></a>Exemples  
 Les exemples de code suivants montrent comment utiliser le **mise en Page** boîte de dialogue en mode masqué pour définir plusieurs propriétés de mise en page sans entrée utilisateur. Les exemples utilisent un <xref:Microsoft.Office.Interop.Word.Dialog> objet utilisé pour configurer une taille de page personnalisée. Les paramètres spécifiques pour la mise en page, telles que la marge supérieure, marge inférieure et ainsi de suite, sont disponibles en tant que propriétés à liaison tardive de la <xref:Microsoft.Office.Interop.Word.Dialog> objet. Ces propriétés sont créées dynamiquement par Word lors de l’exécution.  
  
 L’exemple suivant montre comment effectuer cette tâche dans les projets Visual Basic où **Option Strict** est désactivé et dans les projets Visual c# qui ciblent le [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Dans ces projets, vous pouvez utiliser les fonctions de liaison tardive dans les compilateurs Visual Basic et Visual c#. Pour utiliser cet exemple, exécutez-le à partir de la `ThisDocument` ou `ThisAddIn` classe dans votre projet.  
  
 [!code-vb[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#123)]
 [!code-csharp[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#123)]  
  
 L’exemple suivant montre comment effectuer cette tâche dans les projets Visual Basic où **Option Strict** se trouve sur. Dans ces projets, vous devez utiliser la réflexion pour accéder aux propriétés à liaison tardive. Pour utiliser cet exemple, exécutez-le à partir de la `ThisDocument` ou `ThisAddIn` classe dans votre projet.  
  
 [!code-vb[Trin_VstcoreWordAutomation#104](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#104)]  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : utiliser par programmation les boîtes de dialogue intégrées dans Word](../vsto/how-to-programmatically-use-built-in-dialog-boxes-in-word.md)   
 [Vue d’ensemble du modèle d’objet Word](../vsto/word-object-model-overview.md)   
 [Liaison tardive dans les solutions Office](../vsto/late-binding-in-office-solutions.md)   
 [Réflexion (C#)](/dotnet/csharp/programming-guide/concepts/reflection)  
 [Réflexion (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)  
  
  