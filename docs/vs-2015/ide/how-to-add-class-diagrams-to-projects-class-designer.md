---
title: Guide pratique pour ajouter des diagrammes de classes aux projets (Concepteur de classes) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- class diagrams, creating
- Class Designer [Visual Studio], opening
ms.assetid: 0eac1b54-2711-4e4b-9654-a0c429c08c8f
caps.latest.revision: 43
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: f1a0d10dabdace7ef7ab3805a59b892548cf6556
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72645519"
---
# <a name="how-to-add-class-diagrams-to-projects-class-designer"></a>Comment : ajouter des diagrammes de classes aux projets (Concepteur de classes)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour concevoir, modifier et refactoriser des classes et d'autres types, ajoutez un diagramme de classes à votre projet Visual C# .NET, Visual Basic .NET ou C++. Pour visualiser différentes parties du code d'un projet, ajoutez plusieurs diagrammes de classes à ce dernier.

 Vous ne pouvez pas créer de diagrammes de classes à partir de projets qui partagent du code dans plusieurs applications. Pour créer des diagrammes de classes UML, consultez [Créer des projets et des diagrammes de modélisation UML](../modeling/create-uml-modeling-projects-and-diagrams.md).

### <a name="to-add-a-blank-class-diagram-to-a-project"></a>Pour ajouter un diagramme de classes vide à un projet

1. Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le nom du projet. Choisissez **Ajouter un nouvel élément** ou **Ajouter**, **Nouvel élément**.

2. Dans la liste des modèles, choisissez **Diagramme de classes**. Pour des projets Visual C++, regardez sous **Modèles**, puis sous **Utilitaire** pour trouver ce modèle.

     Le diagramme de classes s’ouvre dans le Concepteur de classes et apparaît comme fichier avec l’extension .cd dans l’Explorateur de solutions dans la hiérarchie de projet. Utilisez la boîte à outils Concepteur de classes pour faire glisser des formes et des lignes vers le diagramme.

3. Pour ajouter plusieurs diagrammes de classes, répétez les étapes de la procédure.

### <a name="to-add-a-class-diagram-based-on-existing-types"></a>Pour ajouter un diagramme de classes basé sur des types existants

1. Dans l’Explorateur de solutions, ouvrez le menu contextuel du fichier de classe, puis choisissez **Afficher le diagramme de classes**.

     - ou -

     Dans **Affichage de classes**, ouvrez le menu contextuel de l’espace de noms ou du type, puis choisissez **Afficher le diagramme de classes**.

### <a name="to-display-the-contents-of-a-complete-project-in-a-class-diagram"></a>Pour afficher le contenu d'un projet complet dans un diagramme de classes

1. Dans l’Explorateur de solutions ou dans Affichage de classes, cliquez avec le bouton droit sur le projet et choisissez **Afficher**, puis choisissez **Afficher le diagramme de classes**.

     Un diagramme de classes est alors créé et rempli automatiquement.

## <a name="see-also"></a>Voir aussi
 [Comment : créer des types à l’aide de concepteur de classes](../ide/how-to-create-types-by-using-class-designer.md) [Comment : afficher des types existants (Concepteur de classes)](../ide/how-to-view-existing-types-class-designer.md) [conception de Classes et de types (Concepteur de classes)](../ide/designing-classes-and-types-class-designer.md) [affichage des types et des relations (Concepteur de classes)](../ide/viewing-types-and-relationships-class-designer.md) [utilisation des diagrammes de classes (Concepteur de classes)](../ide/working-with-class-diagrams-class-designer.md)
