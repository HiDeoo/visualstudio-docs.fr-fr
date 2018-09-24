---
title: Présentation de l’édition
ms.date: 11/30/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 420250a9e8dc99d6a02505efa7efb8f44e287e12
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42626741"
---
# <a name="learn-to-use-the-code-editor"></a>Apprendre à utiliser l’éditeur de code

Dans cette présentation de 10 minutes de l’éditeur de code de Visual Studio, vous allez ajouter du code dans un fichier pour découvrir de quelles façons Visual Studio facilite l’écriture, la navigation et la compréhension du code.

Si vous n’avez pas encore installé Visual Studio, accédez à la page [Téléchargements Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) pour l’installer gratuitement.

Cet article part du principe que vous connaissez déjà un langage de programmation. Si ce n’est pas le cas, nous vous suggérons de commencer par consulter l’un des guides de démarrage rapide de programmation, par exemple, créer une application web en [Python](../ide/quickstart-python.md) ou en [C#](../ide/tutorial-csharp-aspnet-core.md), ou créer une application de console en [Visual Basic](../ide/quickstart-visual-basic-console.md) ou en [C++](../ide/getting-started-with-cpp-in-visual-studio.md).

## <a name="create-a-new-code-file"></a>Créer un fichier de code

Vous allez commencer par créer un fichier et y ajouter du code.

1. Ouvrez Visual Studio et, dans le menu **Fichier** de la barre de menus, choisissez **Nouveau** > **Fichier**.

1. Dans la boîte de dialogue **Nouveau fichier**, sous la catégorie **Général**, choisissez **Classe Visual C#**, puis choisissez **Ouvrir**.

   Le nouveau fichier qui s’ouvre dans l’éditeur présente le squelette d’une classe C#. (Notez que nous ne sommes pas obligés de créer un projet Visual Studio complet pour bénéficier de certains des avantages offerts par l’éditeur de code. Tout ce dont nous avons besoin, c’est d’un fichier de code.)

   ![Fichier de code C# dans Visual Studio](media/quickstart-editor.png)

## <a name="use-code-snippets"></a>Utiliser des extraits de code

Visual Studio fournit des *extraits de code* qui vous aident à créer rapidement et facilement les blocs de code couramment utilisés. Ces [extraits de code](../ide/code-snippets.md) sont disponibles pour plusieurs langages de programmation, y compris C#, Visual Basic et C++. Vous allez maintenant ajouter l’extrait de code `void Main` C# dans votre fichier.

1. Placez votre curseur juste au-dessus de l’accolade fermante finale **}** dans le fichier et tapez les caractères `svm` (ce qui signifie `static void Main`&mdash;ne vous inquiétez pas trop si vous ne savez pas ce que cela veut dire).

   Une boîte de dialogue contextuelle affiche des informations relatives à l’extrait de code `svm`.

   ![IntelliSense pour l’extrait de code dans Visual Studio](media/quickstart-intellisense-snippet.png)

1. Appuyez deux fois sur **Tab** pour insérer l’extrait de code.

   La signature de la méthode `static void Main()` est ajoutée au fichier. La méthode [Main()](/dotnet/csharp/programming-guide/main-and-command-args/) est le point d’entrée pour les applications C#.

Les extraits de code disponibles diffèrent en fonction des langages de programmation. Pour voir quels extraits de code sont disponibles pour votre langage, choisissez **Edition** > **IntelliSense** > **Insérer un extrait de code**, puis choisissez le dossier de votre langage. Pour C#, la liste ressemble à ceci :

![Liste d’extraits de code C#](media/quickstart-code-snippet-list.png)

La liste contient des extraits de code permettant de créer une [classe](/dotnet/csharp/programming-guide/classes-and-structs/classes), un [constructeur](/dotnet/csharp/programming-guide/classes-and-structs/constructors), une boucle [for](/dotnet/csharp/language-reference/keywords/for), une instruction [if](/dotnet/csharp/language-reference/keywords/if-else) ou [switch](/dotnet/csharp/language-reference/keywords/switch), et bien d’autres éléments.

## <a name="comment-out-code"></a>Commenter du code

La barre d’outils, qui est la ligne de boutons sous la barre de menus dans Visual Studio, peut aider à augmenter votre productivité quand vous codez. Par exemple, vous pouvez basculer le mode de complétion IntelliSense ([IntelliSense](using-intellisense.md) est une aide au codage qui affiche entre autres une liste de méthodes correspondantes), augmenter ou réduire un retrait de ligne, ou commenter du code que vous ne souhaitez pas compiler. Dans cette section, nous allons commenter du code.

![Barre d’outils de l’éditeur](media/quickstart-editor-toolbar.png)

1. Collez le code suivant dans le corps de la méthode `Main()`.

    ```csharp
    // _words is a string array that we'll sort alphabetically
    string[] _words = {
        "the",
        "quick",
        "brown",
        "fox",
        "jumps"
    };

    string[] morewords = {
        "over",
        "the",
        "lazy",
        "dog"
    };

    IEnumerable<string> query = from word in _words
                                orderby word.Length
                                select word;
    ```

1. Nous n’avons pas besoin de la variable `morewords` ici, mais nous n’allons pas la supprimer complètement car nous en aurons peut-être besoin plus tard. Au lieu de cela, nous allons commenter ces lignes. Sélectionnez toute la définition de `morewords` jusqu’au point-virgule de fin, puis choisissez le bouton **Commenter les lignes sélectionnées** dans la barre d’outils. Si vous préférez utiliser le clavier, appuyez sur **Ctrl**+**K**, **Ctrl**+**C**.

   ![Bouton Commenter](media/quickstart-comment-out.png)

   Les caractères de commentaire C# `//` sont ajoutés au début de chaque ligne sélectionnée pour commenter le code.

## <a name="collapse-code-blocks"></a>Réduire les blocs de code

Nous n’avons pas besoin de voir le [constructeur](/dotnet/csharp/programming-guide/classes-and-structs/constructors) vide de `Class1` qui a été généré. Pour plus de lisibilité, nous allons donc réduire ce bloc de code. Choisissez la petite case grise avec le signe moins qui se trouve dans la marge de la première ligne du constructeur. Si vous préférez utiliser le clavier, placez le curseur n’importe où dans le code du constructeur et appuyez sur **Ctrl**+**M**, **Ctrl**+**M**.

![Bouton de réduction du mode Plan](media/quickstart-collapse.png)

Le bloc de code est réduit de façon à afficher uniquement la première ligne, suivie de points de suspension (`...`). Pour redévelopper le bloc de code, cliquez sur la même case grise, qui affiche maintenant un signe plus, ou appuyez sur **Ctrl**+**M**, **Ctrl**+**M**  à nouveau. Cette fonctionnalité, appelée [Mode Plan](../ide/outlining.md), est très utile pour réduire des méthodes longues ou des classes entières.

## <a name="view-symbol-definitions"></a>Afficher les définitions de symbole

L’éditeur de Visual Studio facilite l’inspection de la définition d’un type, d’une méthode, etc. Une façon de faire est d’accéder au fichier qui contient la définition, par exemple en choisissant **Atteindre la définition** à partir de n’importe quel endroit où le symbole est référencé. Une autre façon encore plus rapide, sans avoir à déplacer le focus en dehors du fichier dans lequel vous travaillez, consiste à utiliser la fonctionnalité [Aperçu de la définition](../ide/go-to-and-peek-definition.md#peek-definition). Vous allez afficher un aperçu de la définition du type `string`.

1. Cliquez avec le bouton droit sur une occurrence de `string`, puis choisissez **Aperçu de la définition** dans le menu de contenu. Ou bien, appuyez sur **Alt**+**F12**.

   Une fenêtre indépendante s’affiche, avec la définition de la classe `String`. Vous pouvez faire défiler le contenu de la fenêtre indépendante, ou même afficher un aperçu de la définition d’un autre type à partir du code en aperçu.

   ![Fenêtre Aperçu de la définition](media/quickstart-peek-definition.png)

1. Fermez la fenêtre Aperçu de la définition en choisissant la petite case avec un « x » dans le coin supérieur droit de la fenêtre indépendante.

## <a name="use-intellisense-to-complete-words"></a>Utiliser IntelliSense pour compléter des mots

[IntelliSense](../ide/using-intellisense.md) est une aide précieuse quand vous écrivez du code. Cette fonctionnalité peut afficher des informations sur les membres d’un type disponibles, ou les détails des paramètres des différentes surcharges d’une méthode. Vous pouvez également utiliser IntelliSense pour compléter un mot automatiquement quand vous avez tapé suffisamment de caractères pour lever toute ambiguïté sur le mot. Nous allons ajouter une ligne de code pour imprimer les chaînes ordonnées dans la fenêtre de console, qui est l’emplacement standard pour la sortie du programme.

1. Sous la variable `query`, commencez à taper le code suivant :

   ```csharp
   foreach (string str in qu
   ```

   IntelliSense affiche une **Info express** relative au symbole `query`.

   ![Complétion de mot IntelliSense dans Visual Studio](media/quickstart-intellisense-completion-list.png)

1. Pour insérer le reste du mot `query` à l’aide la fonctionnalité de complétion de mot d’IntelliSense, appuyez sur **Tab**.

1. Terminez le bloc de code pour obtenir le code suivant. Si vous voulez vous exercer un peu plus avec des extraits de code, entrez `cw` et appuyez deux fois sur **Tab** pour générer le code `Console.WriteLine`.

   ```csharp
   foreach (string str in query)
   {
      Console.WriteLine(str);
   }
   ```

## <a name="refactor-a-name"></a>Refactoriser un nom

Aucun développeur ne réussit à créer un code parfait dès le départ. L’une de vos premières modifications sera probablement de changer le nom d’une variable ou d’une méthode. Nous allons donc essayer la fonctionnalité [Refactoriser](../ide/refactoring-in-visual-studio.md) de Visual Studio pour renommer la variable `_words` en `words`.

1. Placez votre curseur sur la définition de la variable `_words`, puis choisissez **Renommer** dans le menu contextuel (clic droit), ou appuyez sur **Ctrl**+**R**, **Ctrl**+**R**.

   Une boîte de dialogue contextuelle **Renommer** s’affiche en haut à droite de l’éditeur.

1. Entrez le nom souhaité, **words**. Notez que la référence à `words` dans la requête est également renommée automatiquement. Avant d’appuyer sur **Entrée**, cochez la case **Inclure les commentaires** dans la boîte de dialogue contextuelle **Renommer**.

   ![Renommer (boîte de dialogue)](media/quickstart-rename.png)

1. Appuyez sur **Entrée**.

   Les deux occurrences de `words` ont été renommées, tout comme la référence à `words` dans le commentaire de code.

## <a name="next-steps"></a>Étapes suivantes

> [!div class="nextstepaction"]
> [Découvrir les projets et les solutions](../ide/quickstart-projects-solutions.md)

## <a name="see-also"></a>Voir aussi

- [Extraits de code](../ide/code-snippets.md)
- [Naviguer dans le code](../ide/navigating-code.md)
- [Mode Plan](../ide/outlining.md)
- [Atteindre la définition et Aperçu de la définition](../ide/go-to-and-peek-definition.md)
- [Refactorisation](../ide/refactoring-in-visual-studio.md)
- [Utiliser IntelliSense](../ide/using-intellisense.md)
