---
title: solutions Excel
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], application-level add-ins
- Office solutions [Office development in Visual Studio], Excel
- solutions [Office development in Visual Studio], Excel
- add-ins [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], about Excel solutions
- Excel [Office development in Visual Studio]
- documents [Office development in Visual Studio], Excel
- Office documents [Office development in Visual Studio, Excel
- projects [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], document-level customizations
- user interfaces [Office development in Visual Studio], Excel
- Office development in Visual Studio, Excel solutions
- document-level customizations [Office development in Visual Studio], Excel
- Office projects [Office development in Visual Studio], Excel
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0e37bea181441b7026fdb3ecc1236296409b7749
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35670916"
---
# <a name="excel-solutions"></a>solutions Excel
  Visual Studio fournit des modèles de projet à l'aide desquels vous pouvez créer des personnalisations de niveau document et des compléments VSTO pour Microsoft Office Excel. Vous pouvez utiliser ces solutions pour automatiser Excel, étendre les fonctionnalités Excel et personnaliser l'interface utilisateur Excel. Pour plus d’informations sur les différences entre personnalisations au niveau du document et des Compléments VSTO, consultez [présentation du développement de solutions Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
> [!NOTE]  
>  Vous souhaitez développer des solutions qui étendent l’expérience Office sur [plusieurs plateformes](https://dev.office.com/add-in-availability)? Découvrez le nouvel [modèle de compléments Office](https://dev.office.com/docs/add-ins/overview/office-add-ins). Compléments Office peu encombrantes par rapport aux compléments VSTO et de solutions, et vous pouvez les créer à l’aide de presque toutes les technologies, telles que HTML5, JavaScript, CSS3 et XML de programmation web.  
  
 Cette rubrique fournit les informations suivantes :  
  
-   [Automatiser Excel](#automating).  
  
-   [Développer des personnalisations au niveau du document pour Excel](#doclevel).  
  
-   [Développer des Compléments VSTO pour Excel](#applevel).  
  
-   [Personnaliser l’interface utilisateur d’Excel](#UI).  
  
##  <a name="automating"></a> Automatiser Excel  
 Le modèle objet Excel expose de nombreux types que vous pouvez utiliser pour automatiser Excel. Par exemple, vous pouvez créer des graphiques par programmation, mettre en forme des feuilles de calcul et définir les valeurs de plages et de cellules. Pour plus d’informations, consultez [vue d’ensemble du modèle d’objet Excel](../vsto/excel-object-model-overview.md).  
  
 Lorsque vous développez des solutions Excel dans Visual Studio, vous pouvez également utiliser les *éléments hôtes* et les *contrôles hôtes* dans vos solutions. Il s'agit d'objets qui étendent certains objets couramment utilisés dans le modèle objet Excel, tels que les objets <xref:Microsoft.Office.Interop.Excel.Worksheet> et <xref:Microsoft.Office.Interop.Excel.Range> . Les objets étendus se comportent comme les objets Excel dont ils dépendent, mais ils ajoutent des événements supplémentaires et des fonctionnalités de liaison de données aux objets. Pour plus d’informations, consultez [automatisation d’Excel à l’aide d’objets étendus](../vsto/automating-excel-by-using-extended-objects.md).  
  
##  <a name="doclevel"></a> Développer des personnalisations au niveau du document pour Excel  
 Une personnalisation au niveau du document pour Microsoft Office Excel se compose d'un assembly qui est associé à un classeur spécifique. L'assembly augmente généralement les fonctionnalités du classeur en personnalisant l'interface utilisateur et en automatisant Excel. Contrairement à un complément VSTO, qui est associé à Excel lui-même, les fonctionnalités que vous implémentez dans une personnalisation sont disponibles uniquement lorsque le classeur associé est ouvert dans Excel.  
  
 Pour créer un projet de personnalisation au niveau du document pour Excel, utilisez le classeur Excel ou les modèles de projet de modèle Excel dans le **nouveau projet** boîte de dialogue de Visual Studio. Pour plus d’informations, consultez [Comment : les projets Office de créer dans Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Pour plus d’informations sur comment au niveau du document personnalisations, consultez [Architecture des personnalisations au niveau du document](../vsto/architecture-of-document-level-customizations.md).  
  
### <a name="excel-customization-programming-model"></a>Modèle de programmation de personnalisation Excel  
 Lorsque vous créez un projet au niveau du document pour Excel, Visual Studio génère plusieurs classes qui constituent la base de votre solution : `ThisWorkbook`, `Sheet1`, `Sheet2`et `Sheet3`. Ces classes représentent le classeur et les feuilles de calcul qui sont associés à votre solution et fournissent un point de départ pour écrire votre code.  
  
 Pour plus d’informations sur ces classes générées et autres fonctionnalités que vous pouvez utiliser dans un projet au niveau du document, consultez [programmer des personnalisations au niveau du document](../vsto/programming-document-level-customizations.md).  
  
##  <a name="applevel"></a> Développer des Compléments VSTO pour Excel  
 Un complément VSTO pour Microsoft Office Excel se compose d'un assembly qui est chargé par Excel. L'assembly augmente généralement les fonctionnalités Excel en personnalisant l'interface utilisateur et en automatisant Excel. Contrairement à une personnalisation au niveau du document, qui est associée à un classeur spécifique, les fonctionnalités que vous implémentez dans un complément, VSTO ne sont pas limitées à un seul classeur.  
  
 Pour créer un projet de complément VSTO pour Excel, utilisez le classeur Excel ou les modèles de projet de modèle Excel dans le **nouveau projet** boîte de dialogue de Visual Studio. Pour plus d’informations, consultez [Comment : les projets Office de créer dans Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Pour obtenir des informations générales sur le fonctionnement des compléments VSTO, consultez [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md).  
  
 ![lien vers la vidéo](../vsto/media/playvideo.gif "lien vers la vidéo") pour une démonstration vidéo connexe, consultez [comment faire pour automatiser PowerPoint à partir d’une macro complémentaire Excel ?](http://go.microsoft.com/fwlink/?LinkID=130300).  
  
### <a name="excel-add-in-programming-model"></a>Excel Add-in modèle de programmation  
 Lorsque vous créez un projet de complément VSTO Excel, Visual Studio génère une classe, nommée `ThisAddIn`, qui est le fondement de votre solution. Cette classe fournit un point de départ pour écrire votre code et elle expose également le modèle objet d’Excel à votre complément VSTO.  
  
 Pour plus d’informations sur la `ThisAddIn` classe et autres fonctionnalités de Visual Studio que vous pouvez utiliser dans un complément VSTO, consultez [programme VSTO Add-Ins](../vsto/programming-vsto-add-ins.md).  
  
##  <a name="UI"></a> Personnaliser l’interface utilisateur d’Excel  
 Il existe différentes façons de personnaliser l'interface utilisateur d'Excel. Certaines options sont disponibles pour tous les types de projets, tandis que d'autres options sont disponibles uniquement pour les compléments VSTO ou les personnalisations au niveau du document.  
  
### <a name="options-for-all-project-types"></a>Options pour tous les types de projet  
 Le tableau suivant répertorie les options de personnalisation qui sont disponibles pour les personnalisations au niveau du document et les compléments VSTO.  
  
|Tâche|Pour plus d'informations|  
|----------|--------------------------|  
|Personnaliser le ruban.|[Vue d’ensemble du ruban](../vsto/ribbon-overview.md)|  
|Ajouter des contrôles Windows Forms ou contrôles Excel étendus à une feuille de calcul dans le classeur personnalisé pour une personnalisation au niveau du document ou d'un classeur ouvert pour un complément VSTO.|[Comment : ajouter des contrôles Windows forms aux documents Office](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)<br /><br /> [Comment : ajouter des contrôles Chart aux feuilles de calcul](../vsto/how-to-add-chart-controls-to-worksheets.md)<br /><br /> [Comment : ajouter des contrôles ListObject aux feuilles de calcul](../vsto/how-to-add-listobject-controls-to-worksheets.md)<br /><br /> [Comment : ajouter des contrôles NamedRange aux feuilles de calcul](../vsto/how-to-add-namedrange-controls-to-worksheets.md)|  
  
### <a name="options-for-document-level-customizations"></a>Options pour les personnalisations au niveau du document  
 Le tableau suivant répertorie les options de personnalisation qui sont disponibles uniquement pour les personnalisations au niveau du document.  
  
|Tâche|Pour plus d'informations|  
|----------|--------------------------|  
|Ajouter un volet Actions au classeur.|[Vue d’ensemble du volet Actions](../vsto/actions-pane-overview.md)<br /><br /> [Comment : ajouter un volet actions à des documents Word ou de classeurs Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)|  
|Ajoutez des contrôles de plage étendue mappés aux nœuds XML d'une feuille de calcul.|[Comment : ajouter des contrôles XMLMappedRange aux feuilles de calcul](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)|  
  
### <a name="options-for-vsto-add-ins"></a>Options pour les compléments VSTO  
 Le tableau suivant répertorie les options de personnalisation qui sont disponibles uniquement pour les compléments VSTO.  
  
|Tâche|Pour plus d'informations|  
|----------|--------------------------|  
|Créer un volet des tâches personnalisé.|[Volets Office personnalisés](../vsto/custom-task-panes.md)|  
  
### <a name="related-topics"></a>Rubriques connexes  
|Titre|Description|  
|-----------|-----------------|  
|[Vue d’ensemble du modèle d’objet Excel](../vsto/excel-object-model-overview.md)|Fournit une vue d'ensemble des principaux types fournis par le modèle objet Excel.|  
|[Automatiser Excel à l’aide d’objets étendus](../vsto/automating-excel-by-using-extended-objects.md)|Fournit des informations sur les objets étendus (fournis par le [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]) que vous pouvez utiliser dans les solutions Excel.|  
|[Globalisation et localisation de solutions Excel](../vsto/globalization-and-localization-of-excel-solutions.md)|Contient des informations sur les considérations spéciales pour les solutions Excel qui seront exécutées sur les ordinateurs ayant des paramètres autres qu'anglais pour Windows.|  
|[Contrôles Windows Forms dans les documents Office](../vsto/windows-forms-controls-on-office-documents-overview.md)|Décrit comment ajouter des contrôles Windows Forms aux feuilles de calcul Excel.|  
|[Procédure pas à pas : Créer votre première personnalisation au niveau du document pour Excel](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)|Montre comment créer une personnalisation de base au niveau du document pour Excel.|  
|[Procédure pas à pas : Créer votre premier complément pour Excel](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)|Montre comment créer un complément VSTO de base pour Excel.|  
|[Procédure pas à pas : Ajouter des contrôles à une feuille de calcul lors de l’exécution dans un projet de complément VSTO](../vsto/walkthrough-adding-controls-to-a-worksheet-at-run-time-in-vsto-add-in-project.md)|Montre comment ajouter un contrôle button Windows Forms, un <xref:Microsoft.Office.Tools.Excel.NamedRange>et un <xref:Microsoft.Office.Tools.Excel.ListObject> à une feuille de calcul lors de l’exécution en utilisant un complément, VSTO.|
|[Comprendre la co-création et Add-ins](./understanding-coauthoring-and-addins.md)|Décrit les ajustements, que vous devrez peut-être apporter à vos solutions pour prendre en compte la cocréation.|  
|[Excel 2010 dans le développement Office](http://go.microsoft.com/fwlink/?LinkId=199011)|Fournit des liens vers des articles et une documentation de référence sur le développement de solutions Excel. Ils ne sont pas spécifiques au développement Office avec Visual Studio.|  
  
  