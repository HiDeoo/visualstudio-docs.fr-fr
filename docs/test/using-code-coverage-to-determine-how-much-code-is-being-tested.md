---
title: Couverture du code dans Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- code coverage
dev_langs:
- CSharp
- VB
- CPP
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 8dc6ff1e2813f1457e8a41328f759e8e27d9aa65
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279945"
---
# <a name="use-code-coverage-to-determine-how-much-code-is-being-tested"></a>Utiliser la couverture du code pour déterminer la quantité de code testé

Pour déterminer la proportion de code de votre projet qui sera réellement testée par des tests codés, par exemple des tests unitaires, recourez à la fonctionnalité de couverture du code de Visual Studio. Pour apporter une protection efficace contre les bogues, les tests doivent s'effectuer ou « couvrir » une proportion importante de votre code.

L'analyse de couverture du code peut être appliquée pour du code managé (CLI) et non managé (natif).

Vous pouvez avoir recours à la couverture du code lorsque vous exécutez des méthodes de test à l'aide de l'Explorateur de tests. La table des résultats affiche le pourcentage de code exécuté dans chaque assembly, classe et méthode. En outre, l'éditeur de code source vous indique quel code a été testé.

![Résultats de la couverture du code avec coloration](../test/media/codecoverage1.png)

 **Spécifications**

-   Visual Studio Enterprise

## <a name="to-analyze-code-coverage-on-unit-tests-in-test-explorer"></a>Pour analyser la couverture du code sur les tests unitaires dans l'Explorateur de tests

1.  Dans le menu **Test**, choisissez **Analyser la couverture du code**.

2.  Pour voir les lignes qui ont été exécutées, choisissez ![Icône Afficher la coloration de la couverture du code](../test/media/codecoverage-showcoloringicon.png)**Afficher la coloration de la couverture du code**.

     Pour changer les couleurs ou utiliser des caractères gras, choisissez **Outils** > **Options** > **Environnement** > **Polices et couleurs** > **Afficher les paramètres de : Éditeur de texte**. Sous **Éléments affichés**, ajustez les éléments de couverture.

3.  Si les résultats indiquent une couverture basse, recherchez les parties du code qui ne sont pas testées, puis élaborez d'autres tests pour les couvrir. Les équipes de développement visent généralement une couverture de code qui avoisine 80 %. Dans certaines situations, une couverture inférieure est acceptable. Par exemple, une couverture inférieure est acceptable lorsqu'un code est généré à partir d'un modèle standard.

> [!TIP]
> - Vérifiez que l’optimisation du compilateur est désactivée.
> - Si vous travaillez avec du code non managé (natif), utilisez une version Debug.
> - Vérifiez que vous générez des fichiers de symboles (.pdb) pour chaque assembly.

Si vous n’obtenez pas les résultats escomptés, consultez [Résolution des problèmes liés à la couverture du code](../test/troubleshooting-code-coverage.md). N’oubliez pas de réexécuter la couverture du code après la mise à jour de votre code. Les résultats de couverture et la coloration du code ne sont pas automatiquement mis à jour après avoir la modification de votre code ou lorsque vous exécutez des tests.

## <a name="report-in-blocks-or-lines"></a>Rapport pour les blocs ou les lignes

La couverture du code est mesurée en *blocs*. Un bloc est un fragment de code avec un seul point d'entrée et de sortie.  Si le flux de contrôle du programme traverse un bloc pendant une série de tests, ce bloc est considéré comme couvert. Le nombre de fois où le bloc est utilisé n'a aucun effet sur le résultat.

Les résultats peuvent également être affichés en termes de lignes si vous choisissez **Ajouter/supprimer des colonnes** dans l’en-tête du tableau. Si la série de tests a testé tous les blocs de code dans n'importe quelle ligne de code, le résultat considère qu'il s'agit d'une ligne. Si une ligne contient des blocs de code qui ont été testés et d'autres blocs qui ne l'ont pas été, le résultat considère qu'il s'agit d'une ligne partielle.

Certains utilisateurs préfèrent un nombre de lignes, car les pourcentages correspondent mieux à la taille des fragments que vous voyez dans le code source. Un long bloc de calcul serait considéré comme un seul bloc même s'il occupe plusieurs lignes.

