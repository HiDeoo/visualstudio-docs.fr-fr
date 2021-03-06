---
title: Options, Éditeur de texte, JavaScript, IntelliSense | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Intellisense.References
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Intellisense.General
ms.assetid: b4a9816d-cf87-4dc6-a8d4-1591d6a48103
caps.latest.revision: 24
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1b0d9dec8ec9b3eb8860bb8b3a4ed8f7347aa54d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72662233"
---
# <a name="options-text-editor-javascript-intellisense"></a>Options, Éditeur de texte, JavaScript, IntelliSense
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Utilisez la page **IntelliSense** de la boîte de dialogue **Options** pour modifier les paramètres qui affectent le comportement d'IntelliSense pour JavaScript. Vous pouvez accéder à la page **IntelliSense** en choisissant **Outils**, **Options** dans la barre de menus, et en développant ensuite **Éditeur de texte**, **JavaScript**, **IntelliSense.**

 [!INCLUDE[note_settings_general](../../includes/note-settings-general-md.md)]

 La page **IntelliSense** contient les sections suivantes :

## <a name="validation"></a>Validation
 Vous pouvez utiliser ces options pour définir comment l'éditeur JavaScript doit valider la syntaxe dans votre document.

## <a name="uielement-list"></a>Liste des éléments de l'interface utilisateur
 **Afficher les erreurs de syntaxe** Lorsque cette case à cocher n’est pas activée, l’éditeur de code JavaScript n’affiche pas d’erreurs de syntaxe. Cela est utile si vous travaillez avec du code dont vous n'êtes pas l'auteur et que vous n'avez pas l'intention de corriger les erreurs de syntaxe.

 Lorsque cette case à cocher est activée, vous pouvez activer la case à cocher **Afficher les erreurs comme des avertissements** .

 **Afficher les erreurs en tant qu’avertissements** Lorsque cette case à cocher est activée, les erreurs JavaScript sont affichées sous la forme d’avertissements et non d’erreurs dans la liste d’erreurs.

 **Télécharger les références distantes (par exemple, http://) pour les fichiers dans le projet fichiers divers** Lorsque cette case à cocher est activée et que vous avez un fichier JavaScript ouvert en dehors du contexte d’un projet, Visual Studio télécharge les fichiers JavaScript distants référencés dans le fichier dans le but de fournir des informations IntelliSense. Si cette option est sélectionnée, les fichiers sont téléchargés lorsque vous les incluez en tant que référence dans votre fichier JavaScript.

> [!NOTE]
> Pour les projets Web, les fichiers distants référencés dans votre projet sont téléchargés par défaut.

## <a name="statement-completion"></a>Compléter automatiquement les instructions
 Vous pouvez utiliser ces options pour modifier le comportement de la saisie semi-automatique des instructions IntelliSense.

## <a name="uielement-list"></a>Liste des éléments de l'interface utilisateur
 **Utiliser uniquement la touche Tab ou entrée pour valider** Lorsque cette case à cocher est activée, l’éditeur de code JavaScript ajoute des instructions avec des éléments sélectionnés dans la liste de saisie semi-automatique uniquement après que vous avez choisi l’onglet ou la touche entrée. Lorsque cette case à cocher est désactivée, d'autres caractères, comme un point, une virgule, deux-points, une parenthèse ouvrante, et une accolade ouvrante ({)) peuvent également ajouter des instructions aux éléments sélectionnés.

## <a name="references"></a>Références
 Vous pouvez utiliser ces options pour spécifier les types de fichiers IntelliSense .js qui sont dans la portée pour différents types de projet JavaScript. Les références IntelliSense sont généralement utilisées pour fournir une prise en charge IntelliSense pour les objets globaux. Vous pouvez également utiliser cette page pour définir l'ordre de chargement des scripts qui doivent être chargés au moment de l'exécution, et ajouter des fichiers d'extension IntelliSense.

## <a name="uielement-list"></a>Liste des éléments de l'interface utilisateur
 **Groupes de référence** Cette option spécifie le type de groupe de référence. Trois groupes de référence sont pris en charge :

 Vous pouvez utiliser les groupes de référence prédéfinis pour spécifier les fichiers IntelliSense .js particuliers qui sont dans la portée des projets JavaScript. Quatre groupes de référence sont disponibles :

- Implicite ( *version*de Windows) pour les applications [!INCLUDE[win8_appname_long](../../includes/win8-appname-long-md.md)] en JavaScript. Les fichiers inclus dans ce groupe se trouvent dans la portée pour chaque fichier .js ouvert dans l’éditeur de code pour les applications [!INCLUDE[win8_appname_long](../../includes/win8-appname-long-md.md)] utilisant JavaScript.

- Implicite (Web) pour les projets HTML5. Les fichiers inclus dans ce groupe figurent dans la portée de chaque fichier .js ouvert dans l'éditeur de code pour ces types de projet.

- Groupes de référence de processus de travail dédié pour les traitements Web HTML5. Les fichiers spécifiés dans ce groupe figurent dans la portée des fichiers .js qui possèdent une référence explicite à un groupe de référence de processus de travail dédié.

- Générique pour les autres types de projet JavaScript.

  **Fichiers inclus** Cette option spécifie l’ordre dans lequel les fichiers sont chargés dans le contexte du service de langage. Vous pouvez configurer l'ordre à l'aide des boutons **Supprimer**, **Monter**et **Descendre** . Pour qu'IntelliSense fonctionne correctement, un fichier qui dépend des autres doit être chargé après l'autre fichier.

> [!CAUTION]
> Si un objet est défini de manière inconditionnelle dans deux références implicites ou plus, la dernière référence de cette liste sera utilisée pour définir l'objet.

 **Ajouter une référence au groupe** Cette option permet d’ajouter des fichiers IntelliSense. js supplémentaires en parcourant les fichiers appropriés.

## <a name="see-also"></a>Voir aussi
 [IntelliSense JavaScript](../../ide/javascript-intellisense.md)
