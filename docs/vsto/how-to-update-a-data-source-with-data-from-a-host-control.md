---
title: 'Comment : mettre à jour une source de données avec des données à partir d’un contrôle hôte'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], data source updates
- data [Office development in Visual Studio], updating a data source from a document
- host controls [Office development in Visual Studio], data source updates
- Office documents [Office development in Visual Studio, data sources
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 23fbe0a7563dbb1ebb3832dbe5c340e67dacac72
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35673644"
---
# <a name="how-to-update-a-data-source-with-data-from-a-host-control"></a>Comment : mettre à jour une source de données avec des données à partir d’un contrôle hôte
  Vous pouvez lier un contrôle hôte à une source de données et mettre à jour la source de données avec les modifications apportées aux données dans le contrôle. Deux étapes principales constituent ce processus :  
  
1.  Mise à jour de la source de données en mémoire avec les données modifiées dans le contrôle. En général, la source de données en mémoire est un <xref:System.Data.DataSet>, un <xref:System.Data.DataTable>ou un objet de données.  
  
2.  Mise à jour de la base de données avec les données modifiées dans la source de données en mémoire. Ceci s’applique uniquement si la source de données est connectée à une base de données principale, par exemple une base de données SQL Server ou Microsoft Office Access.  
  
 Pour plus d’informations sur la liaison de données et des contrôles hôtes, consultez [éléments hôtes et héberger de vue d’ensemble des contrôles](../vsto/host-items-and-host-controls-overview.md) et [lier des données aux contrôles dans les solutions Office](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## <a name="update-the-in-memory-data-source"></a>Mettre à jour la source de données en mémoire  
 Par défaut, les contrôles hôtes qui autorisent la liaison de données simple (comme les contrôles de contenu dans un document Word ou un contrôle de plage nommée dans une feuille de calcul Excel) n’enregistrent pas les modifications de données apportées à la source de données en mémoire. Autrement dit, quand un utilisateur final modifie une valeur dans un contrôle hôte, puis quitte le contrôle, la nouvelle valeur du contrôle n’est pas enregistrée automatiquement dans la source de données.  
  
 Pour enregistrer les données dans la source de données, vous pouvez écrire du code qui met à jour la source de données en réponse à un événement spécifique lors de l’exécution, ou vous pouvez configurer le contrôle pour automatiquement mettre à jour la source de données lorsque la valeur du contrôle change.  
  
 Vous n’avez pas besoin d’enregistrer les modifications <xref:Microsoft.Office.Tools.Excel.ListObject> apportées à la source de données en mémoire. Quand vous liez un contrôle <xref:Microsoft.Office.Tools.Excel.ListObject> à des données, le contrôle <xref:Microsoft.Office.Tools.Excel.ListObject> enregistre automatiquement les modifications dans la source de données en mémoire sans que du code supplémentaire soit nécessaire.  
  
### <a name="to-update-the-in-memory-data-source-at-runtime"></a>Pour mettre à jour la source de données en mémoire lors de l’exécution  
  
-   Appelez la méthode <xref:System.Windows.Forms.Binding.WriteValue%2A> de l’objet <xref:System.Windows.Forms.Binding> qui lie le contrôle à la source de données.  
  
     L’exemple suivant enregistre dans la source de données les modifications apportées à un contrôle <xref:Microsoft.Office.Tools.Excel.NamedRange> dans une feuille de calcul Excel. Cet exemple part du principe que vous avez un contrôle <xref:Microsoft.Office.Tools.Excel.NamedRange> nommé `namedRange1` , dont la propriété <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> est liée à un champ dans une source de données.  
  
     [!code-csharp[Trin_VstcoreDataExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreDataExcel#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#1)]  
  
### <a name="automatically-update-the-in-memory-data-source"></a>Mettre à jour automatiquement la source de données en mémoire  
 Vous pouvez également configurer un contrôle pour qu’il mette automatiquement à jour la source de données en mémoire. Dans un projet au niveau du document, vous pouvez pour cela utiliser du code ou le concepteur. Dans un projet de complément VSTO, vous devez utiliser le code.  
  
#### <a name="to-set-a-control-to-automatically-update-the-in-memory-data-source-by-using-code"></a>Pour configurer un contrôle pour qu’il mette automatiquement à jour la source de données en mémoire à l’aide de code  
  
1.  Utiliser le mode System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged de la <xref:System.Windows.Forms.Binding> objet qui lie le contrôle à la source de données. Il existe deux options de mise à jour de la source de données :  
  
    -   Pour mettre à jour la source de données lorsque le contrôle est validé, définissez cette propriété sur System.Windows.Forms.DataSourceUpdateMode.OnValidation.  
  
    -   Pour mettre à jour la source de données lorsque la valeur de la propriété liée aux données du contrôle change, définissez cette propriété sur System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged.  
  
        > [!NOTE]  
        >  L’option System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged ne s’applique pas aux contrôles hôtes Word, car Word ne notifications pas offre document ou de modification du contrôle. Toutefois, vous pouvez utiliser cette option pour les contrôles Windows Forms sur les documents Word.  
  
     L’exemple suivant configure un contrôle <xref:Microsoft.Office.Tools.Excel.NamedRange> pour mettre automatiquement à jour la source de données quand la valeur du contrôle change. Cet exemple part du principe que vous avez un contrôle <xref:Microsoft.Office.Tools.Excel.NamedRange> nommé `namedRange1` , dont la propriété <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> est liée à un champ dans une source de données.  
  
     [!code-csharp[Trin_VstcoreDataExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#19)]
     [!code-vb[Trin_VstcoreDataExcel#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#19)]  
  
#### <a name="to-set-a-control-to-automatically-update-the-in-memory-data-source-by-using-the-designer"></a>Pour configurer un contrôle pour qu’il mette automatiquement à jour la source de données en mémoire à l’aide du concepteur  
  
1.  Dans Visual Studio, ouvrez le document Word ou le classeur Excel dans le concepteur.  
  
2.  Cliquez sur le contrôle qui doit mettre à jour la source de données automatiquement.  
  
3.  Dans la fenêtre **Propriétés** , développez la propriété **(DataBindings)** .  
  
4.  À côté du **(Avancé)** propriété, cliquez sur le bouton de sélection (![d’écran de VisualStudioEllipsesButton](../vsto/media/vbellipsesbutton.png "d’écran de VisualStudioEllipsesButton")).  
  
5.  Dans la boîte de dialogue **Mise en forme et liaison avancée** , cliquez sur la liste déroulante **Mode de mise à jour de la source de données** et sélectionnez l’une des valeurs suivantes :  
  
    -   Pour mettre à jour la source de données quand le contrôle est validé, sélectionnez **OnValidation**.  
  
    -   Pour mettre à jour la source de données quand la valeur de la propriété liée aux données du contrôle change, sélectionnez **OnPropertyChanged**.  
  
        > [!NOTE]  
        >  L’option **OnPropertyChanged** ne s’applique pas aux contrôles hôtes Word, car Word n’offre pas de notifications de modification du document ou du contrôle. Toutefois, vous pouvez utiliser cette option pour les contrôles Windows Forms sur les documents Word.  
  
6.  Fermez la boîte de dialogue **Mise en forme et liaison avancée** .  
  
## <a name="update-the-database"></a>Mettre à jour de la base de données  
 Si la source de données en mémoire est associée à une base de données, vous devez mettre celle-ci à jour avec les modifications apportées à la source de données. Pour plus d’informations sur la mise à jour une base de données, consultez [enregistrer les données dans la base de données](../data-tools/save-data-back-to-the-database.md) et [mettre à jour des données à l’aide d’un TableAdapter](../data-tools/update-data-by-using-a-tableadapter.md) .  
  
### <a name="to-update-the-database"></a>Pour mettre à jour la base de données  
  
1.  Appelez la méthode <xref:System.Windows.Forms.BindingSource.EndEdit%2A> du <xref:System.Windows.Forms.BindingSource> pour le contrôle.  
  
     Le <xref:System.Windows.Forms.BindingSource> est généré automatiquement quand vous ajoutez un contrôle lié aux données à un document ou à un classeur au moment du design. Le <xref:System.Windows.Forms.BindingSource> connecte le contrôle au dataset typé dans votre projet. Pour plus d’informations, consultez [vue d’ensemble du composant BindingSource](/dotnet/framework/winforms/controls/bindingsource-component-overview).  
  
     L’exemple de code suivant part du principe que votre projet contient un <xref:System.Windows.Forms.BindingSource> nommé `customersBindingSource`.  
  
     [!code-csharp[Trin_VstcoreDataExcel#20](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#20)]
     [!code-vb[Trin_VstcoreDataExcel#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#20)]  
  
2.  Appelez le `Update` méthode du TableAdapter généré dans votre projet.  
  
     Le TableAdapter est généré automatiquement lorsque vous ajoutez un contrôle lié aux données à un document ou classeur au moment du design. Le TableAdapter connecte le dataset typé dans votre projet à la base de données. Pour plus d’informations, consultez [vue d’ensemble de TableAdapter](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).  
  
     L’exemple de code suivant suppose que vous disposez d’une connexion à la table Customers dans la base de données Northwind, et que votre projet contient un TableAdapter nommé `customersTableAdapter` et un dataset typé nommé `northwindDataSet`.  
  
     [!code-csharp[Trin_VstcoreDataExcel#21](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#21)]
     [!code-vb[Trin_VstcoreDataExcel#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#21)]  
  
## <a name="see-also"></a>Voir aussi  
 [Lier des données aux contrôles dans les solutions Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Enregistrer les données dans la base de données](../data-tools/save-data-back-to-the-database.md)    
 [Mettre à jour des données à l’aide d’un TableAdapter](../data-tools/update-data-by-using-a-tableadapter.md)    
 [Comment : parcourir les enregistrements de base de données dans une feuille de calcul](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)   
 [Comment : remplir des feuilles de calcul avec des données à partir d’une base de données](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [Comment : remplir des documents avec des données à partir d’objets](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [Comment : remplir des documents avec des données à partir d’une base de données](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Comment : remplir des documents avec des données à partir des services](../vsto/how-to-populate-documents-with-data-from-services.md)  
  
  