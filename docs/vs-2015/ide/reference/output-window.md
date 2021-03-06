---
title: Sortie, fenêtre | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.build.output
- vs.debug.output
- vs.output
helpviewer_keywords:
- Output window, about Output window
- Output window
- Toolbox, removing controls
ms.assetid: d8931d88-250e-4db4-963f-2c5b3e99b45f
caps.latest.revision: 35
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: f17b91cc462b6f628100ffbf370fcdec2eb9888d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72662195"
---
# <a name="output-window"></a>Fenêtre Sortie
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

La fenêtre **Sortie** peut afficher des messages d’état pour diverses fonctionnalités dans l’environnement de développement intégré (IDE). Pour ouvrir la fenêtre **Sortie**, dans la barre de menus, choisissez **Affichage/Sortie** (ou cliquez sur Ctrl+Alt+O).

> [!WARNING]
> La fenêtre Sortie n’apparaît pas dans le menu Affichage des éditions Visual Studio Express. Pour l’afficher, utilisez le raccourci clavier Ctrl+Alt+O.

## <a name="toolbar"></a>Barre d’outils
 **Afficher la sortie de** Affiche un ou plusieurs volets de sortie à afficher. Plusieurs volets d’informations peuvent être disponibles, suivant les outils de l’IDE qui ont utilisé la fenêtre **Sortie** pour remettre des messages à l’utilisateur.

 **Rechercher un message dans le code** Déplace le point d’insertion dans l’éditeur de code vers la ligne qui contient l’erreur de build sélectionnée.

 **Atteindre le message précédent** Remplace le focus dans la fenêtre de **sortie** par l’erreur de build précédente et déplace le point d’insertion dans l’éditeur de code vers la ligne qui contient cette erreur de Build.

 **Atteindre le message suivant** Remplace le focus dans la fenêtre de **sortie** par l’erreur de build suivante et déplace le point d’insertion dans l’éditeur de code vers la ligne qui contient cette erreur de Build.

 **Effacer tout** Efface tout le texte du volet de **sortie** .

 **Activer/désactiver le retour automatique à la ligne** Active et désactive la fonctionnalité de retour automatique à la ligne dans le volet de **sortie** . Quand cette option est activée, le texte des longues entrées qui s’étend au-delà de la zone d’affichage apparaît sur la ligne suivante.

## <a name="output-pane"></a>Volet Sortie
 Le contenu du volet **Sortie** sélectionné dans la liste **Afficher la sortie à partir de** provient de la source indiquée.

## <a name="routing-messages-to-the-output-window"></a>Routage des messages vers la fenêtre Sortie
 Pour afficher la fenêtre **Sortie** chaque fois que vous générez un projet, dans la boîte de dialogue **Général, Projets et solutions, Options**, sélectionnez **Afficher la fenêtre Sortie au démarrage de la génération**. Ensuite, avec un fichier de code ouvert pour modification, choisissez les boutons **Atteindre le message suivant** et **Atteindre le message précédent** dans la barre d’outils de la fenêtre **Sortie** pour sélectionner des entrées dans le volet **Sortie**. Parallèlement, le point d’insertion dans l’éditeur de code se positionne sur la ligne de code à laquelle se produit le problème sélectionné.

 Certaines fonctionnalités et commandes de l’IDE appelées dans la [fenêtre commande](../../ide/reference/command-window.md) fournissent leur sortie dans la fenêtre **sortie** . La sortie des outils externes tels que les fichiers .bat et .com, qui s’affiche généralement dans la fenêtre Invite de commandes, est routée vers un volet **Sortie** quand vous sélectionnez l’option **Utiliser la fenêtre Sortie** dans la [gestion des outils externes](../../ide/managing-external-tools.md). D’autres types de messages peuvent également être affichés dans les volets **Sortie**. Par exemple, quand la syntaxe Transact-SQL d’une procédure stockée fait l’objet d’une vérification par rapport à une base de données cible, les résultats sont affichés dans la fenêtre **Sortie**.

 Vous pouvez également programmer vos propres applications pour qu’elles écrivent les messages de diagnostic au moment de l’exécution vers un volet **Sortie**. Pour ce faire, utilisez les membres de la classe <xref:System.Diagnostics.Debug> ou <xref:System.Diagnostics.Trace> dans l’espace de noms <xref:System.Diagnostics> de la bibliothèque de classes .NET Framework. Les membres de la classe <xref:System.Diagnostics.Debug> affichent la sortie quand vous générez des configurations Debug de votre solution ou projet ; les membres de la classe <xref:System.Diagnostics.Trace> affichent la sortie quand vous générez des configurations Debug ou Release. Pour plus d’informations, consultez [les messages de diagnostic dans le fenêtre Sortie](../../debugger/diagnostic-messages-in-the-output-window.md).

 Dans [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)], vous pouvez créer des étapes de génération personnalisées et des événements de build dont les avertissements et erreurs sont affichés et comptabilisés dans le volet **Sortie**. En appuyant sur F1 dans une ligne de sortie, vous pouvez afficher une rubrique d’aide appropriée. Pour plus d’informations, consultez [Mise en forme de la sortie d’une étape de génération personnalisée ou d’un événement de build](https://msdn.microsoft.com/library/92ad3e38-24d7-4b89-90e6-5a16f5f998da).

## <a name="scrolling-behavior"></a>Comportement de défilement
 Si vous utilisez le défilement automatique dans la fenêtre Sortie, puis que vous naviguez à l’aide de la souris ou des touches de direction, le défilement automatique s’arrête. Pour reprendre le défilement automatique, appuyez sur Ctrl+Fin.

## <a name="see-also"></a>Voir aussi
 [Messages de diagnostic dans le fenêtre Sortie](../../debugger/diagnostic-messages-in-the-output-window.md) [Comment : contrôler la fenêtre Sortie](https://msdn.microsoft.com/library/91aebd15-8854-4a7a-9f7d-57376fb4e858) [compilation et génération](../../ide/compiling-and-building-in-visual-studio.md) présentation de la bibliothèque de classes des [configurations de build](../../ide/understanding-build-configurations.md) [vue d’ensemble](https://msdn.microsoft.com/library/7e4c5921-955d-4b06-8709-101873acf157)
