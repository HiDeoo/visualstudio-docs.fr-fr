---
title: 'Comment : ajouter des parties XML personnalisées aux personnalisations au niveau du document'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document-level customizations [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- custom XML parts [Office development in Visual Studio], adding
- documents [Office development in Visual Studio], custom XML parts
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0472ad001dee595f1f8edb77d7a70f1eefb0c024
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35673412"
---
# <a name="how-to-add-custom-xml-parts-to-document-level-customizations"></a>Comment : ajouter des parties XML personnalisées aux personnalisations au niveau du document
  Vous pouvez stocker des données XML dans un classeur Microsoft Office Excel ou un document Microsoft Office Word en créant une partie XML personnalisée dans une personnalisation au niveau du document. Pour plus d’informations, consultez [vue d’ensemble des parties XML personnalisées](../vsto/custom-xml-parts-overview.md).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
> [!NOTE]  
>  Visual Studio ne fournit pas de projets au niveau du document pour Microsoft Office PowerPoint. Pour plus d’informations sur l’ajout d’une partie XML personnalisée à une présentation PowerPoint en utilisant un complément, VSTO, consultez [Comment : ajouter des parties XML personnalisées à des documents à l’aide des Compléments VSTO](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md).  
  
### <a name="to-add-a-custom-xml-part-to-an-excel-workbook"></a>Pour ajouter une partie XML personnalisée à un classeur Excel  
  
1.  Ajoutez un nouvel objet <xref:Microsoft.Office.Core.CustomXMLPart> à la collection <xref:Microsoft.Office.Core.CustomXMLParts> figurant dans le classeur. <xref:Microsoft.Office.Core.CustomXMLPart> contient la chaîne XML que vous souhaitez stocker dans le classeur.  
  
     [!code-csharp[Trin_AddCustomXmlPartExcelDocLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartExcelDocLevel/ThisWorkbook.cs#1)]
     [!code-vb[Trin_AddCustomXmlPartExcelDocLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartExcelDocLevel/ThisWorkbook.vb#1)]  
  
2.  Ajoutez la méthode `AddCustomXmlPartToWorkbook` à la classe `ThisWorkbook` dans un projet au niveau du document pour Excel.  
  
3.  Appelez cette méthode à partir d'un autre code dans votre projet. Par exemple, pour créer la partie XML personnalisée quand l’utilisateur ouvre le classeur, appelez la méthode à partir du gestionnaire d’événements `ThisWorkbook_Startup` .  
  
### <a name="to-add-a-custom-xml-part-to-a-word-document"></a>Pour ajouter une partie XML personnalisée à un document Word  
  
1.  Ajoutez un nouvel objet <xref:Microsoft.Office.Core.CustomXMLPart> à la collection <xref:Microsoft.Office.Core.CustomXMLParts> figurant dans le document. <xref:Microsoft.Office.Core.CustomXMLPart> contient la chaîne XML que vous souhaitez stocker dans le document.  
  
     [!code-vb[Trin_AddCustomXmlPartWordDocLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartWordDocLevel/ThisDocument.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartWordDocLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartWordDocLevel/ThisDocument.cs#1)]  
  
2.  Ajoutez la méthode `AddCustomXmlPartToDocument` à la classe `ThisDocument` dans un projet au niveau du document pour Word.  
  
3.  Appelez cette méthode à partir d'un autre code dans votre projet. Par exemple, pour créer la partie XML personnalisée quand l’utilisateur ouvre le document, appelez la méthode à partir du gestionnaire d’événements `ThisDocument_Startup` .  
  
## <a name="robust-programming"></a>Programmation fiable  
 Par souci de simplicité, cet exemple utilise une chaîne XML définie comme variable locale dans la méthode. En règle générale, vous devez obtenir le code XML auprès d'une source externe, telle qu'un fichier ou une base de données.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de parties XML personnalisée](../vsto/custom-xml-parts-overview.md)   
 [Comment : ajouter des parties XML personnalisées à des documents à l’aide de compléments VSTO](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)  
  