---
title: Ouvrir un fichier, commande | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.openfile
helpviewer_keywords:
- Open File command
- File.OpenFile command
- of command
ms.assetid: a51a83fc-e3c6-4fa2-8882-8b7b6c0a6406
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1c8dcf35e4c045db0d9acd45e2eb307a31ba39f1
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72671936"
---
# <a name="open-file-command"></a>Ouvrir un fichier, commande
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ouvre un fichier existant et vous permet de spécifier un éditeur.

## <a name="syntax"></a>Syntaxe

```
File.OpenFile filename [/e:editorname]
```

## <a name="arguments"></a>Arguments
 `filename` Obligatoire. Chemin complet ou partiel et nom du fichier à ouvrir. Les chemins comportant des espaces doivent être placés entre guillemets.

## <a name="switches"></a>Commutateurs
 /e:`editorname` (facultatif). Nom de l’éditeur dans lequel le fichier doit être ouvert. Si l’argument est spécifié, mais qu’aucun nom d’éditeur n’est fourni, la boîte de dialogue **Ouvrir avec** s’affiche.

 La syntaxe de l’argument /e:`editorname` utilise les noms d’éditeur tels qu’ils apparaissent dans la boîte de dialogue Ouvrir avec, entre guillemets.

 Par exemple, pour ouvrir un fichier dans l’éditeur de code source, entrez les informations suivantes pour l’argument /e:`editorname`.

```
/e:"Source Code (text) Editor"
```

## <a name="remarks"></a>Notes
 La fonctionnalité de saisie semi-automatique tente de trouver le chemin et le nom de fichier correspondant aux caractères que vous tapez.

## <a name="example"></a>Exemple
 Cet exemple ouvre la feuille de style « Test1.css » dans l’éditeur de code source.

```
>File.OpenFile "C:\My Projects\project1\Test1.css" /e:"Source Code (text) Editor"
```

## <a name="see-also"></a>Voir aussi
 [Commande](../../ide/reference/command-window.md) [Visual Studio commandes](../../ide/reference/visual-studio-commands.md) fenêtre [exécution fenêtre exécution](../../ide/reference/immediate-window.md) [Rechercher/zone de commandes](../../ide/find-command-box.md) [Visual Studio alias de commandes Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
