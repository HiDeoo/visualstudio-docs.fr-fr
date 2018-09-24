---
title: 'Comment : enregistrer des classeurs par programmation'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, saving in XML format
- workbooks, saving
- workbooks, saving backup copies
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6fc715518f31031c65667a2480d7e14111105202
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35672717"
---
# <a name="how-to-programmatically-save-workbooks"></a>Comment : enregistrer des classeurs par programmation
  Il existe plusieurs façons d'enregistrer un classeur. Vous pouvez le faire sans modifier le chemin d'accès. Si le classeur n'a pas été enregistré auparavant, vous devez l'enregistrer en spécifiant un chemin d'accès. Sans chemin d'accès explicite, Microsoft Office Excel enregistre le fichier dans le dossier actif avec le nom qui lui a été attribué lors de sa création. Vous pouvez également enregistrer une copie du classeur sans modifier le classeur ouvert en mémoire.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="save-a-workbook-without-changing-the-path"></a>Enregistrer un classeur sans modifier le chemin d’accès  
  
### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>Pour enregistrer un classeur associé à une personnalisation au niveau du document  
  
1.  Appelez la méthode <xref:Microsoft.Office.Tools.Excel.Workbook.Save%2A> de la classe `ThisWorkbook`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#4](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomation#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#4)]  
  
### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>Pour enregistrer le classeur actif dans un complément VSTO  
  
1.  Appelez la méthode <xref:Microsoft.Office.Interop.Excel._Workbook.Save%2A> pour enregistrer le classeur actif. Pour utiliser l'exemple de code suivant, exécutez-le dans la classe `ThisAddIn` dans un projet de complément VSTO pour Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#3](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#3](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#3)]  
  
## <a name="save-a-workbook-with-a-new-path"></a>Enregistrer un classeur avec un nouveau chemin d’accès  
 Vous pouvez enregistrer le classeur spécifié dans un nouvel emplacement ou avec un nouveau nom, en spécifiant éventuellement un format de fichier, un mot de passe, un mode d'accès, etc.  
  
> [!NOTE]  
>  Vous souhaiterez peut-être définir la <xref:Microsoft.Office.Interop.Excel._Application.DisplayAlerts%2A> propriété **False** avant d’enregistrer le classeur avec un nouveau chemin d’accès car l’enregistrement sous certains formats requiert une interaction. Si cette propriété **False** conduit Excel à utiliser toutes les valeurs par défaut.  
  
### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>Pour enregistrer un classeur associé à une personnalisation au niveau du document  
  
1.  Appelez la méthode <xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A> de la classe `ThisWorkbook`. Pour utiliser l'exemple de code suivant, exécutez-le dans la classe `ThisWorkbook`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#5](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomation#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#5)]  
  
### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>Pour enregistrer le classeur actif dans un complément VSTO  
  
1.  Appelez la méthode <xref:Microsoft.Office.Interop.Excel._Workbook.SaveAs%2A> pour enregistrer le classeur actif avec un nouveau chemin d'accès. Pour utiliser l'exemple de code suivant, exécutez-le dans la classe `ThisAddIn` dans un projet de complément VSTO pour Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#4](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#4](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#4)]  
  
## <a name="save-a-copy-of-the-workbook"></a>Enregistrer une copie du classeur  
 Vous pouvez enregistrer une copie du classeur dans un fichier sans modifier le classeur ouvert en mémoire. Cela est utile quand vous souhaitez créer une copie de sauvegarde sans modifier l'emplacement du classeur.  
  
### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>Pour enregistrer un classeur associé à une personnalisation au niveau du document  
  
1.  Appelez la méthode <xref:Microsoft.Office.Tools.Excel.Workbook.SaveCopyAs%2A> de la classe `ThisWorkbook`. Pour utiliser l'exemple de code suivant, exécutez-le dans la classe `ThisWorkbook`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#6](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomation#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#6)]  
  
### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>Pour enregistrer le classeur actif dans un complément VSTO  
  
1.  Appelez la méthode <xref:Microsoft.Office.Interop.Excel._Workbook.SaveCopyAs%2A> pour enregistrer une copie du classeur actif. Pour utiliser l'exemple de code suivant, exécutez-le dans la classe `ThisAddIn` dans un projet de complément VSTO pour Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#5)]  
  
## <a name="robust-programming"></a>Programmation fiable  
 L'annulation interactive d'une quelconque des méthodes qui enregistrent ou copient le classeur génère une erreur d'exécution dans votre code. Par exemple, si votre procédure appelle la <xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A> méthode mais ne pas désactiver les invites d’Excel, et l’utilisateur clique sur **Annuler** lorsque vous y êtes invité, Excel génère une erreur d’exécution.  
  
## <a name="see-also"></a>Voir aussi  
 [Travailler avec des classeurs](../vsto/working-with-workbooks.md)   
 [Élément hôte de classeur](../vsto/workbook-host-item.md)   
 [Comment : fermer des classeurs par programmation](../vsto/how-to-programmatically-close-workbooks.md)   
 [Limitations de programmation des éléments hôtes et contrôles hôtes](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Paramètres optionnels dans les solutions Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Éléments hôtes et la vue d’ensemble des contrôles hôtes](../vsto/host-items-and-host-controls-overview.md)  
  
  