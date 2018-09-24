---
title: 'Procédure pas à pas : Créer un modèle à l’aide de contrôles de contenu'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- building blocks [Office development in Visual Studio]
- Word [Office development in Visual Studio], creating documents
- content controls [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0f49e2e9e23f19a4346080b0e59435128e33849d
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35672861"
---
# <a name="walkthrough-create-a-template-by-using-content-controls"></a>Procédure pas à pas : Créer un modèle à l’aide de contrôles de contenu
  Cette procédure pas à pas montre comment créer une personnalisation au niveau du document qui utilise des contrôles de contenu pour créer un contenu structuré et réutilisable dans un modèle Microsoft Office Word.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Word permet de créer une collection de parties de document réutilisables, nommé *blocs de construction*. Cette procédure pas à pas montre comment créer deux tableaux en tant que blocs de construction. Chaque tableau contient plusieurs contrôles de contenu qui peuvent contenir différents types de contenu, tels que du texte brut ou des dates. L'un des tableaux contient des informations sur un employé, et l'autre contient des commentaires des clients.  
  
 Après avoir créé un document à partir du modèle, vous pouvez ajouter l'un de ces tableaux dans le document en utilisant plusieurs objets <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> qui affichent les blocs de construction disponibles dans le modèle.  
  
 Cette procédure pas à pas décrit les tâches suivantes :  
  
-   Création de tableaux contenant des contrôles de contenu dans un modèle Word au moment du design  
  
-   Remplissage par programmation d'un contrôle de contenu de type zone de liste modifiable et d'un contrôle de contenu de type liste déroulante  
  
-   Protection d'un tableau spécifié contre toute modification  
  
-   Ajout de tableaux à la collection de blocs de construction d'un modèle  
  
-   Création d'un contrôle de contenu affichant les blocs de construction disponibles dans le modèle  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Prérequis  
 Pour exécuter cette procédure pas à pas, vous devez disposer des composants suivants :  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word.  
  
## <a name="create-a-new-word-template-project"></a>Créez un projet de modèle Word  
 Créez un modèle Word pour que les utilisateurs puissent créer aisément leurs propres copies.  
  
### <a name="to-create-a-new-word-template-project"></a>Pour créer un projet de modèle Word  
  
1.  Créer un projet de modèle Word portant le nom **MonModèleDeBlocDeConstruction**. Dans l'Assistant, créez un nouveau document dans la solution. Pour plus d’informations, consultez [Comment : les projets Office de créer dans Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Ouvre le nouveau modèle Word dans le concepteur et ajoute le **MonModèleDeBlocDeConstruction** projet **l’Explorateur de solutions**.  
  
## <a name="create-the-employee-table"></a>Créer la table employee  
 Créez un tableau contenant quatre types différents de contrôles de contenu, dans lequel l'utilisateur peut entrer des informations sur un employé.  
  
### <a name="to-create-the-employee-table"></a>Pour créer le tableau Employé  
  
1.  Dans le modèle Word hébergé dans le [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer, dans le ruban, cliquez sur le **insérer** onglet.  
  
2.  Dans le **Tables** de groupe, cliquez sur **Table**et insérez un tableau comportant deux colonnes et quatre lignes.  
  
3.  Complétez la première colonne pour obtenir une colonne similaire à ceci :  
  
    ||  
    |-|  
    |**Nom de l’employé**|  
    |**Date d’embauche**|  
    |**Titre**|  
    |**Image**|  
  
4.  Cliquez dans la première cellule de la deuxième colonne (à côté **nom de l’employé**).  
  
5.  Dans le ruban, cliquez sur l'onglet **Développeur** .  
  
    > [!NOTE]  
    >  Si l'onglet **Développeur** n'est pas visible, vous devez tout d'abord l'afficher. Pour plus d’informations, consultez [Comment : afficher l’onglet Développeur sur le ruban](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
6.  Dans le **contrôles** de groupe, cliquez sur le **texte** bouton ![PlainTextContentControl](../vsto/media/plaintextcontrol.gif "PlainTextContentControl") pour ajouter un <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>à la première cellule.  
  
7.  Cliquez sur la deuxième cellule de la deuxième colonne (à côté **Date d’embauche**).  
  
8.  Dans le **contrôles** de groupe, cliquez sur le **sélecteur de dates** bouton ![DatePickerContentControl](../vsto/media/datepicker.gif "DatePickerContentControl") pour ajouter un <xref:Microsoft.Office.Tools.Word.DatePickerContentControl> dans la deuxième cellule.  
  
9. Cliquez sur la troisième cellule de la deuxième colonne (à côté **titre**).  
  
10. Dans le **contrôles** de groupe, cliquez sur le **zone de liste déroulante** bouton ![ComboBoxContentControl](../vsto/media/combobox.gif "ComboBoxContentControl") pour ajouter un <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl>dans la troisième cellule.  
  
11. Cliquez sur la dernière cellule dans la deuxième colonne (à côté **image**).  
  
12. Dans le **contrôles** de groupe, cliquez sur le **contrôle de contenu d’image** bouton ![PictureContentControl](../vsto/media/pictcontentcontrol.gif "PictureContentControl") pour ajouter un <xref:Microsoft.Office.Tools.Word.PictureContentControl> jusqu'à la dernière cellule.  
  
## <a name="create-the-customer-feedback-table"></a>Créer le tableau commentaires des clients  
 Créez un tableau contenant trois types différents de contrôles de contenu, dans lequel l'utilisateur peut entrer des informations sur les commentaires des clients.  
  
### <a name="to-create-the-customer-feedback-table"></a>Pour créer le tableau Commentaires des clients  
  
1.  Dans le modèle Word, cliquez sur la ligne après le tableau employé que vous avez ajouté précédemment, appuyez sur **entrée** pour ajouter un nouveau paragraphe.  
  
2.  Dans le ruban, cliquez sur le **insérer** onglet.  
  
3.  Dans le **Tables** de groupe, cliquez sur **Table**et insérez un tableau comportant deux colonnes et trois lignes.  
  
4.  Complétez la première colonne pour obtenir une colonne similaire à ceci :  
  
    ||  
    |-|  
    |**Nom du client**|  
    |**Indice de satisfaction**|  
    |**Commentaires**|  
  
5.  Cliquez dans la première cellule de la deuxième colonne (à côté **Customer Name**).  
  
6.  Dans le ruban, cliquez sur l'onglet **Développeur** .  
  
7.  Dans le **contrôles** de groupe, cliquez sur le **texte** bouton ![PlainTextContentControl](../vsto/media/plaintextcontrol.gif "PlainTextContentControl") pour ajouter un <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>à la première cellule.  
  
8.  Cliquez dans la deuxième cellule de la deuxième colonne (à côté **taux de Satisfaction**).  
  
9. Dans le **contrôles** de groupe, cliquez sur le **liste déroulante** bouton ![DropDownListContentControl](../vsto/media/dropdownlist.gif "DropDownListContentControl") pour ajouter un <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> dans la deuxième cellule.  
  
10. Cliquez dans la dernière cellule de la deuxième colonne (à côté **commentaires**).  
  
11. Dans le **contrôles** de groupe, cliquez sur le **Rich Text** bouton ![RichTextContentControl](../vsto/media/richtextcontrol.gif "RichTextContentControl") pour ajouter un <xref:Microsoft.Office.Tools.Word.RichTextContentControl>jusqu'à la dernière cellule.  
  
## <a name="populate-the-combo-box-and-drop-down-list-programmatically"></a>Remplir la zone de liste modifiable et de la liste déroulante par programmation  
 Vous pouvez initialiser des contrôles de contenu au moment du design à l’aide de la **propriétés** fenêtre dans [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Vous pouvez également les initialiser lors de l’exécution, ce qui vous permet de définir leurs états initiaux de manière dynamique. Pendant cette procédure pas à pas, utilisez le code pour remplir les entrées dans le <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> et <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> lors de l’exécution afin que vous puissiez voir comment fonctionnent ces objets.  
  
### <a name="to-modify-the-ui-of-the-content-controls-programmatically"></a>Pour modifier par programmation l'interface utilisateur des contrôles de contenu  
  
1.  Dans **l’Explorateur de solutions**, avec le bouton droit **ThisDocument.cs** ou **ThisDocument.vb**, puis cliquez sur **afficher le Code**.  
  
2.  Ajoutez le code suivant à la classe `ThisDocument`. Ce code déclare plusieurs objets que vous utiliserez ultérieurement dans cette procédure pas à pas.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#1](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#1)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#1](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#1)]  
  
3.  Ajoutez le code suivant à la méthode `ThisDocument_Startup` de la classe `ThisDocument`. Ce code ajoute des entrées aux contrôles <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> et <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> dans les tableaux, et définit le texte de l'espace réservé affiché dans chacun de ces contrôles avant que l'utilisateur les modifie.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#2](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#2)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#2](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#2)]  
  
## <a name="prevent-users-from-editing-the-employee-table"></a>Empêcher les utilisateurs de modifier le tableau employé  
 Utilisez l'objet <xref:Microsoft.Office.Tools.Word.GroupContentControl> que vous avez déclaré précédemment pour protéger le tableau Employé. Une fois le tableau protégé, les utilisateurs peuvent encore modifier les contrôles de contenu du tableau. Toutefois, ils ne peuvent plus modifier le texte de la première colonne ni modifier le tableau d'une quelconque autre manière, par exemple en ajoutant ou en supprimant des lignes et des colonnes. Pour plus d’informations sur la façon d’utiliser un <xref:Microsoft.Office.Tools.Word.GroupContentControl> pour protéger une partie d’un document, consultez [contrôles de contenu](../vsto/content-controls.md).  
  
### <a name="to-prevent-users-from-editing-the-employee-table"></a>Pour empêcher les utilisateurs de modifier le tableau Employé  
  
1.  Ajoutez le code suivant à la méthode `ThisDocument_Startup` de la classe `ThisDocument`, après le code que vous avez ajouté à l'étape précédente. Ce code empêche les utilisateurs de modifier le tableau Employé en plaçant celui-ci dans l'objet <xref:Microsoft.Office.Tools.Word.GroupContentControl> que vous avez déclaré précédemment.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#3](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#3)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#3](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#3)]  
  
## <a name="add-the-tables-to-the-building-block-collection"></a>Ajouter les tables à la collection de blocs de construction  
 Ajoutez les tableaux à une collection de blocs de construction de document dans le modèle afin que les utilisateurs puissent insérer les tableaux que vous avez créés dans le document. Pour plus d’informations sur les blocs de construction de document, consultez [contrôles de contenu](../vsto/content-controls.md).  
  
### <a name="to-add-the-tables-to-the-building-blocks-in-the-template"></a>Pour ajouter les tableaux aux blocs de construction du modèle  
  
1.  Ajoutez le code suivant à la méthode `ThisDocument_Startup` de la classe `ThisDocument`, après le code que vous avez ajouté à l'étape précédente. Ce code ajoute de nouveaux blocs de construction contenant les tables à la collection Microsoft.Office.Interop.Word.BuildingBlockEntries, qui contient des blocs de construction réutilisables du modèle. Les nouveaux blocs de construction sont définis dans une nouvelle catégorie nommée **informations employé et client** et prennent le type de bloc de construction `Microsoft.Office.Interop.Word.WdBuildingBlockTypes.wdTypeCustom1`.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#4](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#4)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#4](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#4)]  
  
2.  Ajoutez le code suivant à la méthode `ThisDocument_Startup` de la classe `ThisDocument`, après le code que vous avez ajouté à l'étape précédente. Ce code supprime les tableaux dans le modèle. Ces tableaux ne sont plus nécessaires car vous les avez ajoutés à la galerie des blocs de construction réutilisables du modèle. Le code place en premier lieu le document en mode Création pour permettre la suppression du tableau protégé Employé.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#5](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#5)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#5](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#5)]  
  
## <a name="create-a-content-control-that-displays-the-building-blocks"></a>Créer un contrôle de contenu affichant les blocs de construction  
 Créez un contrôle de contenu permettant d'accéder aux blocs de construction (autrement dit, aux tableaux) que vous avez créés précédemment. Les utilisateurs peuvent cliquer sur ce contrôle pour ajouter les tableaux dans le document.  
  
### <a name="to-create-a-content-control-that-displays-the-building-blocks"></a>Pour créer un contrôle de contenu affichant les blocs de construction  
  
1.  Ajoutez le code suivant à la méthode `ThisDocument_Startup` de la classe `ThisDocument`, après le code que vous avez ajouté à l'étape précédente. Ce code initialise l'objet <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> déclaré précédemment. Le <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> affiche tous les blocs de construction sont définis dans la catégorie **informations employé et client** et qui ont le type de bloc de construction `Microsoft.Office.Interop.Word.WdBuildingBlockTypes.wdTypeCustom1`.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#6](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#6)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#6](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#6)]  
  
## <a name="test-the-project"></a>Le projet de test  
 Les utilisateurs peuvent cliquer sur les contrôles de la galerie des blocs de construction du document pour insérer le tableau Employé ou le tableau Commentaires des clients. Ils peuvent taper ou sélectionner des réponses dans les contrôles de contenu des deux tableaux. Ils peuvent aussi modifier d'autres parties du tableau Commentaires des clients, mais ils ne doivent pas pouvoir modifier d'autres parties du tableau Employé.  
  
### <a name="to-test-the-employee-table"></a>Pour tester le tableau Employé  
  
1.  Appuyez sur **F5** pour exécuter le projet.  
  
2.  Cliquez sur **choisir votre premier bloc de construction** pour afficher le premier contrôle de contenu de la galerie des blocs de construction.  
  
3.  Cliquez sur la flèche déroulante en regard du **Galerie 1 personnalisée** titre dans le contrôle, puis sélectionnez **Table Employee**.  
  
4.  Cliquez dans la cellule à droite de la **nom de l’employé** de la cellule et tapez un nom.  
  
     Vérifiez que vous pouvez ajouter uniquement du texte dans cette cellule. Le contrôle <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> permet aux utilisateurs d'ajouter du texte uniquement, pas d'autres types de contenu tels que des illustrations ou des tableaux.  
  
5.  Cliquez dans la cellule à droite de la **Date d’embauche** de la cellule et sélectionnez une date dans le sélecteur de dates.  
  
6.  Cliquez dans la cellule à droite de la **titre** de la cellule et sélectionnez un des postes dans la zone de liste déroulante.  
  
     Si vous le souhaitez, tapez le nom d'une fonction qui ne figure pas dans la liste. Cela est possible car le contrôle <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> permet aux utilisateurs d'effectuer un choix dans une liste d'entrées ou de taper leurs propres entrées.  
  
7.  Cliquez sur l’icône dans la cellule à droite de la **image** de cellule, puis accédez à une image pour l’afficher.  
  
8.  Essayez d'ajouter et de supprimer des lignes et des colonnes dans le tableau. Vérifiez que vous ne pouvez pas modifier le tableau. L'objet <xref:Microsoft.Office.Tools.Word.GroupContentControl> vous empêche d'apporter la moindre modification.  
  
### <a name="to-test-the-customer-feedback-table"></a>Pour tester le tableau Commentaires des clients  
  
1.  Cliquez sur **choisir votre deuxième bloc de construction** pour afficher le deuxième contrôle de contenu de la galerie des blocs de construction.  
  
2.  Cliquez sur la flèche déroulante en regard du **Galerie 1 personnalisée** titre dans le contrôle, puis sélectionnez **Table Customer**.  
  
3.  Cliquez dans la cellule à droite de la **Customer Name** de la cellule et tapez un nom.  
  
4.  Cliquez dans la cellule à droite de la **taux de Satisfaction** de la cellule et sélectionnez une des options disponibles.  
  
     Vérifiez que vous ne pouvez pas taper votre propre entrée. L'objet <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> permet uniquement aux utilisateurs d'effectuer un choix dans une liste d'entrées.  
  
5.  Cliquez dans la cellule à droite de la **commentaires** de cellule et tapez des commentaires.  
  
     Si vous le souhaitez, ajoutez du contenu autre que du texte, comme une illustration ou un tableau incorporé. Cela est possible car l'objet <xref:Microsoft.Office.Tools.Word.RichTextContentControl> permet aux utilisateurs d'ajouter du contenu autre que du texte.  
  
6.  Vérifiez que vous pouvez ajouter et supprimer des lignes et des colonnes dans le tableau. Cela est possible parce que vous n'avez pas protégé le tableau en le plaçant dans un objet <xref:Microsoft.Office.Tools.Word.GroupContentControl>.  
  
7.  Fermez le modèle.  
  
## <a name="next-steps"></a>Étapes suivantes  
 Pour plus d'informations sur l'utilisation des contrôles de contenu, consultez la rubrique suivante :  
  
-   Lier des contrôles de contenu à des fragments XML, ou parties XML personnalisées, qui sont incorporés dans un document. Pour plus d’informations, consultez [procédure pas à pas : lier des contrôles de contenu à des parties XML personnalisées](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Automatiser Word à l’aide d’objets étendus](../vsto/automating-word-by-using-extended-objects.md)   
 [Contrôles de contenu](../vsto/content-controls.md)   
 [Comment : ajouter des contrôles de contenu à des documents Word](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Comment : protéger des parties de documents à l’aide de contrôles de contenu](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)   
 [Éléments hôtes et la vue d’ensemble des contrôles hôtes](../vsto/host-items-and-host-controls-overview.md)   
 [Limitations de programmation des éléments hôtes et contrôles hôtes](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Ajouter des contrôles aux documents Office au moment de l’exécution](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  