## <a name="manage-code-coverage-results"></a>Gérer les résultats de la couverture du code

La fenêtre **Résultats de la couverture du code** affiche généralement le résultat de la série la plus récente. Les résultats varient si vous modifiez les données de test ou si vous exécutez uniquement certains de vos tests chaque fois.

La fenêtre de couverture du code peut également être utilisée pour afficher les résultats précédents ou des résultats obtenus sur d'autres ordinateurs.

Vous pouvez fusionner les résultats de plusieurs séries, par exemple les résultats de séries qui utilisent des données de test différentes.

-   **Pour afficher un ensemble de résultats antérieur**, sélectionnez-le dans le menu déroulant. Le menu affiche une liste temporaire qui est supprimée lorsque vous ouvrez une nouvelle solution.

-   **Pour afficher les résultats d’une session antérieure**, choisissez **Importer les résultats de la couverture du code**, accédez au dossier **TestResults** dans votre solution, puis importez un fichier *.coverage*.

    La coloration de couverture peut être incorrecte si le code source a été modifié depuis que le fichier *.coverage* a été généré.

-   **Pour afficher les résultats sous forme de texte**, choisissez **Exporter les résultats de la couverture du code**. Un fichier *.coveragexml* lisible est généré. Vous pouvez le traiter avec d’autres outils ou l’envoyer facilement par-email.

-   **Pour envoyer les résultats à une autre personne**, envoyez un fichier *.coverage* ou un fichier *.coveragexml* exporté. Cela permet ensuite à la personne d'importer le fichier. Si la personne a la même version de code source, elle a accès à la coloration de couverture.

## <a name="merge-results-from-different-runs"></a>Fusionner les résultats de différentes exécutions

Dans certains cas, différents blocs de votre code seront utilisés, en fonction des données de test. Par conséquent, vous pouvez souhaiter combiner les résultats des plusieurs séries de tests.

 Supposons par exemple que, lorsque vous exécutez un test avec l'entrée « 2 », vous constatez que 50 % d'une fonction spécifique est couvert. Lorsque vous exécutez le test une deuxième fois avec l'entrée « -2 », vous constatez dans la vue de coloration de couverture que le reste de la fonction (50 %) est couvert. Fusionnez maintenant les résultats des deux séries de tests. Le rapport et la vue de coloration de couverture indiquent que la fonction a été couverte à 100 %.

 Pour cela, utilisez ![Icône du bouton de fusion dans la fenêtre Couverture du code](../test/media/codecoverage-mergeicon.png)**Fusionner les résultats de la couverture du code**. Vous pouvez choisir n'importe quelle combinaison de séries récentes ou de résultats importés. Si vous souhaitez combiner des résultats exportés, vous devez d'abord les importer.

 Utilisez **Exporter les résultats de la couverture du code** pour enregistrer les résultats d’une opération de fusion.

### <a name="limitations-in-merging"></a>Limitations lors de la fusion

-   Si vous fusionnez des données de couverture de différentes versions du code, les résultats s'affichent séparément, mais ils ne sont pas combinés. Pour obtenir des résultats entièrement combinés, utilisez la même version du code et modifiez uniquement les données de test.

-   Si vous fusionnez un fichier de résultats qui a été exporté puis importé, vous pouvez uniquement consulter les résultats par lignes, et non pas par blocs. Utilisez la commande **Ajouter/supprimer des colonnes** pour afficher les données des lignes.

-   Si vous fusionnez les résultats des tests d’un projet ASP .NET, les résultats des tests distincts sont affichés, mais ils ne sont pas combinés. Cela s'applique uniquement aux artefacts ASP .NET eux-mêmes : les résultats de tous les autres assemblys sont combinés.

## <a name="exclude-elements-from-the-code-coverage-results"></a>Exclure des éléments des résultats de la couverture du code

Vous pouvez exclure des éléments spécifiques dans votre code à partir des notes de couverture, par exemple si le code est généré à partir d'un modèle de texte. Ajoutez l'attribut `System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverage` aux éléments de code suivants : classe, structure, méthode, propriété, accesseur Set ou accesseur Get de propriété, événement. Notez que l'exclusion d'une classe n'exclut pas ses classes dérivées.

 Exemple :

