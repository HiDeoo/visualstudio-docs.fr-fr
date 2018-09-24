---
title: 'Comment : parcourir les enregistrements de base de données dans une feuille de calcul'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
- worksheets [Office development in Visual Studio], scrolling records
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7e9ffaffdefda98e3e074467fcd4df8cacce91b4
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35672884"
---
# <a name="how-to-scroll-through-database-records-in-a-worksheet"></a>Comment : parcourir les enregistrements de base de données dans une feuille de calcul
  La procédure suivante montre comment utiliser le concepteur pour afficher un champ d’une table de base de données dans une feuille de calcul Microsoft Office Excel, avec des contrôles qui permettent aux utilisateurs finaux de faire défiler tous les enregistrements.  
  
 Vous pouvez utiliser le concepteur uniquement dans les projets au niveau du document. Toutefois, vous pouvez également ajouter des contrôles et les lier aux données par programmation lors de l’exécution. Pour plus d’informations, consultez [procédure pas à pas : liaison de données Simple dans un projet de complément VSTO](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md).  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
## <a name="to-scroll-through-database-records-in-a-worksheet"></a>Pour faire défiler les enregistrements de base de données dans une feuille de calcul  
  
1.  Ouvrez un projet d’application Excel dans Visual Studio.  
  
2.  Ouvrez le **des Sources de données** fenêtre et créer une source de données à partir de la base de données. Pour plus d’informations, consultez [ajouter de nouvelles connexions](../data-tools/add-new-connections.md).  
  
3.  Développez la table qui contient les données que vous souhaitez afficher, puis sélectionnez la colonne spécifique.  
  
4.  Ouvrir la liste des contrôles, puis sélectionnez **NamedRange**.  
  
5.  Faites glisser le <xref:Microsoft.Office.Tools.Excel.NamedRange> contrôle vers la cellule où vous souhaitez afficher les données.  
  
6.  À partir de la **Windows Forms** onglet de la **boîte à outils**, ajoutez un <xref:System.Windows.Forms.BindingNavigator> le contrôle à votre feuille de calcul et de configurer les contrôles que vous souhaitez utiliser. Pour plus d’informations, consultez [vue d’ensemble du contrôle BindingNavigator &#40;Windows Forms&#41;](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms).  
  
## <a name="see-also"></a>Voir aussi  
 [Lier des données aux contrôles dans les solutions Office](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  