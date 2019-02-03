---
title: 'Procédure : Exporter une Texture qui contient des Mipmaps | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 3d1ad14b-44fb-4cf0-a995-5e2f60026524
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 732fa9a5d32916545b281a006cbeeaa93771f3ec
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54754334"
---
# <a name="how-to-export-a-texture-that-contains-mipmaps"></a>Procédure : Exporter une texture qui contient des mipmaps
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Le pipeline de contenus d’image peut générer des mipmaps à partir d’une image source dans la phase de génération de votre projet. Quand vous n’avez pas besoin de spécifier le contenu de l’image de chaque niveau MIP manuellement, comme cela peut être nécessaire pour obtenir certains effets, la génération de mipmaps au moment de la génération garantit que le contenu des mipmaps n’est jamais désynchronisé et élimine la réduction des performances découlant de la génération de mipmaps au moment de l’exécution.  
  
 Ce document illustre ces activités :  
  
-   Configuration de l’image source à traiter par le pipeline de contenus d’image.  
  
-   Configuration du pipeline de contenus d’image pour générer des mipmaps.  
  
## <a name="exporting-mipmaps"></a>Exportation de mipmaps  
 Le mipmapping fournit automatiquement le niveau de détail de l’espace à l’écran pour les surfaces texturées dans une application ou un jeu 3D. Il améliore les performances de rendu d’un jeu ou d’une application en précalculant des versions sous-échantillonnées d’une texture. Ainsi, une texture entière ne doit pas être sous-échantillonnée chaque fois qu’elle est échantillonnée.  
  
#### <a name="to-export-a-texture-that-has-mipmaps"></a>Pour exporter une texture contenant des mipmaps  
  
1. Commencez par une texture de base. Chargez un fichier image existant ou créez-en un comme décrit dans [Guide pratique pour créer une texture de base](../designers/how-to-create-a-basic-texture.md). Pour prendre en charge les mipmaps, spécifiez une texture dont la largeur et la hauteur ont pour valeur la même puissance de deux (par exemple : 64x64, 256x256 ou 512x512).  
  
2. Configurez le fichier de texture que vous venez de créer pour qu’il soit traité par le pipeline de contenus d’image. Dans l’**Explorateur de solutions**, ouvrez le menu contextuel pour le fichier de texture que vous venez de créer puis choisissez **Propriétés**. Dans la page **Propriétés de configuration**, **Général**, définissez la propriété **Type d’élément** sur **Pipeline de contenus d’image**. Vérifiez que la propriété **Contenu** est définie sur **Oui** et que **Exclure de la génération** est défini sur **Non**, puis choisissez le bouton **Appliquer**. La page des propriétés de configuration du **Pipeline de contenus d’image** apparaît.  
  
3. Configurez le pipeline de contenus d’image pour générer des mipmaps. Dans la page **Propriétés de configuration**, **Pipeline de contenus d’image**, **Général**, affectez à la propriété **Générer des mips** la valeur **Oui (/generatemips)**.  
  
4. Sélectionnez le bouton **OK** .  
  
   Quand vous générez le projet, le pipeline de contenus d’image convertit l’image source du format de travail dans le format de sortie que vous avez spécifié, notamment les niveaux MIP, et le résultat est copié dans le répertoire de sortie du projet.
