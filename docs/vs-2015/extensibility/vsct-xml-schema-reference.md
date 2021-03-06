---
title: Informations de référence sur le schéma XML VSCT | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- Visual Studio command table configuration files (VSCT), XML schema
- VSCT XML schema elements
ms.assetid: 49e7efae-e713-4762-a824-96fdaf92cdc9
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e56de828d3b357762da98cde3b9591033c6b5d19
ms.sourcegitcommit: fb8babf5cd72f1fc2f97ffe4ad7b62d91f325f61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2020
ms.locfileid: "90839710"
---
# <a name="vsct-xml-schema-reference"></a>Informations de référence sur le schéma XML VSCT
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Fournit un tableau des éléments de schéma du compilateur de table de commandes, avec les éléments enfants et les attributs autorisés pour chacun.  
  
 Un fichier de configuration de table de commandes basé sur XML (. vsct) définit les éléments de commande qu’un VSPackage fournit à l’environnement de développement intégré (IDE). Ces éléments incluent des éléments de menu, des menus, des barres d’outils et des zones de liste modifiable.  
  
> [!NOTE]
> Le compilateur VSCT peut exécuter un préprocesseur sur le fichier. vsct. Étant donné qu’il s’agit généralement du préprocesseur C++, vous pouvez définir des inclusions et des macros dont la syntaxe est identique à celle utilisée dans les fichiers C++. Des exemples sont fournis dans le fichier. vsct que l’Assistant **nouveau projet** crée pour un projet VSPackage.  
  
## <a name="optional-elements"></a>Éléments facultatifs  
 Certains éléments VSCT sont facultatifs. Si aucun `Parent` argument n’est spécifié, Group_Undefined : 0 sera implicite. Si un `Icon` argument n’est pas spécifié, guidOfficeIcon : msotcidNoIcon sera implicite. Lorsqu’une touche de raccourci est définie, l’émulation, qui n’est généralement pas utilisée, est facultative.  
  
 Les éléments bitmap peuvent être incorporés au moment de la compilation en spécifiant l’emplacement de la bande de bitmaps dans l' `href` argument. La bande bitmap est copiée au cours de la fusion au lieu d’être extraite des ressources de la DLL. Quand un `href` argument est fourni, l' `usedList` argument devient facultatif et tous les emplacements de la bande bitmap sont considérés comme étant utilisés.  
  
 Toutes les valeurs GUID et ID doivent être définies à l’aide de noms symboliques. Ces noms peuvent être définis dans des fichiers d’en-tête ou dans des \<Symbols> sections vsct. Les noms symboliques doivent être locaux, inclus dans des \<Include> éléments ou référencés par des \<Extern> éléments. Un nom symbolique est importé à partir d’un fichier d’en-tête spécifié dans un \<Extern> élément s’il suit le modèle simple de #define valeur de symbole. La valeur peut être un autre symbole, à condition que ce symbole ait été défini précédemment. Les définitions de GUID doivent suivre le format OLE ou C++. Les valeurs d’ID peuvent être soit des chiffres décimaux, soit des chiffres hexadécimaux précédés de 0x, comme indiqué dans les lignes suivantes :  
  
- {6D484634-E53D-4a2c-ADCB-55145C9362C8}  
  
- {0x6d484634, 0xe53d, 0x4a2c, {0xad, 0xcb, 0x55, 0x14, 0x5c, 0x93, 0x62, 0xC8}}  
  
  Les commentaires XML peuvent être utilisés, mais les outils d’interface utilisateur graphique (GUI) d’aller-retour peuvent les ignorer. Le contenu des \<Annotation> éléments est garanti être conservé quel que soit le format.  
  
## <a name="schema-hierarchy"></a>Hiérarchie de schéma  
 Un fichier. vsct contient les éléments principaux suivants.  
  
 [Élément CommandTable](../extensibility/commandtable-element.md)  
  
 [Élément Extern](../extensibility/extern-element.md)  
  
 [Élément Include](../extensibility/include-element.md)  
  
 [Élément Define](../extensibility/define-element.md)  
  
 [Élément Commands](../extensibility/commands-element.md)  
  
 [Élément CommandPlacements](../extensibility/commandplacements-element.md)  
  
 [Élément VisibilityConstraints](../extensibility/visibilityconstraints-element.md)  
  
 [Élément KeyBindings](../extensibility/keybindings-element.md)  
  
 [Élément UsedCommands](../extensibility/usedcommands-element.md)  
  
 [Élément parent](../extensibility/parent-element.md)  
  
 [Élément Icon](../extensibility/icon-element.md)  
  
 [Élément Strings](../extensibility/strings-element.md)  
  
 [Élément Command Flag](../extensibility/command-flag-element.md)  
  
 [Élément Symbols](../extensibility/symbols-element.md)  
  
 [Attributs conditionnels](../extensibility/vsct-xml-schema-conditional-attributes.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Comment les VSPackages ajoutent des éléments d’interface utilisateur](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Routage des commandes dans VSPackages](../extensibility/internals/command-routing-in-vspackages.md)
