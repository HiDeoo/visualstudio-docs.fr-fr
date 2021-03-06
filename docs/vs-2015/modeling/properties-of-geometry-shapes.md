---
title: Propriétés des formes Geometry | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.geometryshape
helpviewer_keywords:
- Domain-Specific Language, geometry shape
ms.assetid: 3993a23e-eab3-4ceb-b475-c395d5992bfc
caps.latest.revision: 23
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 10b6d282475d3298f15319d89684f9b042bee5f6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72671398"
---
# <a name="properties-of-geometry-shapes"></a>Propriétés des formes de géométrie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez utiliser des formes géométriques pour spécifier la façon dont les instances de classes de domaine sont affichées dans un langage spécifique à un domaine. Pour plus d’informations, consultez [comment définir un langage spécifique à un domaine](../modeling/how-to-define-a-domain-specific-language.md). Pour plus d’informations sur l’utilisation de ces propriétés, consultez [personnalisation et extension d’un langage spécifique à un domaine](../modeling/customizing-and-extending-a-domain-specific-language.md).

 Les propriétés des formes géométriques sont répertoriées dans le tableau suivant.

|Propriété|Description|Default|
|--------------|-----------------|-------------|
|Couleur de remplissage|Couleur de remplissage de cette forme.|White|
|Mode dégradé de remplissage|Mode de remplissage dégradé de cette forme (horizontal, vertical, diagonale vers l’avant, diagonales arrière ou aucune).|Horizontal|
|Géométrie|Géométrie de cette forme (Rectangle, Rectangle arrondi, ellipse ou cercle).|Rectangle|
|A des points de connexion par défaut|Si `True` la forme est, la forme utilise les points de connexion du haut, du bas, de gauche et de droite dans le concepteur généré.|Faux|
|Couleur de contour|Couleur de contour de cette forme.|Noir|
|Style de tiret de contour|Style de tiret de contour de cette forme (plein, tiret, point, tiret point, tiret point point ou personnalisé).|Unie|
|Épaisseur du contour|Épaisseur de contour de cette forme.|0,03125|
|Couleur du texte|Couleur utilisée pour les éléments décoratifs de texte associés à cette forme.|Noir|
|Modificateur d'accès|Modificateur d’accès de la classe (public ou Internal).|Public|
|Attributs personnalisés|Utilisé pour ajouter des attributs à la classe de code source qui est générée pour cette forme.|\<none>|
|Génère un doublon dérivé|Si `True` la valeur est, une classe de base et une classe partielle (pour prendre en charge la personnalisation via des substitutions) sont générées. Pour plus d’informations, consultez [substitution et extension des classes générées](../modeling/overriding-and-extending-the-generated-classes.md).|Faux|
|A un constructeur personnalisé|Si `True` , un constructeur personnalisé est fourni dans le code source. Pour plus d’informations, consultez [substitution et extension des classes générées](../modeling/overriding-and-extending-the-generated-classes.md).|Faux|
|Modificateur d’héritage|Décrit le type d’héritage de la classe de code source qui est généré à partir de la forme ( `none` , `abstract` ou `sealed` ).|Aucun|
|Forme Geometry de base|Classe de base de cette forme.|(aucun)|
|Nom|Nom de cette forme.|Nom actuel|
|Espace de noms|Espace de noms affilié à cette forme.|Espace de noms actuel|
|Type d’info-bulle|Comment l’info-bulle est définie (Fixed, variable ou None). Si elle est fixe, la valeur de la `Fixed Tooltip Text` propriété est utilisée comme info-bulle ; si la variable est, l’info-bulle est définie dans le code personnalisé.|None|
|Notes|Notes informelles associées à cet élément.|\<none>|
|Hauteur initiale|Hauteur initiale de cette forme, en pouces.|1|
|Largeur initiale|Largeur initiale de cette forme, en pouces.|1.5|
|Couleur de remplissage exposée en tant que propriété<br /><br /> Mode dégradé de remplissage exposé<br /><br /> Couleur de contour exposée en tant que propriété<br /><br /> Exposé du style de tiret de contour en tant que propriété<br /><br /> Exposer l’épaisseur de la structure en tant que propriété<br /><br /> Expose la couleur de texte|Si `True` la valeur est, l’utilisateur peut définir la propriété déclarée d’une forme. Pour ce faire, cliquez avec le bouton droit sur la définition de la forme, puis cliquez sur **Ajouter exposé**.|Faux|
|Description|Description utilisée pour documenter le concepteur généré.|\<none>|
|Nom d’affichage|Nom qui sera affiché dans le concepteur généré pour cette forme.|\<none>|
|Texte d’info-bulle fixe|Texte utilisé pour une info-bulle fixe.|\<none>|
|Help Keyword|Mot clé utilisé pour indexer l’aide F1 pour cette forme.|\<none>|

## <a name="see-also"></a>Voir aussi
 [Glossaire des Outils Domain-Specific Language](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
