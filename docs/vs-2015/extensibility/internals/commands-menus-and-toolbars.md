---
title: Commandes, menus et barres d’outils | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus [Visual Studio SDK], commands
- commands [Visual Studio]
- toolbars [Visual Studio], commands
ms.assetid: 07b4ed90-dbbd-40df-b6c9-8395fd6f2ab6
caps.latest.revision: 61
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 337bc4de9171d2f98bf0be0068b298b7f600b979
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68155839"
---
# <a name="commands-menus-and-toolbars"></a>Commandes, menus et barres d’outils
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Les menus et les barres d’outils permettent aux utilisateurs d’accéder aux commandes de votre VSPackage. Les commandes sont des fonctions qui accomplissent des tâches, comme l’impression d’un document, l’actualisation d’une vue ou la création d’un fichier. Les menus et barres d’outils s’avèrent pratiques pour présenter graphiquement vos commandes aux utilisateurs. En règle générale, les commandes associées sont regroupées dans le même menu ou la même barre d’outils.  
  
- Les menus apparaissent généralement sous la forme de chaînes contenant un seul mot rassemblées sur une ligne en haut de l’environnement de développement intégré (IDE) ou d’une fenêtre Outil. Ils peuvent également apparaître après un clic droit et sont alors appelés menus contextuels. Quand vous cliquez dessus, les menus se développent pour présenter une ou plusieurs commandes. Les commandes, quand vous cliquez dessus, permettent d’effectuer des tâches ou de lancer des sous-menus qui contiennent d’autres commandes. Parmi les menus les plus connus figurent les menus Fichier, Edition, Affichage et Fenêtre. Pour plus d’informations, consultez [extension des menus et des commandes](../../extensibility/extending-menus-and-commands.md).  
  
- Les barres d’outils sont généralement des rangées de boutons et autres contrôles, comme des zones de liste modifiable, des zones de liste, des zones de texte et des contrôleurs de menu. Tous les contrôles de barre d’outils sont associés à des commandes. Quand vous cliquez sur un bouton de barre d’outils, sa commande associée est activée. Les boutons de barre d’outils comportent généralement des icônes qui suggèrent les commandes sous-jacentes, comme une imprimante pour une commande Imprimer. Dans un contrôle de liste déroulante, chaque élément de la liste est associé à une commande différente. Un contrôleur de menu est un hybride dans lequel un côté du contrôle est un bouton de barre d’outils et l’autre côté est une flèche vers le bas qui présente des commandes supplémentaires quand vous cliquez dessus. Pour plus d’informations, consultez [Ajout d’un contrôleur de menu à une barre d’outils](../../extensibility/adding-a-menu-controller-to-a-toolbar.md).  
  
- Quand vous créez une commande, vous devez également lui créer un gestionnaire d’événements. Le gestionnaire d’événements détermine quand la commande est visible ou activée, vous permet de modifier son texte et garantit que la commande répond correctement (« itinéraires ») lors de son activation. Dans la plupart des cas, l’IDE gère les commandes à l’aide de l’interface <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>. Les commandes de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] défilent de façon hiérarchique, en commençant par le contexte de commande le plus central, selon la sélection locale, puis en continuant avec le contexte le plus périphérique, selon la sélection globale. Les commandes ajoutées au menu principal sont immédiatement disponibles pour les scripts. Pour plus d’informations, consultez [MenuCommands ou OleMenuCommands](../../misc/menucommands-vs-olemenucommands.md) et [objets de contexte de sélection](../../extensibility/internals/selection-context-objects.md).  
  
  Pour définir de nouveaux menus et de nouvelles barres d’outils, vous devez les décrire dans un fichier Visual Studio Command Table (.vsct). Le modèle de package Visual Studio crée ce fichier pour vous, ainsi que les éléments nécessaires pour prendre en charge les commandes, barres d’outils et éditeurs que vous avez sélectionnés dans le modèle. Vous pouvez également écrire votre propre fichier .vsct en utilisant le schéma xml décrit ici : [VSCT XML Schema Reference](../../extensibility/vsct-xml-schema-reference.md).  
  
  Pour plus d’informations sur l’utilisation des fichiers. vsct, consultez [table de commandes Visual Studio (. Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
  Les rubriques de cette section expliquent comment fonctionnent les commandes, les menus et les barres d’outils dans les VSPackages.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Comment VSPackages ajoute des éléments de l’interface utilisateur](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Description détaillée de la spécification de format de la table de commandes.  
  
 [Fichiers Visual Studio Command Table (.Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)  
 Décrit une syntaxe XML et un compilateur pour les tables de commandes.  
  
 [Emplacement de commande, de groupe et de barre d’outils par défaut](../../extensibility/internals/default-command-group-and-toolbar-placement.md)  
 Décrit des commandes, des groupes, des menus et des barres d’outils prédéfinis.  
  
 [Commandes, menus et groupes définis par l’IDE](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)  
 Spécifie les menus, commandes et groupes de commandes prédéfinis pouvant être utilisés par l' [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE.  
  
 [Création de commande](../../extensibility/internals/command-design.md)  
 Explique comment concevoir des commandes.  
  
 [Optimisation des commandes de menu et de barre d’outils](../../extensibility/internals/optimizing-menu-and-toolbar-commands.md)  
 Fournit des instructions pour les commandes.  
  
 [Rendre les commandes disponibles](../../extensibility/internals/making-commands-available.md)  
 Explique comment rendre les commandes disponibles dans Visual Studio.  
  
 [Commandes et menus utilisant des assemblys d’interopérabilité](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)  
 Explique comment implémenter des commandes qui utilisent des assemblys d’interopérabilité.  
  
## <a name="related-sections"></a>Sections connexes  
 [Routage des commandes dans VSPackages](../../extensibility/internals/command-routing-in-vspackages.md)  
 Explique le routage des commandes dans les VSPackages.
