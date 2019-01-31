---
title: Boîte à outils, onglet Données
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Toolbox, Data tab
- Data tab, Toolbox
- data [Visual Studio], Toolbox
ms.assetid: 2ae38b2a-29d2-461c-a67d-29dad274bf45
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0f30bc874f5ed3debecf24a3259a8b13c9c38d49
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54997401"
---
# <a name="toolbox-data-tab"></a>Boîte à outils, onglet Données

Affiche des objets de données que vous pouvez ajouter à un formulaire et à des composants. L’onglet **Données** de la **boîte à outils** apparaît quand vous créez un projet associé à un concepteur. La **boîte à outils** apparaît par défaut dans l’environnement de développement intégré Visual Studio ; si vous devez afficher la **boîte à outils**, sélectionnez **Boîte à outils** dans le menu **Affichage**.

> [!TIP]
> L’exécution de l’Assistant Configuration de source de données crée et configure automatiquement la plupart des éléments de données. Pour plus d’informations, consultez [Ajouter de nouvelles sources de données](../../data-tools/add-new-data-sources.md).

## <a name="ui-element-list"></a>Liste des éléments de l'interface utilisateur

Pour accéder directement à la page de référence .NET Framework d’un composant, appuyez sur **F1** avec le pointeur placé sur l’élément dans la **boîte à outils** ou sur le composant dans la barre d’état du concepteur.

|Name|Description|
|----------|-----------------|
|<xref:System.Data.DataSet>|Ajoute une instance d’un dataset typé ou non typé au formulaire ou composant. Quand vous faites glisser cet objet dans un concepteur, il affiche une boîte de dialogue qui permet de sélectionner une classe de dataset typée existante ou de spécifier que vous souhaitez créer un dataset vide et non typé. **Remarque :**  N’utilisez pas l’objet <xref:System.Data.DataSet> de la **boîte à outils** pour créer un schéma et une classe de dataset typés. Pour plus d’informations, consultez [Créer et configurer des datasets](../../data-tools/create-and-configure-datasets-in-visual-studio.md).|
|<xref:System.Windows.Forms.DataGridView>|Offre un moyen puissant et souple d’afficher des données sous forme de tableau.|
|<xref:System.Windows.Forms.BindingSource>|Simplifie le processus de liaison des contrôles à une source de données sous-jacente.|
|<xref:System.Windows.Forms.BindingNavigator>|Représente l'interface utilisateur de navigation et manipulation pour les contrôles d'un formulaire liés aux données.|

## <a name="see-also"></a>Voir aussi

- [Accéder aux données dans Visual Studio](../../data-tools/accessing-data-in-visual-studio.md)
- [Outils de données Visual Studio pour .NET](../../data-tools/visual-studio-data-tools-for-dotnet.md)
- [Outils de dataset dans Visual Studio](../../data-tools/dataset-tools-in-visual-studio.md)
- [Lier des contrôles à des données dans Visual Studio](../../data-tools/bind-controls-to-data-in-visual-studio.md)
- [Lier des contrôles Windows Forms à des données dans Visual Studio](../../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Modifier des données dans des datasets](../../data-tools/edit-data-in-datasets.md)
- [Valider les données dans des datasets](../../data-tools/validate-data-in-datasets.md)