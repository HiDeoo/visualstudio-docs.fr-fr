---
title: Rechercher, commande | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- edit.find
helpviewer_keywords:
- Find command
- Edit.Find command
ms.assetid: f0c705dc-2b97-423d-abbf-5584d4827208
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cf2ef55aa291016719c5f481d70dadd09f4403d1
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49259179"
---
# <a name="find-command"></a>Rechercher, commande
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Recherche des fichiers en utilisant un sous-ensemble des options disponibles sous l’onglet **Rechercher dans les fichiers**  de la fenêtre **Rechercher et remplacer**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Edit.Find findwhat [/case] [/doc | /proc | /open | /sel]   
[/markall] [/options] [/reset] [/up] [/wild | /regex] [/word]  
```  
  
## <a name="arguments"></a>Arguments  
 `findwhat`  
 Obligatoire. Texte à rechercher.  
  
## <a name="switches"></a>Commutateurs  
 /case ou /c  
 Facultatif. Il y a correspondance uniquement si les caractères majuscules et minuscules correspondent exactement à ceux spécifiés dans l’argument `findwhat`.  
  
 /doc ou /d  
 Facultatif. Effectue la recherche uniquement dans le document actif. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.  
  
 /markall ou /m  
 Facultatif. Ajoute un graphique à chaque ligne contenant une correspondance du texte recherché dans le document actif.  
  
 /open ou /o  
 Facultatif. Effectue la recherche dans tous les documents ouverts comme s’il s’agissait d’un document unique. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.  
  
 /options ou /t  
 Facultatif. Affiche la liste des paramètres de recherche actuels et n’effectue pas de recherche.  
  
 /proc ou /p  
 Facultatif. Effectue la recherche uniquement dans la procédure en cours. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.  
  
 /reset ou /e  
 Facultatif. Rétablit les paramètres par défaut des options de recherche et n’effectue pas de recherche.  
  
 /sel ou /s  
 Facultatif. Effectue la recherche uniquement dans la sélection en cours. Spécifiez une seule des étendues de recherche disponibles, à savoir `/doc`, `/proc`, `/open` ou `/sel`.  
  
 /up ou /u  
 Facultatif. Effectue la recherche à partir de l’emplacement actuel vers le début du fichier. Par défaut, les recherches commencent à l’emplacement actuel dans le fichier et s’effectuent vers la fin du fichier.  
  
 /regex ou /r  
 Facultatif. Utilise des caractères spéciaux prédéfinis dans l’argument `findwhat` comme notations représentant des modèles de texte, plutôt que des caractères littéraux. Pour obtenir la liste complète des caractères d’expressions régulières, consultez [Expressions régulières](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 /wild ou /l  
 Facultatif. Utilise des caractères spéciaux prédéfinis dans l’argument `findwhat` comme notations représentant un caractère ou une séquence de caractères.  
  
 /word ou /w  
 Facultatif. Recherche uniquement les mots entiers.  
  
## <a name="example"></a>Exemple  
 Cet exemple recherche le mot « somestring » en respectant la casse dans la section de code sélectionnée.  
  
```  
>Edit.Find somestring /sel /case  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fenêtre Commande](../../ide/reference/command-window.md)   
 [Zone Rechercher/Commande](../../ide/find-command-box.md)   
 [Commandes Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Alias de commandes Visual Studio](../../ide/reference/visual-studio-command-aliases.md)