```csharp

using System.Diagnostics.CodeAnalysis;
...
public class ExampleClass1
{
    [ExcludeFromCodeCoverage]
    void ExampleMethod() {...}

    [ExcludeFromCodeCoverage] // exclude property
    int ExampleProperty1
    { get {...} set{...}}

    int ExampleProperty2
    {
        get
        {
            ...
        }
        [ExcludeFromCodeCoverage] // exclude setter
        set
        {
            ...
        }
    }

}
[ExcludeFromCodeCoverage]
class ExampleClass2 { ... }

```

```vb
Imports System.Diagnostics.CodeAnalysis

Class ExampleClass1
    <ExcludeFromCodeCoverage()>
    Public Sub ExampleSub1()
        ...
    End Sub

    ' Exclude property
    < ExcludeFromCodeCoverage()>
    Property ExampleProperty1 As Integer
        ...
    End Property

    ' Exclude setter
    Property ExampleProperty2 As Integer
        Get
            ...
        End Get
        <ExcludeFromCodeCoverage()>
        Set(ByVal value As Integer)
            ...
        End Set
    End Property
End Class

<ExcludeFromCodeCoverage()>
Class ExampleClass2
...
End Class
```

```cpp
// A .cpp file compiled as managed (CLI) code.
using namespace System::Diagnostics::CodeAnalysis;
...
public ref class ExampleClass1
{
  public:
    [ExcludeFromCodeCoverage]
    void ExampleFunction1() { ... }

    [ExcludeFromCodeCoverage]
    property int ExampleProperty2 {...}

    property int ExampleProperty2 {
      int get() { ... }
     [ExcludeFromCodeCoverage]
      void set(int value) { ...  }
   }
}

[ExcludeFromCodeCoverage]
public ref class ExampleClass2
{ ... }
```

### <a name="exclude-elements-in-native-c-code"></a>Exclure des éléments du code C++ natif

Pour exclure les éléments non managés (natifs) du code C++ :

```cpp
#include <CodeCoverage\CodeCoverage.h>
...

// Exclusions must be compiled as unmanaged (native):
#pragma managed(push, off)

// Exclude a particular function:
ExcludeFromCodeCoverage(Exclusion1, L"MyNamespace::MyClass::MyFunction");

// Exclude all the functions in a particular class:
ExcludeFromCodeCoverage(Exclusion2, L"MyNamespace::MyClass2::*");

// Exclude all the functions generated from a particular template:
ExcludeFromCodeCoverage(Exclusion3, L"*::MyFunction<*>");

// Exclude all the code from a particular .cpp file:
ExcludeSourceFromCodeCoverage(Exclusion4, L"*\\unittest1.cpp");

// After setting exclusions, restore the previous managed/unmanaged state:
#pragma managed(pop)
```

Utilisez les macros suivante :

 `ExcludeFromCodeCoverage(` *NomExclusion* `, L"` *NomFonction* `");`

 `ExcludeSourceFromCodeCoverage(` *NomExclusion* `, L"` *CheminFichierSource* `");`

-   *NomExclusion* est un nom unique.

-   *NomFonction* est un nom qualifié complet de fonction. Il peut contenir des caractères génériques. Par exemple, pour exclure toutes les fonctions d'une classe, écrivez `MyNamespace::MyClass::*`

-   *CheminFichierSource* est le chemin local ou UNC d’un fichier .cpp. Il peut contenir des caractères génériques. L'exemple suivant exclut tous les fichiers d'un répertoire particulier : `\\MyComputer\Source\UnitTests\*.cpp`

-   `#include <CodeCoverage\CodeCoverage.h>`

-   Placez les appels aux macros d'exclusion dans l'espace de noms global, et non dans un espace de noms ou dans une classe.

-   Vous pouvez placer les exclusions dans le fichier de code de test unitaire ou dans le fichier de code de l'application.

-   Les exclusions doivent être compilées en tant que code non managé (natif), en définissant l'option du compilateur ou à l'aide de `#pragma managed(off)`.

