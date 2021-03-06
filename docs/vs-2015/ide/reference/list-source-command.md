---
title: Afficher la source, commande | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
caps.latest.revision: 13
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3f13689b6e3ac4db2d58c1def3a5d0dd05c219f2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72672319"
---
# <a name="list-source-command"></a>Afficher la source, commande
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Affiche les lignes de code source spécifiées.

## <a name="syntax"></a>Syntaxe

```
Debug.ListSource [/Count:number] [/Current] [/File:filename]
[/Line:number] [/ShowLineNumbers:yes|no]
```

## <a name="switches"></a>Commutateurs
 /Count : `number` facultatif. Spécifie le nombre de lignes à afficher.

 /Current facultatif. Affiche la ligne active.

 /File : `filename` facultatif. Chemin du fichier à afficher. Si aucun nom de fichier n’est spécifié, la commande affiche le code source de la ligne de l’instruction actuelle.

 /Line : `number` facultatif. Affiche un numéro de ligne spécifique.

 /ShowLineNumbers : `yes|no` facultatif. Spécifie s’il faut afficher les numéros de ligne.

## <a name="remarks"></a>Notes

## <a name="example"></a>Exemple
 Cet exemple affiche le code source à partir de la ligne 4 du fichier Form1.vb, avec les numéros de ligne.

```
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes
```

## <a name="see-also"></a>Voir aussi
 Fenêtre commande de [Visual Studio](../../ide/reference/visual-studio-commands.md) [Commands](../../ide/reference/command-window.md)
