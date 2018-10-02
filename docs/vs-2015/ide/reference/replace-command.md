---
title: Remplacer, commande | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- edit.replace
helpviewer_keywords:
- Edit.Replace command
- Replace command
ms.assetid: a15767f1-5a3d-44f5-8c77-7b0f1157f340
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d4de79f804637f13b0fd487b1db62ad4bf7490ce
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47501643"
---
# <a name="replace-command"></a>Remplacer, commande
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [commande Replace](https://docs.microsoft.com/visualstudio/ide/reference/replace-command).  
  
  
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
 Facultatif. Remplace toutes les occurrences du texte recherché par le texte de remplacement.  
  
 /case ou /c  
 Facultatif. Il y a correspondance uniquement quand les caractères majuscules et minuscules correspondent exactement à ceux spécifiés dans l’argument `findwhat`.  
  
 /doc ou /d  
 Facultatif. Effectue la recherche uniquement dans le document actif. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.  
  
 /hidden ou /h  
 Facultatif. Recherche le texte masqué et réduit, par exemple les métadonnées d’un contrôle DTC, une zone masquée du plan d’un document ou encore une classe ou une méthode réduite.  
  
 /open ou /o  
 Facultatif. Effectue la recherche dans tous les documents ouverts comme s’il s’agissait d’un document unique. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.  
  
 /options ou /t  
 Facultatif. Affiche la liste des paramètres de recherche actuels et n’effectue pas de recherche.  
  
 /proc ou /p  
 Facultatif. Effectue la recherche uniquement dans la procédure en cours. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.  
  
 /regex ou /r  
 Facultatif. Utilise des caractères spéciaux prédéfinis dans l’argument `findwhat` comme notations représentant des modèles de texte, plutôt que des caractères littéraux. Pour obtenir la liste complète des caractères d’expressions régulières, consultez [Expressions régulières](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 /reset ou /e  
 Facultatif. Rétablit les paramètres par défaut des options de recherche et n’effectue pas de recherche.  
  
 /sel ou /s  
 Facultatif. Effectue la recherche uniquement dans la sélection en cours. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.  
  
 /up ou /u  
 Facultatif. Effectue la recherche à partir de l’emplacement actuel vers le début du fichier. Par défaut, les recherches commencent à l’emplacement actuel dans le fichier et s’effectuent vers la fin du fichier.  
  
 /wild ou /l  
 Facultatif. Utilise des caractères spéciaux prédéfinis dans l’argument `findwhat` comme notations représentant un caractère ou une séquence de caractères.  
  
 /word ou /w  
 Facultatif. Recherche uniquement les mots entiers.  
  
## <a name="example"></a>Exemple  
 Cet exemple remplace `btnSend` par `btnSubmit` dans tous les documents ouverts.  
  
```  
>Edit.Replace btnSend btnSubmit /open  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Recherche et remplacement de texte](../../ide/finding-and-replacing-text.md)   
 [Fenêtre Commande](../../ide/reference/command-window.md)   
 [Zone Rechercher/Commande](../../ide/find-command-box.md)   
 [Commandes Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Alias de commandes Visual Studio](../../ide/reference/visual-studio-command-aliases.md)



