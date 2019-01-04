---
title: Étendre des diagrammes de dépendance
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a467366ca470c17c0f52bd72ae17e766bcb284d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53889317"
---
# <a name="extend-dependency-diagrams"></a>Étendre des diagrammes de dépendance
Vous pouvez écrire du code pour créer et mettre à jour des diagrammes de dépendance et pour valider la structure de votre code de programme par rapport aux diagrammes de dépendance dans Visual Studio. Vous pouvez ajouter des commandes qui s’affichent dans le menu contextuel des diagrammes, personnaliser les mouvements de glisser-déplacer et accéder au modèle de couche à partir de modèles de texte. Vous pouvez empaqueter ces extensions dans une extension d’intégration Visual Studio (VSIX) et les distribuer à d’autres utilisateurs de Visual Studio.

 Pour plus d’informations sur les diagrammes de dépendance, consultez :

-   [Diagrammes de dépendance : Référence](../modeling/layer-diagrams-reference.md)

-   [Diagrammes de dépendance : Instructions](../modeling/layer-diagrams-guidelines.md)

-   [Créer des diagrammes de dépendance à partir de votre code](../modeling/create-layer-diagrams-from-your-code.md)

-   [Validation du code avec des diagrammes de dépendance](../modeling/validate-code-with-layer-diagrams.md)

##  <a name="prereqs"></a> Spécifications
 Vous devez avoir installé les éléments suivants sur l’ordinateur où vous voulez développer vos extensions de couche :

-   Visual Studio

-   [Kit de développement logiciel Visual Studio](../extensibility/visual-studio-sdk.md)

-   SDK Modeling pour Visual Studio


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]


 Une version appropriée de Visual Studio doit être installée sur l’ordinateur où vous voulez exécuter vos extensions de couche. Pour plus d’informations, consultez [déployer une extension de modèle de couche](../modeling/deploy-a-layer-model-extension.md).

 Pour connaître les versions de Visual Studio prennent en charge les diagrammes de dépendance, consultez [versions prises en charge pour l’architecture et les outils de modélisation](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="in-this-section"></a>Dans cette section
 [Ajout de commandes et de mouvements aux diagrammes de dépendance](../modeling/add-commands-and-gestures-to-layer-diagrams.md)

 [Ajout d’une validation d’architecture personnalisée aux diagrammes de dépendance](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)

 [Ajout de propriétés personnalisées à des diagrammes de dépendance](../modeling/add-custom-properties-to-layer-diagrams.md)

 [Parcourir et mettre à jour les modèles de couche dans le code du programme](../modeling/navigate-and-update-layer-models-in-program-code.md)

 [Déployer une extension de modèle de couche](../modeling/deploy-a-layer-model-extension.md)

 [Dépannage des extensions pour des diagrammes de dépendance](../modeling/troubleshoot-extensions-for-layer-diagrams.md)

## <a name="see-also"></a>Voir aussi

- [Diagrammes de dépendance : Référence](../modeling/layer-diagrams-reference.md)
- [Diagrammes de dépendance : Instructions](../modeling/layer-diagrams-guidelines.md)
- [Créer des diagrammes de dépendance à partir de votre code](../modeling/create-layer-diagrams-from-your-code.md)
- [Validation du code avec des diagrammes de dépendance](../modeling/validate-code-with-layer-diagrams.md)
