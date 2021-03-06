---
title: 'Comment : exécuter des calculs Excel par programmation'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, running calculations
- calculations, running in Excel
- Excel [Office development in Visual Studio], running calculations programmatically
- workbooks, running calculations
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a02e86864065d2c626de2f6e7fea7528554f1391
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85547379"
---
# <a name="how-to-programmatically-run-excel-calculations"></a>Comment : exécuter des calculs Excel par programmation
  Vous utilisez un processus similaire pour exécuter des calculs dans un <xref:Microsoft.Office.Tools.Excel.NamedRange> contrôle ou un objet de plage Excel natif.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="run-calculations-in-a-namedrange-control"></a>Exécuter des calculs dans un contrôle NamedRange
 L’exemple suivant crée un <xref:Microsoft.Office.Tools.Excel.NamedRange> à la cellule a1, puis calcule la cellule. Ce code doit être placé dans une classe Sheet et non pas dans la classe `ThisWorkbook` .

### <a name="to-run-calculations-in-a-namedrange-control"></a>Pour exécuter des calculs dans un contrôle NamedRange

1. Créez la plage nommée.

     [!code-csharp[Trin_VstcoreExcelAutomation#75](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#75)]
     [!code-vb[Trin_VstcoreExcelAutomation#75](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#75)]

2. Appelez la <xref:Microsoft.Office.Tools.Excel.NamedRange.Calculate%2A> méthode de la plage spécifiée.

     [!code-csharp[Trin_VstcoreExcelAutomation#76](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#76)]
     [!code-vb[Trin_VstcoreExcelAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#76)]

## <a name="run-calculations-in-a-native-excel-range"></a>Exécuter des calculs dans une plage Excel Native

### <a name="to-run-calculations-in-a-native-excel-range"></a>Pour exécuter des calculs dans une plage Excel Native

1. Créez la plage nommée.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#30](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#30)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#30](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#30)]

2. Appelez la <xref:Microsoft.Office.Interop.Excel.Range.Calculate%2A> méthode de la plage spécifiée.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#31](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#31](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#31)]

## <a name="see-also"></a>Voir aussi
- [Utiliser des plages](../vsto/working-with-ranges.md)
- [NamedRange, contrôle](../vsto/namedrange-control.md)
- [Paramètres facultatifs dans les solutions Office](../vsto/optional-parameters-in-office-solutions.md)
