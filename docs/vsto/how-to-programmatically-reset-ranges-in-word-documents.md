---
title: 'Comment : réinitialiser par programmation des plages dans des documents Word'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], resetting ranges
- ranges, resetting in documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0da42b0e6ad6f8761e474292532728beb3987c57
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35671157"
---
# <a name="how-to-programmatically-reset-ranges-in-word-documents"></a>Comment : réinitialiser par programmation des plages dans des documents Word
  Utilisez la méthode <xref:Microsoft.Office.Interop.Word.Range.SetRange%2A> pour redimensionner une plage existante dans un document Microsoft Office Word.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-reset-an-existing-range"></a>Pour réinitialiser une plage existante  
  
1.  Définissez une plage initiale commençant par les sept premiers caractères du document.  
  
     Vous pouvez utiliser l’exemple de code suivant dans une personnalisation au niveau du document.  
  
     [!code-vb[Trin_VstcoreWordAutomation#43](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#43)]
     [!code-csharp[Trin_VstcoreWordAutomation#43](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#43)]  
  
     L'exemple de code suivant peut être utilisé dans un complément VSTO. Ce code utilise le document actif.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#43](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#43)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#43](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#43)]  
  
2.  Utilisez <xref:Microsoft.Office.Interop.Word.Range.SetRange%2A> pour commencer la plage au niveau de la deuxième phrase et la terminer à la fin de la cinquième phrase.  
  
     [!code-vb[Trin_VstcoreWordAutomation#44](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#44)]
     [!code-csharp[Trin_VstcoreWordAutomation#44](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#44)]  
  
## <a name="document-level-customization-example"></a>Exemple de personnalisation au niveau du document  
  
### <a name="to-reset-an-existing-range-in-a-document-level-customization"></a>Pour réinitialiser une plage existante dans une personnalisation au niveau du document  
  
1.  L’exemple suivant montre le code complet pour une personnalisation au niveau du document. Pour utiliser ce code, exécutez-le à partir de la classe `ThisDocument` de votre projet.  
  
     [!code-vb[Trin_VstcoreWordAutomation#42](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#42)]
     [!code-csharp[Trin_VstcoreWordAutomation#42](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#42)]  
  
## <a name="vsto-add-in-example"></a>Exemple de complément VSTO  
  
### <a name="to-reset-an-existing-range-in-a-vsto-add-in"></a>Pour réinitialiser une plage existante dans un complément, VSTO  
  
1.  L’exemple suivant montre un exemple complet pour un composant logiciel complément VSTO. Pour utiliser ce code, exécutez-le à partir de la classe `ThisAddIn` de votre projet.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#42](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#42)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#42](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#42)]  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : étendre des plages dans des documents par programmation](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Comment : définir et sélectionner des plages dans les documents par programmation](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Comment : récupérer par programme des caractères de début et de fin dans les plages](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Comment : réduire des plages ou des sélections dans des documents par programmation](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)  
  
  