> [!NOTE]
> Pour exclure des fonctions dans le code C++/CLI, appliquez l'attribut `[System::Diagnostics::CodeAnalysis::ExcludeFromCodeCoverage]` à la fonction. La procédure est la même que pour C#.

### <a name="include-or-exclude-additional-elements"></a>Inclure ou exclure des éléments supplémentaires

L’analyse de la couverture du code est exécutée uniquement sur les assemblys chargés et pour lesquels un fichier *.pdb* est disponible dans le même répertoire que le fichier *.dll* ou *.exe*. Par conséquent, dans certains cas, vous pouvez étendre le jeu d’assemblys inclus par l’obtention des copies des fichiers *.pdb* appropriés.

Vous pouvez mieux contrôler les assemblys et les éléments qui sont sélectionnés pour l’analyse de la couverture du code en écrivant un fichier *.runsettings*. Par exemple, vous pouvez exclure des assemblys de type particulier sans devoir ajouter des attributs à leurs classes. Pour plus d’informations, consultez [Personnaliser l’analyse de la couverture du code](../test/customizing-code-coverage-analysis.md).

## <a name="analyze-code-coverage-in-azure-pipelines"></a>Analyse de la couverture du code dans Azure Pipelines

Lorsque vous archivez votre code, vos tests s’exécutent sur le serveur de builds, avec l’ensemble des tests des autres membres de l’équipe. (Si vous ne l’avez pas déjà fait, consultez [Exécuter des tests dans votre processus de génération](http://msdn.microsoft.com/Library/d05743a1-c5cf-447e-bed9-bed3cb595e38).) L’analyse de la couverture du code dans Azure Pipelines est pratique, car elle permet d’obtenir l’image la plus récente et la plus complète de la couverture du projet complet. Elle inclut également des tests système automatisés et d’autres tests codés qui ne sont généralement pas exécutés sur les ordinateurs de développement.

1. Dans **Team Explorer**, ouvrez **Builds**, puis ajoutez ou modifiez une définition de build.

2. Dans la page **Processus**, développez **Tests automatisés**, **Source de test**, **Paramètres d’exécution**. Affectez à **Type des paramètres d’exécution** la valeur **Couverture du code activée**.

   Si vous avez plusieurs définitions de source de test, répétez cette étape pour chaque définition.

   ![Définition de build pour la couverture du code](../test/media/codecoverage-plaincc.png)

> [!TIP]
> S’il n’existe aucun champ nommé **Type de fichier de paramètres d’exécution**, changez la propriété **Test Runner**. Sous **Tests automatisés**, sélectionnez **Assembly de test**, puis choisissez le bouton de sélection **[...]** situé à la fin de la ligne. Dans la boîte de dialogue **Ajouter/Modifier une série de tests**, sous **Test Runner**, choisissez **Visual Studio Test Runner**.

Après l'exécution de la build, les résultats de la couverture du code sont liés à la série de tests et s'affichent dans le résumé de la build.

## <a name="analyze-code-coverage-from-the-command-line"></a>Analyser la couverture du code depuis la ligne de commande

Pour exécuter des tests à partir de la ligne de commande, utilisez *vstest.console.exe*. La couverture du code est une option de l’utilitaire *vstest.console.exe*.

1.  Lancez l'invite de commandes développeur Visual Studio :

    Dans le menu **Démarrer** de Windows, choisissez **Visual Studio 2017** > **Invite de commandes développeur pour VS 2017**.

2.  Exécutez la commande suivante :

    `vstest.console.exe MyTestAssembly.dll /EnableCodeCoverage`

Pour plus d’informations, consultez [Options de ligne de commande VSTest.Console.exe](vstest-console-options.md).

## <a name="troubleshoot"></a>Résoudre les problèmes

Si vous ne voyez pas les résultats de la couverture du code, consultez la rubrique [Résoudre les problèmes liés à la couverture du code](../test/troubleshooting-code-coverage.md).

## <a name="see-also"></a>Voir aussi

- [Personnaliser l’analyse de la couverture du code](../test/customizing-code-coverage-analysis.md)
- [Dépannage de la couverture du code](../test/troubleshooting-code-coverage.md)
- [Tests unitaires sur votre code](../test/unit-test-your-code.md)
