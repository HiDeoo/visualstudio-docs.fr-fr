---
title: Nœuds de constante | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c798a50-a2d7-459b-9879-ad4ad8290c9b
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0b062f6190213fc2b18670f50fdd527c4c3f212a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49260063"
---
# <a name="constant-nodes"></a>Nœuds constants
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans le concepteur de nuanceur, les nœuds de constante représentent les valeurs littérales et les attributs de sommets interpolés dans les calculs de nuanceur de pixels. Comme les attributs de sommets sont interpolés (et donc différents pour chaque pixel), chaque instance de nuanceur de pixels reçoit une version différente de la constante. Ce faisant, chaque pixel a une apparence unique.  
  
## <a name="vertex-attribute-interpolation"></a>Interpolation des attributs de sommets  
 L’image d’une scène 3D d’un jeu ou d’une application est réalisée en transformant mathématiquement plusieurs objets, qui sont définis par des sommets, des attributs de sommets et des définitions de primitives, en pixels à l’écran. Toutes les informations requises pour donner à un pixel son apparence unique sont fournies par le biais des attributs de sommets, qui sont fusionnés en fonction de la proximité du pixel avec les différents sommets qui composent sa *primitive*. Une primitive est un élément de rendu de base, autrement dit, une forme simple comme un point, une ligne ou un triangle. Un pixel très proche d’un des sommets reçoit des constantes qui sont pratiquement identiques à ce sommet, mais un pixel espacé uniformément entre tous les sommets d’une primitive reçoit des constantes qui sont la moyenne de ces sommets. Dans la programmation des graphiques, les constantes que les pixels reçoivent sont dites *interpolées*. Fournir des données de constantes aux pixels de cette façon produit une très bonne qualité visuelle tout en réduisant l’encombrement mémoire et les besoins en bande passante.  
  
 Même si chaque instance de nuanceur de pixels ne reçoit qu’un ensemble de valeurs de constantes et ne peut pas modifier ces valeurs, différentes instances de nuanceur de pixels reçoivent différents ensembles de données de constantes. Cette conception permet à un programme nuanceur de produire une sortie couleur différente pour chaque pixel de la primitive.  
  
## <a name="constant-node-reference"></a>Informations de référence des nœuds de constante  
  
|Nœud|Détails|Properties|  
|----------|-------------|----------------|  
|**Vecteur d’appareil photo**|Vecteur qui s’étend du pixel actuel à l’appareil photo dans l’espace universel.<br /><br /> Vous pouvez l’utiliser pour calculer les réflexions dans l’espace universel.<br /><br /> **Sortie**<br /><br /> `Output`: `float3`<br /> Vecteur du pixel actuel à l’appareil photo.|Aucun.|  
|**Constante de couleur**|Valeur de constante de couleur.<br /><br /> **Sortie**<br /><br /> `Output`: `float4`<br /> Valeur de la couleur.|**Sortie**<br /> Valeur de la couleur.|  
|**Constante**|Valeur scalaire de constante.<br /><br /> **Sortie**<br /><br /> `Output`: `float`<br /> Valeur scalaire.|**Sortie**<br /> Valeur scalaire.|  
|**Constante 2D**|Constante vectorielle à deux composants.<br /><br /> **Sortie**<br /><br /> `Output`: `float2`<br /> Valeur vectorielle.|**Sortie**<br /> Valeur vectorielle.|  
|**Constante 3D**|Constante vectorielle à trois composants.<br /><br /> **Sortie**<br /><br /> `Output`: `float3`<br /> Valeur vectorielle.|**Sortie**<br /> Valeur vectorielle.|  
|**Constante 4D**|Constante vectorielle à quatre composants.<br /><br /> **Sortie**<br /><br /> `Output`: `float4`<br /> Valeur de la couleur.|**Sortie**<br /> Valeur vectorielle.|  
|**Position normalisée**|Position du pixel actuel, exprimée en coordonnées normalisées de l’appareil.<br /><br /> Les valeurs de l’axe des abscisses et de l’axe des ordonnées sont comprises dans la plage [-1, 1], la valeur de la coordonnée z est comprise dans la plage [0, 1], et le composant w contient la valeur de profondeur de point dans l’espace d’affichage ; w n’est pas normalisé.<br /><br /> **Sortie**<br /><br /> `Output`: `float4`<br /> Position du pixel actuel.|Aucun.|  
|**Couleur du point**|Couleur diffuse du pixel actuel, qui est une combinaison des attributs de couleur diffuse de matériau et de couleur de sommet.<br /><br /> **Sortie**<br /><br /> `Output`: `float4`<br /> Couleur diffuse du pixel actuel.|Aucun.|  
|**Profondeur de point**|Profondeur du pixel actuel dans l’espace d’affichage.<br /><br /> **Sortie**<br /><br /> `Output`: `float`<br /> Profondeur du pixel actuel.|Aucun.|  
|**Profondeur de point normalisée**|Profondeur du pixel actuel, exprimée en coordonnées normalisées de l’appareil.<br /><br /> La valeur du résultat est comprise dans la plage [0, 1].<br /><br /> **Sortie**<br /><br /> `Output`: `float`<br /> Profondeur du pixel actuel.|Aucun.|  
|**Position à l’écran**|Position du pixel actuel, exprimée en coordonnées d’écran.<br /><br /> Les coordonnées d’écran sont basées sur la fenêtre d’affichage actuelle. Les composants x et y contiennent les coordonnées d’écran, le composant z contient la profondeur normalisée dans la plage [0, 1], et le composant w contient la valeur de profondeur dans l’espace d’affichage.<br /><br /> **Sortie**<br /><br /> `Output`: `float4`<br /> Position du pixel actuel.|Aucun.|  
|**Normale de surface**|Normale de surface du pixel actuel dans l’espace d’objets.<br /><br /> Vous pouvez l’utiliser pour calculer les contributions de l’éclairage et les réflexions dans l’espace d’objets.<br /><br /> **Sortie**<br /><br /> `Output`: `float3`<br /> Normale de surface du pixel actuel.|Aucun.|  
|**Vecteur d’appareil photo de l’espace tangent**|Vecteur qui s’étend du pixel actuel à l’appareil photo dans l’espace tangent.<br /><br /> Vous pouvez l’utiliser pour calculer les réflexions dans l’espace tangent.<br /><br /> **Sortie**<br /><br /> `Output`: `float3`<br /> Vecteur du pixel actuel à l’appareil photo.|Aucun.|  
|**Direction de la lumière de l’espace tangent**|Vecteur qui définit la direction dans laquelle la lumière est diffusée depuis une source de lumière dans l’espace tangent du pixel actuel.<br /><br /> Vous pouvez l’utiliser pour calculer les contributions spéculaires et d’éclairage dans l’espace tangent.<br /><br /> **Sortie**<br /><br /> `Output`: `float3`<br /> Vecteur du pixel actuel à une source de lumière.|Aucun.|  
|**Normale universelle**|Normale de surface du pixel actuel dans l’espace universel.<br /><br /> Vous pouvez l’utiliser pour calculer les contributions de l’éclairage et les réflexions dans l’espace universel.<br /><br /> **Sortie**<br /><br /> `Output`: `float3`<br /> Normale de surface du pixel actuel.|Aucun.|  
|**Position universelle**|Position du pixel actuel dans l'espace universel.<br /><br /> **Sortie**<br /><br /> `Output`: `float4`<br /> Position du pixel actuel.|Aucun.|



