---
title: 'Comment : créer des documents par programmation'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- templates [Office development in Visual Studio], custom document
- Word [Office development in Visual Studio], creating documents
- documents [Office development in Visual Studio], creating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8e82c5ca62c407481b73de9394c584c3039a8f57
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85545988"
---
# <a name="how-to-programmatically-create-new-documents"></a>Comment : créer des documents par programmation
  Quand vous créez un document par programmation, le nouveau document est un objet <xref:Microsoft.Office.Interop.Word.Document>natif. Cet objet ne possède pas les fonctionnalités de liaison de données et les événements supplémentaires d’un élément hôte <xref:Microsoft.Office.Tools.Word.Document>. Pour plus d’informations, consultez [limitations de programmation des éléments hôtes et des contrôles hôtes](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 Quand vous développez un projet au niveau du document, vous ne pouvez pas ajouter par programmation d'éléments hôtes <xref:Microsoft.Office.Tools.Word.Document> à votre projet. Dans un projet de complément VSTO, vous pouvez convertir tout objet <xref:Microsoft.Office.Interop.Word.Document> en un élément hôte <xref:Microsoft.Office.Tools.Word.Document> au moment de l’exécution. Pour plus d’informations, consultez [extension de documents Word et de classeurs Excel dans des compléments VSTO au moment](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)de l’exécution.

## <a name="to-create-a-new-document-based-on-the-normal-template"></a>Pour créer un nouveau document basé sur le modèle Normal

- Utilisez la méthode <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> de la collection <xref:Microsoft.Office.Interop.Word.Documents> pour créer un nouveau document basé sur le modèle Normal. Pour utiliser cet exemple de code, exécutez-le à partir de la classe `ThisDocument` ou `ThisAddIn` de votre projet.

     [!code-vb[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#1)]
     [!code-csharp[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#1)]

## <a name="use-custom-templates"></a>Utiliser des modèles personnalisés
 La <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> méthode a un argument *template* facultatif pour créer un nouveau document basé sur un modèle autre que le modèle normal. Vous devez fournir le nom de fichier et le chemin d'accès complet du modèle.

### <a name="to-create-a-new-document-based-on-a-custom-template"></a>Pour créer un nouveau document basé sur un modèle personnalisé

- Appelez la méthode <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> de la collection <xref:Microsoft.Office.Interop.Word.Documents> et spécifiez le chemin d'accès au modèle. Pour utiliser cet exemple de code, exécutez-le à partir de la classe `ThisDocument` ou `ThisAddIn` de votre projet.

     [!code-vb[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#2)]
     [!code-csharp[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#2)]

## <a name="see-also"></a>Voir aussi
- [Comment : ouvrir des documents existants par programmation](../vsto/how-to-programmatically-open-existing-documents.md)
- [Vue d’ensemble des éléments hôtes et des contrôles hôtes](../vsto/host-items-and-host-controls-overview.md)
- [Limitations de programmation des éléments hôtes et des contrôles hôtes](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Paramètres facultatifs dans les solutions Office](../vsto/optional-parameters-in-office-solutions.md)
