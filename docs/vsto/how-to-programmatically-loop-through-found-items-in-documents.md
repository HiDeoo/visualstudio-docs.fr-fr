---
title: 'Comment : Parcourir par programmation des éléments trouvés dans les documents'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- loops, through found items in documents
- documents [Office development in Visual Studio], searching
- text [Office development in Visual Studio], searching in documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0ff9a85319ac35e051b41ff65ab5b027dc226f44
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35672869"
---
# <a name="how-to-programmatically-loop-through-found-items-in-documents"></a>Comment : Parcourir par programmation des éléments trouvés dans les documents
  La classe <xref:Microsoft.Office.Interop.Word.Find> a une propriété <xref:Microsoft.Office.Interop.Word.Find.Found%2A> , qui retourne **true** chaque fois qu’un élément recherché est trouvé. Vous pouvez exécuter en boucle toutes les instances trouvées dans un <xref:Microsoft.Office.Interop.Word.Range> à l’aide de la méthode <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> .  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-loop-through-found-items"></a>Pour exécuter en boucle les éléments trouvés  
  
1.  Déclarez un objet <xref:Microsoft.Office.Interop.Word.Range> .  
  
     Vous pouvez utiliser l’exemple de code suivant dans une personnalisation au niveau du document.  
  
     [!code-vb[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#79)]
     [!code-csharp[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#79)]  
  
     L'exemple de code suivant peut être utilisé dans un complément VSTO. Cet exemple utilise le document actif.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#79)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#79)]  
  
2.  Utilisez la propriété <xref:Microsoft.Office.Interop.Word.Find.Found%2A> d’une boucle pour rechercher toutes les occurrences de la chaîne dans le document, puis incrémentez une variable entière de 1 chaque fois que la chaîne est trouvée.  
  
     [!code-vb[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#80)]
     [!code-csharp[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#80)]  
  
3.  Affichez le nombre de fois où que la chaîne a été trouvée dans une boîte de message.  
  
     [!code-vb[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#81)]
     [!code-csharp[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#81)]  
  
 Les exemples suivants montrent la méthode complète.  
  
## <a name="document-level-customization-example"></a>Exemple de personnalisation au niveau du document  
  
### <a name="to-loop-through-items-in-a-document-level-customization"></a>Pour exécuter en boucle les éléments d’une personnalisation au niveau du document  
  
1.  L'exemple suivant montre le code complet pour une personnalisation au niveau du document. Pour utiliser ce code, exécutez-le à partir de la classe `ThisDocument` de votre projet.  
  
     [!code-vb[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#78)]  
  
## <a name="vsto-add-in-example"></a>Exemple de complément VSTO  
  
### <a name="to-loop-through-items-in-a-vsto-add-in"></a>Pour parcourir les éléments dans un composant logiciel complément VSTO  
  
1.  L’exemple suivant montre le code complet pour un complément VSTO. Pour utiliser ce code, exécutez-le à partir de la classe `ThisAddIn` de votre projet.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#78)]  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : rechercher par programmation et de remplacer des rext dans des documents](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [Comment : définir par programmation les options de recherche dans Word](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [Comment : définir et sélectionner des plages dans les documents par programmation](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Comment : restaurer des sélections après des recherches par programmation](../vsto/how-to-programmatically-restore-selections-after-searches.md)   
 [Paramètres optionnels dans les solutions Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  