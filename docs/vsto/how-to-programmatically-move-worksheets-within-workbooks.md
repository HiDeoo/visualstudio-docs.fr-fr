---
title: 'Comment : déplacer des feuilles de calcul dans des classeurs par programmation'
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, moving
- workbooks, moving worksheets in
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fca9d466f3af8a0dd3191f2845613fc9b43ec549
ms.sourcegitcommit: 9d2829dc30b6917e89762d602022915f1ca49089
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91584215"
---
# <a name="how-to-programmatically-move-worksheets-within-workbooks"></a>Comment : déplacer des feuilles de calcul dans des classeurs par programmation
  Vous pouvez modifier par programmation la position des feuilles de calcul les unes par rapport aux autres dans un classeur. Si vous ne spécifiez pas d’emplacement pour la feuille déplacée, Excel crée un classeur pour le contenir.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="to-move-a-worksheet-in-a-document-level-customization"></a>Pour déplacer une feuille de calcul dans une personnalisation au niveau du document

1. Affectez le nombre total de feuilles dans le classeur à une variable, puis déplacez la première feuille de calcul pour qu’elle devienne la dernière.

     [!code-csharp[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#24)]
     [!code-vb[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#24)]

## <a name="to-move-a-worksheet-in-a-vsto-add-in"></a>Pour déplacer une feuille de calcul dans un complément VSTO

1. Affectez le nombre total de feuilles dans le classeur à une variable, puis déplacez la première feuille de calcul pour qu’elle devienne la dernière.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#16)]

## <a name="see-also"></a>Voir aussi
- [Utiliser des feuilles de calcul](../vsto/working-with-worksheets.md)
- [Comment : masquer des feuilles de calcul par programmation](../vsto/how-to-programmatically-hide-worksheets.md)
- [Comment : supprimer des feuilles de calcul à partir de classeurs par programmation](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)
- [Comment : protéger des feuilles de calcul par programmation](../vsto/how-to-programmatically-protect-worksheets.md)
- [Accès global aux objets dans les projets Office](../vsto/global-access-to-objects-in-office-projects.md)
