---
title: Comportement de l’éditeur
description: Cet article décrit les différentes options que vous pouvez utiliser pour modifier le comportement de l’éditeur de texte dans Visual Studio pour Mac
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 81EE4460-26EB-4BB0-9297-932E1F88E4B8
ms.openlocfilehash: 4d40d03bde0323ce44b9de6ff1ae13e281f0ed6c
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2018
ms.locfileid: "43224132"
---
# <a name="editor-behavior"></a>Comportement de l’éditeur

Les comportements de l’éditeur peuvent être définis de façon à autoriser la mise en forme du code au fil de son écriture. Ces actions sont définies sous **Visual Studio > Préférences... > Éditeur de texte > Comportement**, et certaines des fonctions les plus couramment utilisées sont décrites ci-dessous :

![Options de comportement de l’éditeur](media/source-editor-image9.png)

*  Les accolades fermantes correspondantes peuvent être ajoutées automatiquement au code lors de la création de nouvelles classes, méthodes ou propriétés. Si cette option est sélectionnée, quand vous tapez `{`, l’éditeur ajoute automatiquement `}`.
* La mise en forme du code à la volée est déclenchée par la saisie de certains caractères, comme le point-virgule ou les accolades, qui va appliquer les préférences de mise en forme qui sont définies.
* Vous pouvez également choisir de mettre en forme le fichier lors de son enregistrement : ceci vous permet d’écrire le code comme vous le souhaitez et de laisser à l’IDE la responsabilité de la mise en forme du code telle qu’elle est définie par les préférences existantes.
* La mise en retrait peut être définie sur Aucune, Automatique ou Intelligente. Voici ce que font ces options :
 * Aucune : place le point d’insertion au début de la ligne suivante
 * Automatique : place le point d’insertion sur la même colonne de la ligne suivante
 * Intelligente : met en retrait sur la ligne suivante en fonction du code
* Le comportement de la césure des mots diffère entre les systèmes d’exploitation et, pour la navigation dans le code, l’éditeur de texte doit savoir où les mots commencent ou se terminent. La mise en forme peut être définie pour Unix ou pour Windows.

Vous pouvez aussi définir des règles de mise en forme pour XML, CSS, HTML et JSON.