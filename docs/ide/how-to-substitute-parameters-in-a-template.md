---
title: Ajouter des paramètres de nom à des modèles de projet et d’élément
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- template parameters
- template parameters, substituting
- Visual Studio templates, using parameters
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 93e553338478bcdead9e283323348b02ac73eaac
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55031758"
---
# <a name="how-to-substitute-parameters-in-a-template"></a>Procédure : Substituer des paramètres dans un modèle

Les paramètres de modèle vous permettent de remplacer des identificateurs, comme des noms de classes et des espaces de noms, pendant la création d’un fichier à partir d’un modèle. Vous pouvez ajouter des paramètres de modèle à des modèles existants ou créer vos propres modèles avec des paramètres de modèle.

Les paramètres d’un modèle s’écrivent au format $*parameter*$. Pour obtenir la liste complète des paramètres de modèle, consultez [Paramètres de modèle](../ide/template-parameters.md).

La section suivante vous montre comment modifier un modèle pour remplacer le nom d’un espace de noms par le « nom du projet sécurisé ».

## <a name="to-use-a-parameter-to-replace-the-namespace-name"></a>Pour utiliser un paramètre pour remplacer le nom de l’espace de noms

1. Ajoutez le paramètre dans l'un ou plusieurs des fichiers de code du modèle. Par exemple :

    ```csharp
    namespace $safeprojectname$
    ```

1. Dans le fichier *.vstemplate* du modèle, localisez l’élément `ProjectItem` qui inclut ce fichier.

1. Affectez à l’attribut `ReplaceParameters` la valeur `true` pour l’élément `ProjectItem` :

    ```xml
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>
    ```

## <a name="see-also"></a>Voir aussi

- [Créer des modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)
- [Paramètres de modèle](../ide/template-parameters.md)
- [Informations de référence sur les schémas de modèles Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [ProjectItem, élément (modèles d’élément Visual Studio)](../extensibility/projectitem-element-visual-studio-item-templates.md)