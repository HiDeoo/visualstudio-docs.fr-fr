---
title: Extraits de code pour R
description: Les extraits de code pour R dans Visual Studio fournissent des raccourcis pour insérer rapidement des blocs de code de longueur arbitraire, ce qui vous évite de retaper du code similaire plusieurs fois de suite.
ms.date: 01/24/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.workload:
- data-science
ms.openlocfilehash: 0f7dbe2322ceedaf057db67b2c56411abb46a7a9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54964728"
---
# <a name="code-snippets"></a>Extraits de code

Les extraits de code dans Visual Studio fournissent des raccourcis pour insérer rapidement des blocs de code de longueur arbitraire, ce qui vous évite de retaper du code similaire plusieurs fois de suite. Les Outils R pour Visual Studio (RTVS) ajoutent des dizaines d’extraits de code R utiles à la collection de Visual Studio.

Pour insérer un extrait de code, tapez son nom abrégé (IntelliSense vous aide), puis appuyez sur **Tab** pour l’insérer.

Voici quelques exemples simples :

- tapez `=`, puis appuyez sur Tab : RTVS le convertit en opérateur d’assignation `<-`.
- tapez `>`, puis appuyez sur Tab : RTVS le convertit en opérateur de barre verticale `%>%`.

Les extraits de code peuvent apporter bien plus que la saisie semi-automatique de caractères. Un extrait de code qui permet de lire un fichier CSV avec la fonction `read.csv`, par exemple, peut vous éviter d’avoir à mémoriser les noms ou paramètres :

![Animation de l’utilisation d’un extrait de code pour insérer un appel dans read.csv](media/code-snippet-expansion.gif)

Dans ce cas, quand vous tapez `readc`, IntelliSense affiche une liste de saisie semi-automatique. Sélectionnez cette complétion dans la liste déroulante et appuyez sur **Tab** pour sélectionner `readc`, et réappuyez sur **Tab** pour développer l’extrait de code. (Pour cette raison, le développement de l’extrait de code est souvent évoqué comme « tapez l’extrait de code et appuyez deux fois sur Tab »). Dans la plupart des cas, le premier appui sur Tab effectue la sélection IntelliSense et le deuxième appui déclenche le développement.

Pour voir tous les extraits de code disponibles, ouvrez la boîte de dialogue **Outils** > **Gestionnaire des extraits de code** (**Ctrl**+**K**,**B**) et sélectionnez **R** pour **Langage**. Développez les groupes, puis sélectionnez les extraits de code individuels pour afficher une description et le texte de raccourci :

![Boîte de dialogue Extraits de code pour R](media/code-snippet-dialog.png)

Pour créer des extraits de code personnalisés, suivez les instructions de [Procédure pas à pas : Créer un extrait de code](../ide/walkthrough-creating-a-code-snippet.md). En fin de compte, un extrait de code est un simple fichier XML. Par exemple, le code suivant est l’extrait de code pour l’opération de barre verticale (raccourci `>`) :

```xml
<?xml version="1.0" encoding="utf-8" ?>
<CodeSnippets  xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
  <CodeSnippet Format="1.0.0">
    <Header>
      <Title>Dplyr pipe</Title>
      <Shortcut>&gt;</Shortcut>
      <Description>Code snippet for '%&gt;%' operator</Description>
      <Author>Microsoft Corporation</Author>
      <SnippetTypes>
        <SnippetType>Expansion</SnippetType>
       </SnippetTypes>
    </Header>
    <Snippet>
      <Code Language="R">
        <![CDATA[ %>% $end$]]>
      </Code>
    </Snippet>
  </CodeSnippet>
</CodeSnippets>
```

Les fichiers XML de tous les extraits de code sont installés avec RTVS. Le champ **Emplacement** du **Gestionnaire des extraits de code** fournit le chemin. Vous pouvez également les trouver dans le code source RTVS sur GitHub sous [src/Package/Impl/Snippets](https://github.com/Microsoft/RTVS/tree/master/src/Package/Impl/Snippets).
