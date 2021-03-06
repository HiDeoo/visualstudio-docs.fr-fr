---
title: Fenêtre Propriétés | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- properties [Visual Studio], Properties Window
- handler functions, Properties window
- handlers, Properties window
- Windows messages
- properties [Visual Studio], setting at design time
- properties [Visual Studio], editing
- Property Browser
- Windows messages, adding message handlers
- Properties window, overrides
- virtual functions, Properties window
- Properties window
ms.assetid: e6e0fa4f-75c4-4a52-af15-281cd61876ca
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 959bd36995ca4086bf64020816b00aee6f777fbe
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72662070"
---
# <a name="properties-window"></a>Fenêtre Propriétés
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Utilisez cette fenêtre pour afficher et modifier les événements et propriétés au moment du design des objets sélectionnés qui sont situés dans les éditeurs et les concepteurs. Vous pouvez également utiliser la fenêtre **Propriétés** pour afficher et modifier les propriétés des fichiers, des projets et des solutions. Vous trouverez la fenêtre **Propriétés** dans le menu **Affichage**. Vous pouvez également l’ouvrir en appuyant sur F4 ou en tapant **Propriétés** dans la fenêtre **Lancement rapide**.

 La fenêtre **Propriétés** affiche différents types de champs d’édition, en fonction des besoins d’une propriété particulière. Ces champs d’édition sont notamment des zones d’édition, des listes déroulantes et des liens vers des boîtes de dialogue d’éditeur personnalisé. Les propriétés affichées en gris sont en lecture seule.

## <a name="uielement-list"></a>Liste des éléments de l'interface utilisateur
 Nom de l’objet répertorie les objets actuellement sélectionnés. Seuls les objets de l'éditeur ou du générateur actif sont visibles. Quand vous sélectionnez plusieurs objets, seules les propriétés communes à tous les objets sélectionnés s’affichent.

 Catégoriséd répertorie toutes les propriétés et les valeurs de propriété pour l’objet sélectionné, par catégorie. Vous pouvez réduire une catégorie afin de diminuer le nombre de propriétés visibles. Quand vous développez ou réduisez une catégorie, un signe plus (+) ou moins (-) s’affiche à gauche du nom de la catégorie. Les catégories s'affichent par ordre alphabétique.

 Alphabétique trie par ordre alphabétique tous les événements et propriétés au moment du design pour les objets sélectionnés. Pour modifier une propriété non estompée, cliquez dans la cellule située à sa droite et entrez les modifications souhaitées.

 Pages de propriétés affiche la boîte de dialogue **pages de propriétés** ou le **Concepteur de projets** pour l’élément sélectionné. La boîte de dialogue Pages de propriétés affiche un sous-ensemble, un ensemble équivalent ou un sur-ensemble des propriétés disponibles dans la fenêtre **Propriétés**. Utilisez ce bouton pour afficher et modifier des propriétés relatives à la configuration active de votre projet.

 Propriétés affiche les propriétés d’un objet. De nombreux objets possèdent également des événements qui peuvent être affichés à l’aide de la fenêtre **Propriétés**.

 Triez les propriétés des groupes de sources de propriété par source, telles que l’héritage, les styles appliqués et les liaisons. Uniquement disponible lors de la modification de fichiers XAML dans le concepteur.

 Événements affiche les événements d’un objet.

> [!NOTE]
> Ce contrôle de barre d’outils de la fenêtre **Propriétés** n’est disponible que quand un Concepteur de formulaires ou de contrôles est actif dans le contexte d’un projet [!INCLUDE[csprcs](../../includes/csprcs-md.md)]. Lors de la modification de fichiers XAML, les événements apparaissent sous un onglet séparé de la fenêtre Propriétés.

 Messages répertorie tous les messages Windows. Vous permet d’ajouter ou de supprimer des fonctions gestionnaires spécifiées pour les messages fournis pour la classe sélectionnée.

> [!NOTE]
> Ce contrôle de barre d’outils de la fenêtre **Propriétés** n’est disponible que quand la fenêtre active est **Affichage de classes** dans le contexte d’un projet [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)].

 Substitutions répertorie toutes les fonctions virtuelles pour la classe sélectionnée et vous permet d’ajouter ou de supprimer des fonctions de substitution.

> [!NOTE]
> Ce contrôle de barre d’outils de la fenêtre **Propriétés** n’est disponible que quand la fenêtre active est **Affichage de classes** dans le contexte d’un projet [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)].

 Le volet Description affiche le type de propriété et une brève description de la propriété. Vous pouvez activer et désactiver la description de la propriété à l’aide de la commande Description du menu contextuel.

> [!NOTE]
> Ce contrôle de barre d’outils de la fenêtre **Propriétés** n’est pas disponible lors de la modification de fichiers XAML dans le concepteur.

 La vue miniature affiche une représentation visuelle de l’élément actuellement sélectionné lors de la modification de fichiers XAML dans le concepteur.

 La recherche fournit une fonction de recherche pour les propriétés et les événements lors de la modification de fichiers XAML dans le concepteur. La zone de recherche répond aux recherches de correspondance partielle de texte et met à jour les résultats de la recherche au fur et à mesure de la saisie.

## <a name="see-also"></a>Voir aussi
 Informations de référence sur les [Propriétés de projet](../../ide/reference/project-properties-reference.md) [Personnalisation des dispositions de fenêtres](../../ide/customizing-window-layouts-in-visual-studio.md)
