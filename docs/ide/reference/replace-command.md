---
title: Remplacer, commande
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- edit.replace
helpviewer_keywords:
- Edit.Replace command
- Replace command
ms.assetid: a15767f1-5a3d-44f5-8c77-7b0f1157f340
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4d834d35a31c40e82987bb93deb43c5727074b00
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55022571"
---
# <a name="replace-command"></a>Remplacer, commande
Remplace le texte dans les fichiers à l’aide d’un sous-ensemble des options proposées sous l’onglet **Remplacer dans les fichiers** de la fenêtre **Rechercher et remplacer**.

## <a name="syntax"></a>Syntaxe

```
Edit.Replace findwhat replacewith [/all] [/case]
[/doc|/proc|/open|/sel] [/hidden] [/options] [/reset] [/up]
[/wild|/regex] [/word]
```

## <a name="arguments"></a>Arguments
 `findwhat`

 Obligatoire. Texte à rechercher.

 `replacewith`

 Obligatoire. Texte de remplacement du texte trouvé.

## <a name="switches"></a>Commutateurs
 /all ou /a

 Optionnel. Remplace toutes les occurrences du texte recherché par le texte de remplacement.

 /case ou /c

 Optionnel. Il y a correspondance uniquement quand les caractères majuscules et minuscules correspondent exactement à ceux spécifiés dans l’argument `findwhat`.

 /doc ou /d

 Optionnel. Effectue la recherche uniquement dans le document actif. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.

 /hidden ou /h

 Optionnel. Recherche le texte masqué et réduit, par exemple les métadonnées d’un contrôle DTC, une zone masquée du plan d’un document ou encore une classe ou une méthode réduite.

 /open ou /o

 Optionnel. Effectue la recherche dans tous les documents ouverts comme s’il s’agissait d’un document unique. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.

 /options ou /t

 Optionnel. Affiche la liste des paramètres de recherche actuels et n’effectue pas de recherche.

 /proc ou /p

 Optionnel. Effectue la recherche uniquement dans la procédure en cours. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.

 /regex ou /r

 Optionnel. Utilise des caractères spéciaux prédéfinis dans l’argument `findwhat` comme notations représentant des modèles de texte, plutôt que des caractères littéraux. Pour obtenir la liste complète des caractères d’expressions régulières, consultez [Expressions régulières](../../ide/using-regular-expressions-in-visual-studio.md).

 /reset ou /e

 Optionnel. Rétablit les paramètres par défaut des options de recherche et n’effectue pas de recherche.

 /sel ou /s

 Optionnel. Effectue la recherche uniquement dans la sélection en cours. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.

 /up ou /u

 Optionnel. Effectue la recherche à partir de l’emplacement actuel vers le début du fichier. Par défaut, les recherches commencent à l’emplacement actuel dans le fichier et s’effectuent vers la fin du fichier.

 /wild ou /l

 Optionnel. Utilise des caractères spéciaux prédéfinis dans l’argument `findwhat` comme notations représentant un caractère ou une séquence de caractères.

 /word ou /w

 Optionnel. Recherche uniquement les mots entiers.

## <a name="example"></a>Exemple
 Cet exemple remplace `btnSend` par `btnSubmit` dans tous les documents ouverts.

```
>Edit.Replace btnSend btnSubmit /open
```

## <a name="see-also"></a>Voir aussi

- [Recherche et remplacement de texte](../../ide/finding-and-replacing-text.md)
- [Commande, fenêtre](../../ide/reference/command-window.md)
- [Rechercher/Commande, zone](../../ide/find-command-box.md)
- [Commandes Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)