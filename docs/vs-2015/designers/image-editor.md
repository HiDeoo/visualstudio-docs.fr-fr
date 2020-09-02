---
title: Éditeur d’images | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- vs.graphics.designer.imageeditor
- vs.graphics.imageeditor
ms.assetid: fc71d502-c548-4863-8afc-12a1d3ec90d4
caps.latest.revision: 47
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0c30e6f1be9daf07f3685c06b21ed9d507b86a07
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72664392"
---
# <a name="image-editor"></a>éditeur d’images
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ce document décrit comment utiliser l’éditeur d’images de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pour afficher et modifier des ressources de texture et d’image.

 Vous pouvez utiliser l’éditeur d’images pour travailler avec les types de formats de texture et d’image enrichis qui sont utilisés dans le développement d’applications DirectX : ceci inclut la prise en charge des formats de fichiers et des codages des couleurs répandus, des fonctionnalités comme les canaux alpha et le mappage MIP, ainsi que de nombreux formats de texture fortement compressés et avec accélération matérielle pris en charge par DirectX.

## <a name="supported-formats"></a>Formats pris en charge
 L’éditeur d’images prend en charge les formats d’image suivants :

|Nom de format|Extension de nom de fichier|
|-----------------|-------------------------|
|Format PNG|.png|
|JPEG|.jpg, .jpeg, .jpe, .jfif|
|Direct Draw Surface|.dds|
|Format GIF|.gif|
|Bitmap|.bmp, .dib|
|Format TIFF (Tagged Image File Format)|.tif, .tiff|
|TGA (Targa)|.tga|

## <a name="getting-started"></a>Mise en route
 Cette section décrit comment ajouter une image à votre projet [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] et comment la configurer selon vos besoins.

#### <a name="to-add-an-image-to-your-project"></a>Pour ajouter une image à votre projet

1. Dans l’**Explorateur de solutions**, ouvrez le menu contextuel du projet auquel vous souhaitez ajouter l’image puis choisissez **Ajouter**, **Nouvel élément**.

2. Dans la boîte de dialogue **Ajouter un nouvel élément**, sous **Installé**, sélectionnez **Graphiques**, puis sélectionnez un format de fichier approprié pour l’image. Pour plus d’informations sur la façon de choisir un format de fichier en fonction de vos besoins, consultez la section suivante.

3. Spécifiez le **Nom** du fichier image, ainsi que l’**Emplacement** où vous voulez le créer.

4. Choisissez le bouton **Ajouter**.

### <a name="choosing-the-image-format"></a>Choix du format d’image
 Selon la façon dont vous prévoyez d’utiliser l’image, certains formats de fichiers peuvent être plus appropriés que d’autres. Par exemple, certains formats ne prennent pas en charge une fonctionnalité dont vous avez besoin, comme la transparence ou un format de couleur spécifique, ou ils peuvent ne pas fournir une compression appropriée pour le type de contenu de l’image que vous avez prévu.

 Les informations suivantes peuvent vous aider à choisir un format d’image qui répond à vos besoins.

 **Image bitmap (.bmp)** Format d’image bitmap. Format d’image non compressé qui prend en charge les couleurs sur 24 bits. Le format bitmap ne prend pas en charge la transparence.

 **Image GIF (.gif)** Format d’image GIF (Graphics Interchange Format). Un format d’image compressé LZW sans perte, qui prend en charge jusqu’à 256 couleurs. Inapproprié pour les photographies et les images qui ont une quantité significative de détails en couleurs, mais offre de bons taux de compression pour les images avec peu de couleurs qui présentent un degré élevé de cohérence des couleurs.

 **Image JPG (.jpg)** Format d’image JPEG (Joint Photographic Experts Group). Un format d’image fortement compressée avec des pertes de données, qui prend en charge les couleurs sur 24 bits et convient pour la compression à usage général d’images qui présentent un degré élevé de cohérence des couleurs.

 **Image PNG (.png)** Format d’image PNG (Portable Network Graphics). Un format d’image modérément compressé sans pertes de données, qui prend en charge les couleurs sur 24 bits et la transparence alpha. Il convient pour les images naturelles et artificielles, mais n’offre pas un taux de compression aussi bon que les formats avec pertes de données, comme JPG ou GIF.

 **Image TIFF (.tif)** Format d’image TIFF ou TIF (Tagged Image File Format). Un format d’image flexible qui prend en charge plusieurs schémas de compression.

 **Texture DDS (.dds)** Format de texture DDS (DirectDraw Surface). Un format de texture fortement compressé sans pertes de données, qui prend en charge les couleurs sur 24 bits et la transparence alpha. Son taux de compression peut atteindre 8:1. Il est basé sur la compression de texture S3, qui peut être décompressée sur le matériel graphique.

 **Image TGA (.tga)** Format d’image TGA (Truevision Graphics Adapter), également appelé Targa. Un format d’image avec compression RLE sans pertes de données, qui prend en charge les images avec mappage des couleurs (palette de couleurs) ou en couleurs directes, avec des couleurs jusqu’à 24 bits et transparence alpha. Inapproprié pour les photographies et les images qui ont une quantité significative de détails en couleurs, mais fournit de bons taux de compression pour les images qui ont de grandes surfaces de couleurs identiques.

