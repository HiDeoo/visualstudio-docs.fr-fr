---
title: 'Comment : appliquer un nuanceur à un modèle 3D | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a3877bd6-abd8-4a9d-842c-6848b6c2f335
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 15d88f52b3af3a3e4502c618280107a882761259
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72664615"
---
# <a name="how-to-apply-a-shader-to-a-3-d-model"></a>Comment : appliquer un nuanceur à un modèle 3D
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ce document indique comment utiliser l’éditeur de modèle pour appliquer un nuanceur DGSL (Directed Graph Shader Language) à un modèle 3D.

 Ce document illustre cette activité :

- Application d’un nuanceur à un modèle 3D

## <a name="applying-a-shader-to-a-3-d-model"></a>Application d’un nuanceur à un modèle 3D
 Vous pouvez appliquer un effet de nuanceur à un modèle 3D pour lui donner une apparence intéressante.

 Avant de commencer, assurez-vous que la fenêtre **Propriétés** est affichée.

#### <a name="to-apply-a-shader-to-a-3-d-model"></a>Pour appliquer un nuanceur à un modèle 3D

1. Commencez par une scène 3D contenant un ou plusieurs modèles. Si vous ne disposez pas d’une scène 3D appropriée, créez-en une comme décrit dans [Comment : créer un modèle 3D de base](../designers/how-to-create-a-basic-3-d-model.md). Vous devez également disposer d’un nuanceur DGSL que vous pouvez appliquer au modèle. Si vous ne disposez pas d’un nuanceur approprié, créez-en un en suivant la description de l’article [Comment : créer un nuanceur de couleur de base](../designers/how-to-create-a-basic-color-shader.md) et veillez à l’enregistrer dans un fichier avant de continuer.

2. En mode **Sélection**, sélectionnez le modèle que vous souhaitez appliquer au nuanceur, puis, dans la fenêtre **Propriétés**, dans la propriété **Nom de fichier** du groupe de propriétés **Effet**, spécifiez le nuanceur DGSL à appliquer au modèle.

   Exemple de modèle auquel l’effet de couleur de base est appliqué :

   ![3&#45;scène D montrant l’effet de couleur de base](../designers/media/digit-3d-model-effect.png "Digit-3D-Model-Effect")

   Après avoir appliqué un nuanceur à un modèle, vous pouvez l’ouvrir dans le Concepteur de nuanceur en sélectionnant le modèle, puis, dans la fenêtre **Propriétés**, dans la propriété **(Avancé)** du groupe de propriétés **Effet**, en choisissant le bouton de sélection (**... **).

## <a name="see-also"></a>Voir aussi
 [Comment : créer un modèle 3D de base](../designers/how-to-create-a-basic-3-d-model.md) [Comment : créer un modèle de nuanceur de couleur de base](../designers/how-to-create-a-basic-color-shader.md) [Model Editor](../designers/model-editor.md) [Concepteur de nuanceur](../designers/shader-designer.md)
