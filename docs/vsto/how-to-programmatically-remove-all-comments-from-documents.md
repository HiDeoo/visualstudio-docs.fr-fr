---
title: 'Comment : supprimer tous les commentaires des documents par programmation'
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], removing comments
- comments, removing from documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ee30cb7d4083adfff18261e3267dea1d8a96626f
ms.sourcegitcommit: 9d2829dc30b6917e89762d602022915f1ca49089
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91584818"
---
# <a name="how-to-programmatically-remove-all-comments-from-documents"></a>Comment : supprimer tous les commentaires des documents par programmation
  Utilisez la méthode `DeleteAllComments` pour supprimer tous les commentaires d’un document Microsoft Office Word.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-remove-all-comments-from-a-document-that-is-part-of-a-document-level-customization"></a>Pour supprimer tous les commentaires d’un document qui fait partie d’une personnalisation au niveau du document

1. Appelez la méthode <xref:Microsoft.Office.Tools.Word.Document.DeleteAllComments%2A> de la classe `ThisDocument` dans votre projet. Pour utiliser cet exemple de code, exécutez-le à partir de la classe `ThisDocument` .

     [!code-vb[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#119)]

## <a name="to-remove-all-comments-from-a-document-by-using-a-vsto-add-in"></a>Pour supprimer tous les commentaires d’un document à l’aide d’un complément VSTO

1. Appelez la méthode <xref:Microsoft.Office.Interop.Word._Document.DeleteAllComments%2A> du <xref:Microsoft.Office.Interop.Word.Document> à partir duquel vous souhaitez supprimer les commentaires.

     L’exemple de code suivant supprime tous les commentaires du document actif. Pour utiliser cet exemple de code, exécutez-le à partir de la classe `ThisAddIn` de votre projet.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#119)]

## <a name="see-also"></a>Voir aussi
- [Comment : ajouter des commentaires à du texte dans des documents par programmation](../vsto/how-to-programmatically-add-comments-to-text-in-documents.md)
- [Élément hôte de document](../vsto/document-host-item.md)
