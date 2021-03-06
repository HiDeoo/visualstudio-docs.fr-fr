---
title: Remplacer dans les fichiers | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.findreplace.replaceinfiles
- vs.replaceinfiles
helpviewer_keywords:
- text searches, replacing text
- Find and Replace window, Replace in Files tab
- Replace in Files tab, Find and Replace window
ms.assetid: ca361466-53bd-44db-a28a-3a74bc03b028
caps.latest.revision: 33
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 001f1faa969275788b10bc9bd1e6398373a54b37
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72669972"
---
# <a name="replace-in-files"></a>Remplacer dans les fichiers
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Remplacer dans les fichiers** vous permet de rechercher une chaîne ou une expression dans le code d’un ensemble défini de fichiers, et de changer l’ensemble ou une partie des correspondances trouvées. Les correspondances trouvées et les actions prises sont répertoriées dans la fenêtre résultats de la **recherche** sélectionnée dans **options de résultat**.

> [!NOTE]
> Les boîtes de dialogue et les commandes de menu affichées peuvent différer de celles décrites dans l'Aide selon les paramètres actifs ou le mode d'édition. Pour modifier vos paramètres, choisissez Importation et exportation de paramètres dans le menu Outils. Pour plus d’informations, consultez [Personnalisation des paramètres de développement dans Visual Studio](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).

 Vous pouvez utiliser l’une des méthodes suivantes pour afficher l’option **Remplacer dans les fichiers** dans la fenêtre **Rechercher et remplacer**.

### <a name="to-display-replace-in-files"></a>Pour afficher Remplacer dans les fichiers

1. Dans le menu **Edition**, développez **Rechercher et remplacer**.

2. Choisissez **Remplacer dans les fichiers**.

     — ou —

     Si la fenêtre **Rechercher et remplacer** est déjà ouverte, dans la barre d’outils, choisissez **Remplacer dans les fichiers**.

