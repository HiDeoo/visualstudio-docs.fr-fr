---
title: 'Comment : remplir par programmation des tableaux Word avec des propriétés de document'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document properties, inserting in Word tables
- documents [Office development in Visual Studio], document properties
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b996a8d66ceb4947d35dbbba7323b70c21c065fc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49900395"
---
# <a name="how-to-programmatically-populate-word-tables-with-document-properties"></a>Comment : remplir par programmation des tableaux Word avec des propriétés de document
  L'exemple suivant crée un tableau Microsoft Office Word en haut du document et le remplit avec les propriétés du document hôte.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="populate-tables-in-a-document-level-customization"></a>Remplir les tables dans une personnalisation au niveau du document  
  
### <a name="to-create-a-table-and-populate-it-with-document-properties"></a>Pour créer un tableau et le remplir avec des propriétés de document  
  
1. Définissez la plage en haut du document.  
  
    [!code-vb[Trin_VstcoreWordAutomation#90](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#90)]
    [!code-csharp[Trin_VstcoreWordAutomation#90](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#90)]  
  
2. Insérez un titre pour le tableau et insérez des marques de paragraphe.  
  
    [!code-vb[Trin_VstcoreWordAutomation#91](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#91)]
    [!code-csharp[Trin_VstcoreWordAutomation#91](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#91)]  
  
3. Ajoutez le tableau au document au niveau de la plage.  
  
    [!code-vb[Trin_VstcoreWordAutomation#92](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#92)]
    [!code-csharp[Trin_VstcoreWordAutomation#92](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#92)]  
  
4. Mettez en forme le tableau et appliquez un style.  
  
    [!code-vb[Trin_VstcoreWordAutomation#93](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#93)]
    [!code-csharp[Trin_VstcoreWordAutomation#93](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#93)]  
  
5. Insérez les propriétés de document dans les cellules.  
  
    [!code-vb[Trin_VstcoreWordAutomation#94](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#94)]
    [!code-csharp[Trin_VstcoreWordAutomation#94](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#94)]  
  
   L'exemple suivant montre la procédure complète. Pour utiliser ce code, exécutez-le à partir de la classe `ThisDocument` de votre projet.  
  
   [!code-vb[Trin_VstcoreWordAutomation#89](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#89)]
   [!code-csharp[Trin_VstcoreWordAutomation#89](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#89)]  
  
## <a name="populate-tables-in-a-vsto-add-in"></a>Remplir les tables dans un composant logiciel complément VSTO  
  
### <a name="to-create-a-table-and-populate-it-with-document-properties"></a>Pour créer un tableau et le remplir avec des propriétés de document  
  
1. Définissez la plage en haut du document.  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#90](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#90)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#90](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#90)]  
  
2. Insérez un titre pour le tableau et insérez des marques de paragraphe.  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#91](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#91)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#91](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#91)]  
  
3. Ajoutez le tableau au document au niveau de la plage.  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#92](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#92)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#92](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#92)]  
  
4. Mettez en forme le tableau et appliquez un style.  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#93](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#93)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#93](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#93)]  
  
5. Insérez les propriétés de document dans les cellules.  
  
    [!code-vb[Trin_VstcoreWordAutomationAddIn#94](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#94)]
    [!code-csharp[Trin_VstcoreWordAutomationAddIn#94](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#94)]  
  
   L'exemple suivant montre la procédure complète. Pour utiliser ce code, exécutez-le à partir de la classe `ThisAddIn` de votre projet.  
  
   [!code-vb[Trin_VstcoreWordAutomationAddIn#89](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#89)]
   [!code-csharp[Trin_VstcoreWordAutomationAddIn#89](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#89)]  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : créer des tableaux Word par programmation](../vsto/how-to-programmatically-create-word-tables.md)   
 [Comment : ajouter texte et mise en forme aux cellules des tableaux Word par programmation](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)   
 [Comment : ajouter par programmation des lignes et colonnes à des tableaux Word](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)   
 [Paramètres optionnels dans les solutions Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  