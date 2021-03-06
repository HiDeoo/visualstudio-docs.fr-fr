---
title: Lier des contrôles WPF à des données (partie 1) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: e05a1e0c-5082-479d-bbc9-d395b0bc6580
caps.latest.revision: 39
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 25b144409ae58f006602706a5b5cb498c0535ea2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85540164"
---
# <a name="bind-wpf-controls-to-data-in-visual-studio"></a>Lier des contrôles WPF à des données dans Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez afficher des données pour les utilisateurs de votre application en liant des données à des contrôles [!INCLUDE[TLA#tla_titlewinclient](../includes/tlasharptla-titlewinclient-md.md)]. Pour créer ces contrôles liés aux données, vous pouvez faire glisser des éléments depuis la fenêtre **sources de données** vers le [!INCLUDE[wpfdesigner_current_short](../includes/wpfdesigner-current-short-md.md)] dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] . Cette rubrique décrit quelques tâches, outils et classes les plus courants que vous pouvez utiliser pour créer des applications [!INCLUDE[TLA#tla_titlewinclient](../includes/tlasharptla-titlewinclient-md.md)] liées aux données.

 Pour obtenir des informations générales sur la création de contrôles liés aux données dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , consultez [lier des contrôles à des données dans Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md). Pour plus d’informations sur la [!INCLUDE[TLA#tla_titlewinclient](../includes/tlasharptla-titlewinclient-md.md)] liaison de données, consultez [vue d’ensemble](https://msdn.microsoft.com/library/c707c95f-7811-401d-956e-2fffd019a211)de la liaison de données.

## <a name="tasks-involved-in-binding-wpf-controls-to-data"></a>Tâches impliquées dans la liaison de contrôles WPF à des données
 Le tableau suivant liste les tâches qui peuvent être accomplies en faisant glisser des éléments de la fenêtre **Sources de données** vers le [!INCLUDE[wpfdesigner_current_short](../includes/wpfdesigner-current-short-md.md)].

|Tâche|Informations complémentaires|
|----------|----------------------|
|Créer des contrôles liés aux données.<br /><br /> Lier des contrôles existants à des données.|[Lier des contrôles WPF à des données dans Visual Studio lier des](../data-tools/bind-wpf-controls-to-data-in-visual-studio2.md) [contrôles WPF à un DataSet](../data-tools/bind-wpf-controls-to-a-dataset.md)|
|Créer des contrôles qui affichent les données connexes d'une relation parent-enfant : lorsque l'utilisateur sélectionne un enregistrement de données parentes dans un contrôle, un autre contrôle affiche les données enfants connexes pour l'enregistrement sélectionné.|[Afficher des données associées dans des applications WPF](../data-tools/display-related-data-in-wpf-applications.md)|
|Créer une *table de recherche* qui affiche les informations provenant d’une table en fonction de la valeur d’un champ de clé étrangère d’une autre table.|[Créer des tables de recherche dans des applications WPF](../data-tools/create-lookup-tables-in-wpf-applications.md)|
|Lier un contrôle à une image dans une base de données.|[Lier des contrôles à des images d’une base de données](../data-tools/bind-controls-to-pictures-from-a-database.md)|

## <a name="valid-drop-targets"></a>Cibles de dépôt valides
 Vous pouvez faire glisser des éléments dans la fenêtre **Sources de données** seulement vers les cibles de dépôt valides dans le [!INCLUDE[wpfdesigner_current_short](../includes/wpfdesigner-current-short-md.md)]. Il existe deux genres principaux de cibles de déplacement valides : conteneurs et contrôles. Un conteneur est un élément d'interface utilisateur qui contient généralement des contrôles. Par exemple, une grille est un conteneur, de même qu'une fenêtre.

## <a name="generated-xaml-and-code"></a>XAML généré et code
 Lorsque vous faites glisser un élément de la fenêtre **sources de données** vers le [!INCLUDE[wpfdesigner_current_short](../includes/wpfdesigner-current-short-md.md)] , [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] génère [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] qui définit un nouveau contrôle lié aux données (ou lie un contrôle existant à la source de données). Pour certaines sources de données, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] génère également du code dans le fichier code-behind qui remplit la source de données avec les données.

 Le tableau suivant répertorie les [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] et le code [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] générés par pour chaque type de source de données dans la fenêtre **sources de données** .

|Source de données|Générer le code XAML qui lie un contrôle à la source de données|Générer du code qui remplit la source de données avec les données|
|-----------------|-----------------------------------------------------------|--------------------------------------------------------|
|Dataset|Oui|Oui|
|[!INCLUDE[adonet_edm](../includes/adonet-edm-md.md)]|Oui|Oui|
|Service|Oui|Non|
|Object|Oui|Non|

### <a name="datasets"></a>Groupes de données
 Lorsque vous faites glisser une table ou une colonne de la fenêtre **sources de données** vers le concepteur, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] génère [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] ce qui suit :

- Ajoute le groupe de données (dataset) et un nouveau <xref:System.Windows.Data.CollectionViewSource> aux ressources du conteneur vers lequel vous avez fait glisser l'élément. Le <xref:System.Windows.Data.CollectionViewSource> est un objet qui peut être utilisé pour naviguer et pour afficher les données dans le groupe de données.

- Crée une liaison de données pour un contrôle. Si vous faites glisser l'élément vers un contrôle existant dans le concepteur, le code XAML lie le contrôle à l'élément. Si vous faites glisser l’élément vers un conteneur, le code XAML crée le contrôle sélectionné pour l’élément déplacé et lie le contrôle à l’élément. Le contrôle est créé dans une nouvelle <xref:System.Windows.Controls.Grid>.

  [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] apporte également les modifications suivantes au fichier code-behind :