### <a name="configuring-the-image"></a>Configuration de l’image
 Avant de commencer à travailler avec l’image que vous venez de créer, vous pouvez changer sa configuration par défaut. Par exemple, vous pouvez changer ses dimensions ou le format de couleur qu’elle utilise. Pour plus d’informations sur la configuration de ces propriétés et d’autres propriétés de l’image, consultez [Propriétés de l’image](#ImageProperties).

> [!NOTE]
> Avant d’enregistrer votre travail, veillez à définir la propriété **Format de couleur** si vous voulez utiliser un format spécifique. Si le format de fichier prend en charge la compression, vous pouvez ajuster les paramètres de compression quand vous enregistrez le fichier pour la première fois ou quand vous choisissez **Enregistrer sous**.

## <a name="working-with-the-image-editor"></a>Utilisation de l’éditeur d’images
 Cette section explique comment utiliser l’éditeur d’images pour modifier des textures et des images.

### <a name="image-editor-toolbars"></a>Barres d’outils de l’éditeur d’images
 Les barres d’outils de l’éditeur d’images contiennent des commandes qui vous aident à travailler avec des images.

 Les commandes qui affectent l’état de l’éditeur d’images se trouvent sur la barre d’outils **Mode de l’éditeur d’images**, qui contient aussi des commandes avancées. La barre d’outils se trouve le long du bord supérieur de l’aire de conception de l’éditeur d’images. Les outils de dessin se trouvent sur la barre d’outils l’**Éditeur d’images** le long du bord gauche de l’aire de conception de l’éditeur d’images.

 Voici la barre d’outils **Mode de l’éditeur d’images** :

 ![Barre d'outils modale de l'éditeur d'images.](../designers/media/digit-tre-modal-toolbar.png "-TRE-modal-Toolbar")

 Ce tableau décrit les éléments de la barre d’outils **Mode de l’éditeur d’images**, répertoriés dans l’ordre où ils figurent, de gauche à droite.

|Élément de la barre d'outils|Description|
|------------------|-----------------|
|**Select**|Permet de sélectionner une zone rectangulaire d’une image. Après avoir sélectionné une zone, vous pouvez la couper, la copier, la déplacer, la mettre à l’échelle, la faire pivoter, la retourner ou la supprimer. Quand il existe une sélection active, les outils de dessin affectent seulement la zone sélectionnée.|
|**Sélection irrégulière**|Permet de sélectionner une zone irrégulière d’une image. Après avoir sélectionné une zone, vous pouvez la couper, la copier, la déplacer, la mettre à l’échelle, la faire pivoter, la retourner ou la supprimer. Quand il existe une sélection active, les outils de dessin affectent seulement la zone sélectionnée.|
|**Sélection « Baguette magique »**|Permet de sélectionner une zone avec des couleurs similaires dans une image. La *tolérance*, c’est-à-dire la différence maximale entre des couleurs adjacentes pour laquelle elles sont considérées comme similaires, peut être configurée pour inclure une plage plus petite ou plus large de couleurs similaires. Après avoir sélectionné une zone, vous pouvez la couper, la copier, la déplacer, la mettre à l’échelle, la faire pivoter, la retourner ou la supprimer. Quand il existe une sélection active, les outils de dessin affectent seulement la zone sélectionnée.|
|**Panoramique**|Permet de déplacer l’image par rapport au cadre de la fenêtre. En mode **Panoramique**, sélectionnez un point sur l’image et déplacez-le.<br /><br /> Vous pouvez activer temporairement le mode **Panoramique** en appuyant sur la touche Ctrl et en la maintenant enfoncée.|
|**Zoom**|Permet l’affichage d’une image avec plus ou moins de détails par rapport au cadre de la fenêtre. En mode **Zoom**, sélectionnez un point dans l’image et déplacez-le vers la droite ou vers le bas pour effectuer un zoom avant, ou vers la gauche ou vers le haut pour effectuer un zoom arrière.<br /><br /> Vous pouvez effectuer un zoom avant ou arrière en appuyant sur la touche Ctrl et en la maintenant enfoncée, alors que vous utilisez la roulette de la souris, ou que vous appuyez sur le signe Plus (+) ou sur le signe Moins (-).|
|**Zoom sur la taille réelle**|Affiche l’image en utilisant une relation 1:1 entre les pixels de l’image et les pixels de l’écran.|
|**Zoom pour ajuster**|Affiche l’image entière dans le cadre de la fenêtre.|
|**Zoom sur la largeur**|Affiche la largeur entière de l’image dans le cadre de la fenêtre.|
|**Grid**|Active ou désactive la grille qui montre les limites des pixels. Il peut être nécessaire de faire un zoom avant pour faire apparaître la grille.|
|**Afficher le niveau MIP suivant**|Active le niveau MIP supérieur suivant dans une chaîne de mappage MIP. Le niveau MIP actif est affiché dans l’aire de conception. Cet élément est disponible seulement pour les textures qui ont des niveaux MIP.|
|**Afficher le niveau MIP précédent**|Active le niveau MIP inférieur dans une chaîne de mappage MIP. Le niveau MIP actif est affiché dans l’aire de conception. Cet élément est disponible seulement pour les textures qui ont des niveaux MIP.|
|**Canal rouge**<br /><br /> **Canal vert**<br /><br /> **Canal bleu**<br /><br /> **Canal alpha**|Active ou désactive le canal de couleur spécifique. **Remarque :** En activant ou en désactivant de façon systématique des canaux de couleur, vous pouvez isoler les problèmes liés à une ou plusieurs de ces couleurs. Par exemple, vous pourrez identifier une transparence alpha incorrecte.|
|**Contexte**|Active ou désactive l’affichage de l’arrière-plan à travers les parties transparentes de l’image. Vous pouvez configurer la façon dont l’arrière-plan s’affiche en choisissant parmi les options suivantes :<br /><br /> **Damier**<br /> Utilise une couleur verte avec la couleur d’arrière-plan spécifiée pour afficher l’arrière-plan sous la forme d’un modèle de damier. Vous pouvez utiliser cette option pour rendre les parties transparentes de l’image plus apparentes.<br /><br /> Arrière-plan blanc<br /> Utilise la couleur blanc pour afficher l’arrière-plan.<br /><br /> Arrière-plan noir<br /> Utilise la couleur noir pour afficher l’arrière-plan.<br /><br /> Animer l’arrière-plan<br /> Permet de déplacer le modèle de damier lentement selon un mouvement panoramique. Vous pouvez utiliser cette option pour rendre les parties transparentes de l’image plus apparentes.|
|**Propriétés**|Affiche ou masque alternativement la fenêtre **Propriétés**.|
|**Avancée**|Contient des commandes et des options supplémentaires.<br /><br /> **Filtres**<br /><br /> Fournit plusieurs filtres d’image courants : **Noir et blanc**, **Flou**, **Éclaircir**, **Obscurcir**, **Détection des bords**, **Relief**, **Inverser les couleurs**, **Ripple**, **Ton sépia** et **Accentuer**.<br /><br /> **Moteurs graphiques**<br /><br /> **Afficher avec D3D11**<br /> Utilise Direct3D 11 pour afficher l’aire de conception de l’éditeur d’images.<br /><br /> **Afficher avec D3D11WARP**<br /> Utilise la plateforme WARP (Windows Advanced Rasterization Platform) Direct3D 11 pour afficher l’aire de conception de l’éditeur d’images.<br /><br /> **outils**<br /><br /> **Symétrie horizontale**<br /> Transpose l’image autour de son axe horizontal (l’axe X).<br /><br /> **Symétrie verticale**<br /> Transpose l’image autour de son axe vertical (l’axe Y).<br /><br /> **Générer des mips**<br /> Génère des niveaux MIP pour une image. Si des niveaux MIP existent déjà, ils sont recréés à partir du niveau MIP le plus grand. Toutes les modifications qui ont été apportées à des niveaux MIP plus petits sont perdues. Pour enregistrer les niveaux MIP que vous avez générés, vous devez utiliser le format .dds pour enregistrer l’image.<br /><br /> **Visualiser**<br /><br /> **Fréquence d’images**<br /> Quand cette option est activée, elle affiche la fréquence d’images dans le coin supérieur droit de l’aire de conception. La fréquence d'images est le nombre d'images dessinées par seconde. **Conseil :**  Vous pouvez cliquer sur le bouton **avancé** pour réexécuter la dernière commande.|

 Voici la barre d’outils **Éditeur d’images**.

 ![Barre d'outils Éditeur d'images](../designers/media/digit-tre-toolbar.png "La barre d’outils digit-TRE")

 Le tableau suivant décrit les éléments de la barre d’outils **Éditeur d’images**, répertoriés dans l’ordre où ils figurent, de haut en bas.

|Élément de la barre d'outils|Description|
|------------------|-----------------|
|**Crayon**|Utilise la sélection de couleur active pour dessiner un trait sans lissage. Vous pouvez définir la couleur et l’épaisseur du trait dans la fenêtre **Propriétés**.|
|**Brush**|Utilise la sélection de couleur active pour dessiner un trait avec lissage. Vous pouvez définir la couleur et l’épaisseur du trait dans la fenêtre **Propriétés**.|
|**Aérographe**|Utilise la sélection active de couleur pour dessiner un trait avec lissage qui fusionne avec l’image et devient plus saturé en fonction du temps. Vous pouvez définir la couleur et l’épaisseur du trait dans la fenêtre **Propriétés**.|
|**Pipette**|Définit la sélection de couleur active sur la couleur du pixel sélectionné.|
|**Fill**|Utilise la sélection de couleur active pour remplir une zone de l’image. La zone affectée est définie comme le pixel où le remplissage est appliqué, ainsi que chaque pixel qui y est connecté par des pixels de la même couleur et qui est lui-même de la même couleur. Si le remplissage est appliqué dans une sélection active, la zone affectée est limitée par la sélection.<br /><br /> Par défaut, la sélection de couleur active est fusionnée avec la zone affectée de l’image en fonction de son composant alpha. Pour utiliser la sélection de couleur active pour remplacer la zone affectée, maintenez la touche Maj enfoncée quand vous utilisez l’outil de remplissage.|
|**Gomme**|Applique aux pixels la couleur entièrement transparente si l’image prend en charge un canal alpha. Sinon, applique aux pixels la couleur d’arrière-plan active.|
|**Ligne**, **Rectangle**, **Rectangle à coins arrondis**, **Ellipse**|Dessine une forme sur l’image. Vous pouvez définir la couleur et l’épaisseur du contour dans la fenêtre **Propriétés**.<br /><br /> Pour dessiner une primitive de largeur et de hauteur identiques, maintenez la touche Maj pendant que vous dessinez.|
|**Text**|Utilise la sélection de couleur de premier plan pour dessiner du texte. La couleur d’arrière-plan est déterminée par la sélection de couleur d’arrière-plan. Pour un arrière-plan transparent, la valeur alpha de la sélection de couleur d’arrière-plan doit être 0. Quand la zone de texte est active, vous pouvez définir si le texte est dessiné avec un trait avec lissage, et vous pouvez définir la **Valeur**, la **Police**, la **Taille**et le style (**Gras**, **Italique** ou **Souligné**) du texte dans la fenêtre **Propriétés**. Le contenu et l’apparence du texte sont finalisés une fois que la zone de texte n’est plus active.|
|**Faire pivoter**|Fait pivoter l’image de 90 degrés dans le sens des aiguilles d’une montre.|
|**Trim**|Découpe l’image au format de la sélection active.|

### <a name="working-with-mip-levels"></a>Utilisation des niveaux MIP
 Certains formats d’image, par exemple, DirectDraw Surface (.dds), prennent en charge les niveaux MIP pour le niveau de détail de l’espace de texture. Pour plus d’informations sur la façon de générer et d’utiliser les niveaux MIP, consultez [Guide pratique pour créer et modifier les niveaux MIP](../designers/how-to-create-and-modify-mip-levels.md)

### <a name="working-with-transparency"></a>Utilisation de la transparence
 Certains formats d’image, par exemple, DirectDraw Surface (.dds), prennent en charge la transparence. Vous pouvez utiliser la transparence de plusieurs façons, selon l’outil que vous utilisez. Pour spécifier le niveau de transparence pour une sélection de couleur, dans la fenêtre **Propriétés**, configurez le composant **A** (alpha) de la sélection de couleur. Voici comment les différents types d’outils contrôlent comment la transparence est appliquée :

|Outil|Description|
|----------|-----------------|
|**Crayon**, **Pinceau**, **Aérographe**, **Ligne**, **Rectangle**, **Rectangle à coins arrondis**, **Ellipse**, **Texte**|Pour fusionner la sélection de couleur active avec l’image, dans la fenêtre **Propriétés**, développez le groupe de propriétés **Canaux**, cochez la case **Dessiner** sur le canal **Alpha** puis dessinez normalement.<br /><br /> Pour dessiner en utilisant la sélection de couleur active et laisser telle quelle la valeur alpha de l’image, décochez la case **Dessiner** du canal **Alpha** puis dessinez normalement.|
|**Fill**|Pour fusionner la sélection de couleur active avec l’image, choisissez simplement la zone à remplir.<br /><br /> Pour utiliser la sélection de couleur active, y compris la valeur du canal alpha, pour remplacer l’image, maintenez la touche Maj enfoncée puis choisissez la zone à remplir.|

### <a name="image-properties"></a><a name="ImageProperties"></a> Propriétés de l’image
 Vous pouvez utiliser la fenêtre **Propriétés** pour spécifier différentes propriétés de l’image. Par exemple, vous pouvez définir les propriétés Largeur et Hauteur pour redimensionner l’image.

 Le tableau suivant décrit les propriétés d’une image.

|Propriété|Description|
|--------------|-----------------|
|Largeur|Largeur de l’image.|
|Hauteur|Hauteur de l’image.|
|Bits par pixel|Nombre de bits qui représentent chaque pixel. La valeur de cette propriété dépend du **Format de couleur** de l’image.|
|Sélection transparente|**Vrai** pour fusionner la couche de la sélection avec l’image principale, en fonction de la valeur alpha de la couche de la sélection ; sinon, **Faux**. Cet élément est disponible seulement pour les images qui prennent en charge alpha.|
|Format|Format de couleur de l’image. Vous pouvez spécifier différents formats de couleur selon le format de l’image. Le format de couleur définit le nombre et le type des canaux de couleur qui sont inclus dans l’image, ainsi que la taille et de codage des différents canaux.|
|Niveau MIP|Niveau MIP actif. Cet élément est disponible seulement pour les textures qui ont des niveaux MIP.|
|Nombre de niveaux mip|Nombre total de niveaux MIP dans l’image. Cet élément est disponible seulement pour les textures qui ont des niveaux MIP.|
|Nombre de frames|Nombre total de trames dans l’image. Cet élément est disponible seulement pour les images qui prennent en charge les tableaux de textures.|
|Frame|Trame en cours. Seule la première trame peut être visualisée. Toutes les autres trames sont perdues quand l’image est enregistrée.|
|Nombre de secteurs de profondeur|Nombre total de secteurs de profondeur dans l’image. Cet élément est disponible seulement pour les images qui prennent en charge les textures de volume.|
|Secteur de profondeur|Secteur de profondeur actif. Seule le premier secteur peut être visualisé. Tous les autres secteurs sont perdus quand l’image est enregistrée.|

> [!NOTE]
> Comme la propriété **Faire pivoter de** s’applique à tous les outils et à toutes les zones sélectionnées, elle apparaît toujours en bas de la fenêtre **Propriétés** en même temps que d’autres propriétés de l’outil. **Faire pivoter de** est toujours affiché, car l’image entière est implicitement sélectionnée quand il n’existe aucune autre sélection ou outil actif. Pour plus d’informations sur la propriété **Faire pivoter de**, consultez [Propriétés de l’outil](#ToolProperties).

#### <a name="resizing-images"></a>Redimensionnement des images
 Voici deux façons de redimensionner une image. Dans les deux cas, l’éditeur d’images utilise une interpolation bilinéaire pour rééchantillonner l’image.

- Dans la fenêtre **Propriétés**, spécifiez de nouvelles valeurs pour les propriétés **Largeur** et **Hauteur**.

- Sélectionnez l’image entière et utilisez les marqueurs de bordure pour redimensionner l’image.

### <a name="working-with-tools"></a>Utilisation des outils

#### <a name="selected-regions"></a>Zones concernées
 Les sélections dans l’éditeur d’images définissent des zones de l’image qui sont actives : ces zones sont affectées par les outils et les transformations. Quand il existe une sélection active, les zones situées en dehors de la zone sélectionnée ne sont pas affectées par la plupart des outils et des transformations. S’il n’existe pas de sélection active, c’est l’image entière qui est active.

 La plupart des outils (**crayon**, **pinceau**, **aérographe**, **remplissage**, **gomme**et primitives 2d) et des transformations (**rotation**, **découpage**, **inversion des couleurs**, **symétrie horizontale**et **symétrie verticale**) sont limités ou définis par la sélection active. Cependant, certains outils, comme **Pipette** et **Texte**, ainsi que des transformations, comme **Générer des mips**, ne sont affectés par aucune sélection active ; ces outils se comportent toujours comme si l’image entière était la sélection active.

 Quand vous sélectionnez une zone, vous pouvez maintenir la touche Maj enfoncée pour effectuer une sélection proportionnelle (carrée) ; sinon, la sélection n’est pas contrainte.

##### <a name="resizing-selections"></a>Redimensionnement des sélections
 Une fois que vous avez sélectionné une zone, vous pouvez redimensionner celle-ci ou l’image qu’elle contient en changeant la taille du marqueur de sélection. Quand vous redimensionnez la zone sélectionnée, vous pouvez utiliser les touches suivantes pour modifier le comportement de la zone sélectionnée lors de son redimensionnement (maintenez enfoncée la touche pendant le redimensionnement).

 Ctrl copie le contenu de la zone sélectionnée avant son redimensionnement. Ceci laisse l’image d’origine intacte, alors que la copie est redimensionnée.

 La touche Maj redimensionne la zone sélectionnée proportionnellement à sa taille d’origine.

 ALT modifie la taille de la zone de sélection. Ceci laisse l’image non modifiée.

 Voici les combinaisons de touches de modification valides :

|Ctrl|Shift|Alt|Description|
|----------|-----------|---------|-----------------|
||||Redimensionne le contenu de la zone sélectionnée.|
||Shift||Redimensionne proportionnellement le contenu de la zone sélectionnée.|
|||Alt|Redimensionne la zone sélectionnée. Ceci définit une nouvelle zone de sélection.|
||Shift|Alt|Redimensionne proportionnellement la zone sélectionnée. Ceci définit une nouvelle zone de sélection.|
|Ctrl|||Copie et redimensionne le contenu de la zone sélectionnée.|
|Ctrl|Shift||Copie puis redimensionne proportionnellement le contenu de la zone sélectionnée.|

#### <a name="tool-properties"></a><a name="ToolProperties"></a> Propriétés de l’outil
 Quand un outil est sélectionné, vous pouvez utiliser la fenêtre **Propriétés** pour spécifier des détails sur la façon dont il affecte l’image. Par exemple, vous pouvez définir l’épaisseur de l’outil **Crayon** ou la couleur de l’outil **Pinceau**.

 Vous pouvez définir une couleur de premier plan et une couleur d’arrière-plan. Les deux prennent en charge un canal alpha pour fournir une opacité définie par l’utilisateur. Les paramètres s’appliquent à tous les outils. Si vous utilisez une souris, le bouton gauche de la souris correspond à la couleur de premier plan, et le bouton droit de la souris correspond à la couleur d’arrière-plan.

 Le tableau suivant décrit les propriétés des outils.

|Outil|Propriétés|
|----------|----------------|
|Tous les outils et toutes les sélections|**Faire pivoter de**<br /> Définit la quantité de la rotation, en degrés, pour la sélection ou l’effet de l’outil dans le sens des aiguilles d’une montre.|
|**Crayon**, **Pinceau**, **Aérographe**, **Gomme**|**Thickness**<br /> Définit la taille de la zone affectée par l’outil.|
|**Text**|**Anticrénelage**<br /> Dessine du texte avec des contours lissés. Le texte a ainsi un aspect plus lisse.<br /><br /> **Valeur**<br /> Texte à dessiner.<br /><br /> **Police**<br /> Police utilisée pour dessiner le texte.<br /><br /> **Taille**<br /> Taille du texte.<br /><br /> **Gras**<br /> Met la police en gras.<br /><br /> **Italique**<br /> Met la police en italique.<br /><br /> **Souligné**<br /> Met la police en souligné.|
|**Primitive 2D**|**Anticrénelage**<br /> Dessine les primitives avec des contours lissés. Ceci leur donne une apparence plus lisse.<br /><br /> **Thickness**<br /> Définit l’épaisseur de la ligne qui constitue la limite de la primitive.<br /><br /> **Rayon X**<br /> (Rectangle à coins arrondis uniquement) Définit le rayon de l’arrondi pour les bords supérieur et inférieur de la primitive.<br /><br /> **Rayon Y**<br /> (Rectangle à coins arrondis uniquement) Définit le rayon de l’arrondi pour les bords gauche et droit de la primitive.|
|**Crayon**, **pinceau**, **aérographe**, **primitive 2D**|**Canaux**<br /> Active ou désactive des canaux de couleur spécifiques pour l’affichage et le dessin. Si **Afficher** est défini pour un canal de couleur spécifique, ce canal est visible dans l’image ; sinon, il n’est pas visible. Si **Dessiner** est défini pour un canal de couleur spécifique, ce canal est affecté par les opérations de dessin ; sinon, il ne l’est pas.|
|**Sélection « Baguette magique »**, **Remplissage**|**Seuil**<br /> Définit la différence maximale entre des couleurs adjacentes, selon laquelle elles sont considérées comme similaires, de sorte que plus ou moins de couleurs similaires font partie de la zone affectée ou sélectionnée. Par défaut, la valeur est 32, ce qui signifie que les pixels adjacents dans 32 nuances (plus claires ou plus sombres) de la couleur d’origine sont considérés comme faisant partie de la zone.|

## <a name="keyboard-shortcuts"></a>Raccourcis clavier

|Commande|Raccourcis clavier|
|-------------|------------------------|
|Passer en mode **Sélection**|S|
|Passer en mode **Zoom**|Z|
|Passer en mode **Panoramique**|K|
|Sélectionner tout|Ctrl+A|
|Supprimer la sélection actuelle|Supprimer|
|Annuler la sélection actuelle|Caractère d'échappement|
|Faire un zoom avant|Ctrl+Roulette de la souris vers l'avant<br /><br /> Ctrl+Pg préc<br /><br /> Signe plus (+)|
|Faire un zoom arrière|Ctrl-Roulette de la souris vers l’arrière<br /><br /> Ctrl-Pg. suiv<br /><br /> Signe moins (-)|
|Panoramique de l’image vers le haut|Roulette de la souris vers l'arrière<br /><br /> Pg suiv|
|Panoramique de l’image vers le bas|Roulette de la souris vers l'avant<br /><br /> Pg préc|
|Panoramique de l’image vers la gauche|Maj+Roulette de la souris vers l'arrière<br /><br /> Roulette de la souris vers la gauche<br /><br /> Maj+Pg. suiv|
|Panoramique de l’image vers la droite|Maj+Roulette de la souris vers l'avant<br /><br /> Roulette de la souris vers la droite<br /><br /> Maj+Pg. préc|
|Zoom sur la taille réelle|Ctrl+0 (zéro)|
|Adapter l’image à la fenêtre|Ctrl+G, Ctrl+F|
|Adapter l’image à la largeur de la fenêtre|Ctrl+G, Ctrl+I|
|Activer/désactiver la grille|Ctrl+G, Ctrl+G|
|Rogner l’image pour l’adapter à la sélection actuelle|Ctrl+G, Ctrl+C|
|Afficher le niveau MIP suivant (plus de détails)|Ctrl+G, Ctrl+6|
|Afficher le niveau MIP précédent (moins de détails)|Ctrl+G, Ctrl+7|
|Activer/désactiver le canal rouge|Ctrl+G, Ctrl+1|
|Activer/désactiver le canal vert|Ctrl+G, Ctrl+2|
|Activer/désactiver le canal bleu|Ctrl+G, Ctrl+3|
|Activer/désactiver le canal alpha (transparence)|Ctrl+G, Ctrl+4|
|Activer/désactiver le modèle de damier alpha|Ctrl+G, Ctrl+B|
|Passer à l’outil Sélection irrégulière|L|
|Passer à l’outil Baguette magique|M|
|Passer à l’outil Crayon|P|
|Passer à l’outil Pinceau|B|
|Passer à l’outil Remplissage|F|
|Passer à l’outil Gomme|E|
|Passer à l’outil Texte|T|
|Passer à l’outil de sélection de couleur (Pipette)|I|
|Déplacer la sélection active et son contenu.|Touches de direction.|
|Redimensionner la sélection active et son contenu.|Ctrl+Touches de direction|
|Déplacer la sélection active mais pas son contenu.|Maj+Touches de direction|
|Redimensionner la sélection active mais pas son contenu.|Maj+Ctrl+Touches de direction|
|Valider la couche actuelle|Renvoie|
|Diminuer l’épaisseur de l’outil|[|
|Augmenter l’épaisseur de l’outil|]|

## <a name="related-topics"></a>Rubriques connexes

|Titre|Description|
|-----------|-----------------|
|[Utilisation de ressources 3D pour les jeux et les applications](../designers/working-with-3-d-assets-for-games-and-apps.md)|Fournit une vue d’ensemble des outils que vous pouvez utiliser dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pour travailler avec des ressources graphiques, comme des textures et des images, des modèles 3D et des effets du nuanceur.|
|[Éditeur de modèle](../designers/model-editor.md)|Décrit l’utilisation de l’éditeur de modèle [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] avec les modèles 3D.|
|[Concepteur Shader](../designers/shader-designer.md)|Explique comment utiliser le concepteur Shader de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pour travailler avec des nuanceurs.|
