---
title: 'Comment : créer un nuanceur de couleur de base | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: c301328a-079a-49e8-b688-4749c01657c0
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 90f27e2359954e56a5b3d86bfc31883d4f29c44d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72664586"
---
# <a name="how-to-create-a-basic-color-shader"></a>Comment : créer un nuanceur de couleur de base
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ce document indique comment utiliser le concepteur de nuanceur et DGSL (Directed Graph Shader Language) pour créer un nuanceur de couleur plat. Ce nuanceur définit la couleur finale sur une valeur de couleur RVB de constante.

 Ce document illustre ces activités :

- Suppression de nœuds d’un graphique

- Ajout de nœuds à un graphique

- Définition de propriétés de nœud

- Connexion de nœuds

## <a name="creating-a-flat-color-shader"></a>Création d’un nuanceur de couleur plat
 Vous pouvez implémenter un nuanceur de couleur plat en écrivant la valeur de couleur d’une constante de couleur RVB sur la couleur de sortie finale.

 Avant de commencer, veillez à ce que la fenêtre **Propriétés** et la **Boîte à outils** soient affichées.

#### <a name="to-create-a-flat-color-shader"></a>Pour créer un nuanceur de couleur plat

1. Créez un shader DGSL à utiliser. Pour plus d’informations sur l’ajout d’un nuanceur DGSL à votre projet, consultez la section Prise en main de l’article [Concepteur de nuanceur](../designers/shader-designer.md).

2. Supprimez le nœud **Couleur du point**. À l’aide de l’outil **Sélection**, sélectionnez le nœud **Couleur du point**, puis, dans la barre de menus, choisissez **Modifier**, **Supprimer**.

3. Ajoutez un nœud **Constante de couleur** au graphique. Dans la **Boîte à outils**, sous **Constantes**, sélectionnez **Constante de couleur** et déplacez-la vers l’aire de conception.

4. Spécifiez une valeur de couleur pour le nœud **Constante de couleur**. À l’aide de l’outil **Sélection**, sélectionnez le nœud **Constante de couleur**, puis, dans la fenêtre **Propriétés**, dans la propriété **Sortie**, spécifiez une valeur de couleur. Pour l’orange, spécifiez la valeur (1,0, 0,5, 0,2, 1,0).

5. Connectez la constante de couleur à la couleur finale. Pour créer les connexions, déplacez le terminal **RVB** du nœud **Constante de couleur** vers le terminal **RVB** du nœud **Couleur finale**, puis le terminal **Alpha** du nœud **Constante de couleur** vers le terminal **Alpha** du nœud **Couleur finale**. Ces connexions définissent la couleur finale sur la constante de couleur définie à l’étape précédente.

   L’illustration suivante présente le graphique du nuanceur terminé ainsi qu’un aperçu du nuanceur appliqué à un cube.

> [!NOTE]
> Une couleur orange a été spécifiée dans l’illustration pour mettre en évidence l’effet du nuanceur.

 ![Graphique du nuanceur et résultat sur un modèle de 3&#45;D](../designers/media/digit-flat-color-effect.png "Chiffre-effet à couleur plate")

 Certaines formes peuvent fournir de meilleurs aperçus pour certains nuanceurs. Pour plus d’informations sur l’aperçu des nuanceurs dans le concepteur de nuanceur, consultez l’article [Concepteur de nuanceur](../designers/shader-designer.md).

## <a name="see-also"></a>Voir aussi
 [Comment : appliquer un nuanceur à un modèle 3D](../designers/how-to-apply-a-shader-to-a-3-d-model.md) [procédure : exporter](../designers/how-to-export-a-shader.md) des [nœuds](../designers/shader-designer-nodes.md) du concepteur de nuanceur Shader [Designer](../designers/shader-designer.md)
