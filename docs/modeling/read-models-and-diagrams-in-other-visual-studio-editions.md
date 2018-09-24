---
title: Lire des modèles et des diagrammes dans d'autres éditions de Visual Studio
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- models, versions of Visual Studio
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 420a17dbac9e0a3bf10b4c92baa108067ad44949
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43775579"
---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>Lire des modèles et des diagrammes dans d'autres éditions de Visual Studio
Quand vous ouvrez un modèle dans une version de Visual Studio qui ne prend pas en charge la création de modèle, le modèle s'ouvre en mode lecture seule. Dans ce mode, vous pouvez modifier la disposition des diagrammes, mais vous ne pouvez pas modifier le modèle.

 Pour connaître les versions de Visual Studio prennent en charge la création de modèles, consultez [versions prises en charge pour l’architecture et les outils de modélisation](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="obtaining-access-to-a-model-and-diagrams"></a>Obtention de l'accès à un modèle et à des diagrammes
 Pour lire un diagramme de dépendances, vous devez tout d’abord utiliser Visual Studio pour ouvrir le projet de modélisation et puis ouvrez le schéma qu’il contient.

 Pour cette raison, si vous souhaitez lire un diagramme de dépendances, vous devez également accéder au projet de modélisation dans lequel il a été créé. Pour cela, vous pouvez soit accéder au projet à partir de [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)], soit obtenir une copie des fichiers du projet.

> [!NOTE]
>  Cela ne s'applique pas aux cartes de code et aux diagrammes de classe .NET générés à partir du code. Ces diagrammes peuvent être affichés indépendamment d'un projet de modélisation.

 Pour lire un diagramme de dépendances, l’ensemble minimal de fichiers dont vous avez besoin est la suivante :

-   Les deux fichiers de diagrammes pour le diagramme que vous souhaitez lire, par exemple, **MyDiagram.classdiagram and MyDiagram.classdiagram.layout**.

    > [!NOTE]
    >  Pour les diagrammes de dépendance, vous devez également avoir le fichier nommé _Mondiagramme_**. layerdiagram.suppressions**.

-   Fichier de projet de modélisation (**MyModel.modelproj**)

-   Le fichier de modèle racine (**ModelDefinition\MyModel.uml**)

-   Les fichiers de package pour tout package référencé dans le diagramme (**ModelDefinition\MyPackage.UML**)

## <a name="changes-that-you-can-make-in-read-only-mode"></a>Modifications que vous pouvez apporter en mode lecture seule
 Si vous ouvrez un modèle et ses diagrammes dans une version de Visual Studio qui ne prend pas en charge la création de modèles, vous ne pouvez pas modifier le modèle. Autrement dit, vous ne pouvez pas modifier les éléments et les relations qui sont affichés dans les diagrammes ou dans l'Explorateur de modèles. En revanche, vous pouvez apporter certaines modifications à la disposition des diagrammes. Vous pouvez :

-   réorganiser les formes et connecteurs dans le diagramme ;

-   développer et réduire des formes.

 Vous pouvez enregistrer ces modifications. Si vous souhaitez rendre visibles à d’autres utilisateurs vos modifications, vous devez envoyer au moins la mise à jour **.layout** fichiers.

##  <a name="RelatedTopics"></a> Rubriques connexes

|Titre|Description|
|-----------|-----------------|
|[Diagrammes de dépendance : référence](../modeling/layer-diagrams-reference.md)|Un diagramme de couche montre la structure d'une architecture existante ou proposée. Quand du code est écrit, il peut être validé automatiquement par rapport à un diagramme de couche.|

## <a name="see-also"></a>Voir aussi

- [Créer des modèles pour votre application](../modeling/create-models-for-your-app.md)