## <a name="find-what"></a>Rechercher
 Pour rechercher une nouvelle chaîne de texte ou expression, entrez-la dans cette zone. Pour rechercher une des 20 dernières chaînes que vous avez recherchées récemment, ouvrez la liste et sélectionnez la chaîne à rechercher. Choisissez le bouton adjacent **Générateur d’expressions** si vous souhaitez utiliser une ou plusieurs expressions régulières dans votre chaîne de recherche. Pour plus d’informations, consultez [Utilisation d’expressions régulières dans Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

## <a name="replace-with"></a>Remplacer par
 Pour remplacer des instances de la chaîne dans la zone **Rechercher** par une autre chaîne, entrez la chaîne de remplacement dans la zone **Remplacer par**. Pour supprimer des instances de la chaîne dans la zone **Rechercher**, laissez ce champ vide. Ouvrez la liste pour afficher les 20 chaînes que vous avez recherchées le plus récemment. Choisissez le bouton adjacent **Générateur d’expressions** si vous souhaitez utiliser une ou plusieurs expressions régulières dans votre chaîne de remplacement. Pour plus d’informations, consultez [Utilisation d’expressions régulières dans Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

## <a name="look-in"></a>Regarder dans
 L’option choisie dans la liste déroulante **Regarder dans** détermine si la fonction **Remplacer dans les fichiers** effectue la recherche uniquement dans les fichiers actuellement actifs ou dans tous les fichiers stockés dans certains dossiers. Sélectionnez une étendue de recherche dans la liste, tapez le chemin d’un dossier ou cliquez sur le bouton **Parcourir (...)** pour afficher la boîte de dialogue **Choisir des dossiers de recherche** et choisissez un ensemble de dossiers. Vous pouvez également taper un chemin directement dans la zone **Regarder dans**.

> [!NOTE]
> Si l’option **Regarder dans** sélectionnée entraîne la recherche dans un fichier que vous avez extrait du contrôle de code source, la recherche ne porte que sur la version du fichier ayant été téléchargée sur votre ordinateur local.

## <a name="find-options"></a>Options de recherche
 Vous pouvez développer ou réduire la section **options de recherche** . Les options suivantes peuvent être sélectionnées ou désélectionnées :

 Respecter la casse lorsqu’elle est sélectionnée, les fenêtres résultats de la **recherche** affichent uniquement les instances de la chaîne **Rechercher** qui sont mises en correspondance à la fois par le contenu et par la casse. Par exemple, la recherche de « MyObject » avec l’option **Respecter la casse** sélectionnée retourne « MyObject », mais pas « myobject » ni « MYOBJECT ».

 Mot entier quand vous sélectionnez cette option, les fenêtres résultats de la **recherche** affichent uniquement les instances de la chaîne **Rechercher** qui correspondent à des mots entiers. Par exemple, la recherche de « MyObject » retourne « MyObject », mais pas « CMyObject » ni « MyObjectC ».

 Utiliser des expressions régulières lorsque cette case à cocher est activée, vous pouvez utiliser des notations spéciales pour définir des modèles de texte dans les zones de texte **Rechercher** ou **remplacer par** . Pour obtenir la liste de ces notations, consultez [Utilisation d’expressions régulières dans Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

 Examiner ces types de fichiers cette liste indique les types de fichiers dans lesquels effectuer la recherche **dans les répertoires de recherche** . Si ce champ est laissé vide, tous les fichiers dans les répertoires choisis dans **Regarder dans** sont examinés.

 Sélectionnez un élément dans la liste pour entrer une chaîne de recherche prédéfinie à rechercher dans les fichiers de ces types particuliers.

## <a name="result-options"></a>Options de résultat
 Vous pouvez développer ou réduire la section **options de résultat** . Les options suivantes peuvent être sélectionnées ou désélectionnées :

 Fenêtre résultats de la recherche 1 : lorsque cette option est sélectionnée, les résultats de la recherche actuelle remplacent le contenu de la fenêtre résultats de la **recherche 1** . Cette fenêtre s'ouvre automatiquement pour afficher vos résultats de recherche. Pour ouvrir cette fenêtre manuellement, sélectionnez **Autres fenêtres** dans le menu **Affichage** et choisissez **Résultats de la recherche 1**.

 Fenêtre résultats de la recherche 2 : lorsque cette option est sélectionnée, les résultats de la recherche actuelle remplacent le contenu de la fenêtre résultats de la **recherche 2** . Cette fenêtre s'ouvre automatiquement pour afficher vos résultats de recherche. Pour ouvrir cette fenêtre manuellement, sélectionnez **Autres fenêtres** dans le menu **Affichage** et choisissez **Résultats de la recherche 2**.

 Afficher les noms de fichiers uniquement lorsque cette case à cocher est activée, les fenêtres résultats de la recherche répertorient les noms complets et les chemins d’accès de tous les fichiers qui contiennent la chaîne recherchée. Toutefois, les résultats ne contiennent pas la ligne de code où apparaît la chaîne. Cette case à cocher n’est disponible que pour Rechercher dans les fichiers.

 Conserver les fichiers modifiés ouverts après l’option remplacer tout lorsqu’ils sont sélectionnés, ouvre tous les fichiers dans lesquels des remplacements ont été effectués, ce qui vous permet d’annuler ou d’enregistrer les modifications. Les contraintes de mémoire peuvent limiter le nombre de fichiers qui peuvent rester ouverts suite à une opération de remplacement.

> [!CAUTION]
> Vous ne pouvez utiliser la commande **Annuler** qu’avec les fichiers qui restent ouverts à des fins d’édition. Si vous n’activez pas cette option, les fichiers qui n’étaient pas ouverts à des fins d’édition restent fermés et l’option **Annuler** n’est pas disponible pour ces fichiers.

## <a name="see-also"></a>Voir aussi
 [Recherche et remplacement de texte](../ide/finding-and-replacing-text.md) [Rechercher dans des fichiers](../ide/find-in-files.md) [commandes Visual Studio](../ide/reference/visual-studio-commands.md)