- Crée un gestionnaire d'événements <xref:System.Windows.FrameworkElement.Loaded> pour l'élément [!INCLUDE[TLA2#tla_ui](../includes/tla2sharptla-ui-md.md)] qui contient le contrôle. Le gestionnaire d'événements remplit la table des données, extrait le <xref:System.Windows.Data.CollectionViewSource> des ressources du conteneur, puis active le premier élément de données comme élément de données actuel. Si un <xref:System.Windows.FrameworkElement.Loaded> Gestionnaire d’événements existe déjà, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ajoute ce code au gestionnaire d’événements existant.

### <a name="entity-data-models"></a>Modèles de données d’entité
 Lorsque vous faites glisser une entité ou une propriété d’entité de la fenêtre **sources de données** vers le concepteur, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] génère [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] ce qui suit :

- Ajoute un nouveau <xref:System.Windows.Data.CollectionViewSource> aux ressources du conteneur vers lequel vous avez fait glisser l'élément. Le <xref:System.Windows.Data.CollectionViewSource> est un objet qui peut être utilisé pour naviguer et pour afficher les données dans l'entité.

- Crée une liaison de données pour un contrôle. Si vous faites glisser l'élément vers un contrôle existant dans le concepteur, le code [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] lie le contrôle à l'élément. Si vous faites glisser l’élément vers un conteneur, le [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] crée le contrôle sélectionné pour l’élément déplacé et lie le contrôle à l’élément. Le contrôle est créé dans une nouvelle <xref:System.Windows.Controls.Grid>.

  Visual Studio apporte également les modifications suivantes au fichier code-behind :

- Ajoute une nouvelle méthode qui retourne une requête pour l'entité que vous avez fait glisser vers le concepteur (ou l'entité qui contient la propriété que vous avez fait glisser vers le concepteur). La nouvelle méthode porte le nom obtenir la requête*EntityName*, où *EntityName* est le nom de l’entité.

- Crée un gestionnaire d'événements <xref:System.Windows.FrameworkElement.Loaded> pour l'élément [!INCLUDE[TLA2#tla_ui](../includes/tla2sharptla-ui-md.md)] qui contient le contrôle. Le gestionnaire d’événements appelle la méthode de requête obtenir*EntityName*pour remplir l’entité avec des données, extrait le <xref:System.Windows.Data.CollectionViewSource> des ressources du conteneur, puis définit le premier élément de données comme élément actuel. Si un <xref:System.Windows.FrameworkElement.Loaded> Gestionnaire d’événements existe déjà, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ajoute ce code au gestionnaire d’événements existant.

### <a name="services"></a>Services
 Lorsque vous faites glisser un objet de service ou une propriété de la fenêtre **sources de données** vers le concepteur, génère l’objet pour [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] créer un contrôle lié aux données (ou lie un contrôle existant à l’objet ou à la propriété). Toutefois, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ne génère pas de code qui remplit l'objet de service proxy avec les données. Vous devez écrire ce code vous-même. Pour obtenir un exemple qui montre comment procéder, consultez [lier des contrôles WPF à un service de données WCF](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md).

 Visual Studio génère du code XAML qui effectue les opérations suivantes :

- Ajoute un nouveau <xref:System.Windows.Data.CollectionViewSource> aux ressources du conteneur vers lequel vous avez fait glisser l'élément. Le <xref:System.Windows.Data.CollectionViewSource> est un objet qui peut être utilisé pour naviguer et pour afficher les données dans l'objet retourné par le service.

- Crée une liaison de données pour un contrôle. Si vous faites glisser l'élément vers un contrôle existant dans le concepteur, le code [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] lie le contrôle à l'élément. Si vous faites glisser l’élément vers un conteneur, le [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] crée le contrôle sélectionné pour l’élément déplacé et lie le contrôle à l’élément. Le contrôle est créé dans une nouvelle <xref:System.Windows.Controls.Grid>.

### <a name="objects"></a>Objets
 Quand vous faites glisser un objet ou une propriété de la fenêtre **sources de données** vers le concepteur, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] génère [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] un contrôle lié aux données (ou lie un contrôle existant à l’objet ou à la propriété). Toutefois, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ne génère pas de code pour remplir l'objet avec les données. Vous devez écrire ce code vous-même.

> [!NOTE]
> Les classes personnalisées doivent être publiques et, par défaut, avoir un constructeur sans paramètres. Elles ne peuvent pas être des classes imbriquées qui ont un « point » dans leur syntaxe. Pour plus d’informations, consultez [XAML et classes personnalisées pour WPF](https://msdn.microsoft.com/library/e7313137-581e-4a64-8453-d44e15a6164a).

 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] génère [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] qui effectue les opérations suivantes :

- Ajoute un nouveau <xref:System.Windows.Data.CollectionViewSource> aux ressources du conteneur vers lequel vous avez fait glisser l'élément. Le <xref:System.Windows.Data.CollectionViewSource> est un objet qui peut être utilisé pour naviguer et pour afficher les données dans l'objet.

- Crée une liaison de données pour un contrôle. Si vous faites glisser l'élément vers un contrôle existant dans le concepteur, le code XAML lie le contrôle à l'élément. Si vous faites glisser l’élément vers un conteneur, le code XAML crée le contrôle sélectionné pour l’élément déplacé et lie le contrôle à l’élément. Le contrôle est créé dans une nouvelle <xref:System.Windows.Controls.Grid>.

## <a name="see-also"></a>Voir aussi
 [Lier des contrôles à des données dans Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)
