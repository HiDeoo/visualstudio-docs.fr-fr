---
title: 'Didacticiel : étendre une application console C# simple'
description: Découvrez comment développer une application console C# dans Visual Studio, étape par étape.
ms.custom: get-started
ms.date: 07/09/2020
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
ms.topic: tutorial
ms.devlang: CSharp
author: ghogen
ms.author: ghogen
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 981f18857beb83ef2a4902f50985ca8e9f7ed901
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "88507954"
---
# <a name="tutorial-extend-a-simple-c-console-app"></a>Didacticiel : étendre une application console C# simple

Dans ce didacticiel, vous allez apprendre à utiliser Visual Studio pour étendre l’application console que vous avez créée dans la première partie. Vous apprendrez quelques-unes des fonctionnalités de Visual Studio dont vous aurez besoin pour le développement quotidien, telles que la gestion de plusieurs projets et le référencement de packages tiers.

Si vous venez de terminer la [première partie](tutorial-console.md) de cette série, vous disposez déjà de l’application console Calculator.  Pour ignorer la partie 1, vous pouvez commencer par ouvrir le projet à partir d’un référentiel GitHub. L’application Calculatrice C# se trouve dans le [référentiel vs-Tutorial-Samples](https://github.com/MicrosoftDocs/vs-tutorial-samples). vous pouvez donc simplement suivre les étapes du [Didacticiel : ouvrir un projet à partir d’un référentiel](../tutorial-open-project-from-repo.md) pour commencer.

## <a name="add-a-new-project"></a>Ajouter un nouveau projet

Le code réel implique de nombreux projets qui fonctionnent ensemble dans une solution. À présent, nous allons ajouter un autre projet à l’application Calculatrice. Il s’agit d’une bibliothèque de classes qui fournit certaines fonctions de calculatrice.

1. Dans Visual Studio, vous pouvez utiliser le **fichier**de commandes de menu de niveau supérieur  >  **Ajouter**  >  un**nouveau projet** pour ajouter un nouveau projet, mais vous pouvez également cliquer avec le bouton droit sur le nom de projet existant (appelé « nœud de projet ») et ouvrir le menu contextuel du projet (ou menu contextuel). Ce menu contextuel contient de nombreuses façons d’ajouter des fonctionnalités à vos projets. Cliquez avec le bouton droit sur le nœud de votre projet dans **Explorateur de solutions**, puis choisissez **Ajouter**  >  **un nouveau projet**.

1. Choisissez la bibliothèque de classes de modèles de projet C# **(.NET standard)**.

   ![Capture d’écran de la sélection du modèle de projet de bibliothèque de classes](media/vs-2019/calculator2-add-project-dark.png)

1. Tapez le nom du projet **CalculatorLibrary**, puis choisissez **créer**. Visual Studio crée le projet et l’ajoute à la solution.

   ![Capture d’écran de Explorateur de solutions avec le projet de bibliothèque de classes CalculatorLibrary ajouté](media/vs-2019/calculator2-solution-explorer-with-class-library-dark2.png)

1. Au lieu d’avoir *Class1.cs*, renommez le fichier **CalculatorLibrary.cs**. Vous pouvez cliquer sur le nom dans **Explorateur de solutions** pour le renommer, ou cliquer avec le bouton droit et choisir **Renommer**, ou appuyer sur la touche **F2** .

   Vous pouvez être invité à indiquer si vous souhaitez renommer toutes les références à `Class1` dans le fichier. Peu importe la façon dont vous répondez, puisque vous allez remplacer le code dans une étape ultérieure.

1. Nous devons maintenant ajouter une référence de projet, de sorte que le premier projet puisse utiliser des API exposées par la nouvelle bibliothèque de classes.  Cliquez avec le bouton droit sur le nœud **références** dans le premier projet, puis choisissez **Ajouter une référence de projet**.

   ![Capture d’écran de l’élément de menu Ajouter une référence de projet](media/vs-2019/calculator2-add-project-reference-dark.png)

   La boîte de dialogue **Gestionnaire de références** s’affiche. Cette boîte de dialogue vous permet d’ajouter des références à d’autres projets, ainsi que des assemblys et des DLL COM dont vos projets ont besoin.

   ![Capture d’écran de la boîte de dialogue Gestionnaire de références](media/vs-2019/calculator2-ref-manager-dark.png)

1. Dans la boîte de dialogue **Gestionnaire de références** , cochez la case du projet **CalculatorLibrary** , puis choisissez **OK**.  La référence de projet apparaît sous un nœud **projets** dans **Explorateur de solutions**.

   ![Capture d’écran de Explorateur de solutions avec la référence de projet](media/vs-2019/calculator2-solution-explorer-with-project-reference-dark2.png)

1. Dans *Program.cs*, sélectionnez la `Calculator` classe et tout son code, puis appuyez sur **CTRL + X** pour la couper de Program.cs. Ensuite, dans **CalculatorLibrary**, dans *CalculatorLibrary.cs*, collez le code dans l' `CalculatorLibrary` espace de noms. Ensuite, faites de la classe Calculator `public` pour l’exposer en dehors de la bibliothèque. Le code de *CalculatorLibrary.cs* doit maintenant ressembler au code suivant :

   ```csharp
   using System;

    namespace CalculatorLibrary
    {
        public class Calculator
        {
            public static double DoOperation(double num1, double num2, string op)
            {
                double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error.

                // Use a switch statement to do the math.
                switch (op)
                {
                    case "a":
                        result = num1 + num2;
                        break;
                    case "s":
                        result = num1 - num2;
                        break;
                    case "m":
                        result = num1 * num2;
                        break;
                    case "d":
                        // Ask the user to enter a non-zero divisor.
                        if (num2 != 0)
                        {
                            result = num1 / num2;
                        }
                        break;
                    // Return text for an incorrect option entry.
                    default:
                        break;
                }
                return result;
            }
        }
    }
   ```

1. Le premier projet a une référence, mais vous verrez une erreur indiquant que l’appel Calculator. nooperation ne se résout pas. Étant donné que CalculatorLibrary se trouve dans un espace de noms de différence, ajoutez l' `CalculatorLibrary` espace de noms pour une référence qualifiée complète.

   ```csharp
   result = CalculatorLibrary.Calculator.DoOperation(cleanNum1, cleanNum2, op);
   ```

   Essayez d’ajouter une directive using au début du fichier à la place :

   ```csharp
   using CalculatorLibrary;
   ```

   Cette modification devrait vous permettre de supprimer l’espace de noms CalculatorLibrary du site d’appel, mais il y a maintenant une ambiguïté. La classe est-elle `Calculator` dans CalculatorLibrary, ou est-ce que l’espace de noms ?  Pour résoudre l’ambiguïté, renommez l’espace de noms `CalculatorProgram` .

   ```csharp
   namespace CalculatorProgram
   ```

## <a name="reference-net-libraries-write-to-a-log"></a>Référencer des bibliothèques .NET : écrire dans un journal

1. Supposons que vous souhaitez maintenant ajouter un journal de toutes les opérations et l’écrire dans un fichier texte. La `Trace` classe .NET fournit cette fonctionnalité. (C’est également utile pour les techniques de débogage d’impression de base.)  La classe trace se trouve dans System. Diagnostics. par conséquent, commencez par ajouter une directive using :

   ```csharp
   using System.Diagnostics;
   ```

1. En examinant la façon dont la classe trace est utilisée, vous devez conserver une référence pour la classe, qui est associée à un FileStream. Cela signifie que la calculatrice fonctionne mieux sous la forme d’un objet. nous allons donc ajouter un constructeur.

   ```csharp
   public Calculator()
        {
            StreamWriter logFile = File.CreateText("calculator.log");
            Trace.Listeners.Add(new TextWriterTraceListener(logFile));
            Trace.AutoFlush = true;
            Trace.WriteLine("Starting Calculator Log");
            Trace.WriteLine(String.Format("Started {0}", System.DateTime.Now.ToString()));
        }

    public double DoOperation(double num1, double num2, string op)
        {
   ```

1. Et nous devons changer la méthode statique `DoOperation` en une méthode de membre.  Nous allons également ajouter la sortie à chaque calcul pour le journal, de sorte que l’opération de l’action ressemble au code suivant :

   ```csharp
   public double DoOperation(double num1, double num2, string op)
   {
        double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error.

        // Use a switch statement to do the math.
        switch (op)
        {
            case "a":
                result = num1 + num2;
                Trace.WriteLine(String.Format("{0} + {1} = {2}", num1, num2, result));
                break;
            case "s":
                result = num1 - num2;
                Trace.WriteLine(String.Format("{0} - {1} = {2}", num1, num2, result));
                break;
            case "m":
                result = num1 * num2;
                Trace.WriteLine(String.Format("{0} * {1} = {2}", num1, num2, result));
                break;
            case "d":
                // Ask the user to enter a non-zero divisor.
                if (num2 != 0)
                {
                    result = num1 / num2;
                    Trace.WriteLine(String.Format("{0} / {1} = {2}", num1, num2, result));
                }
                    break;
            // Return text for an incorrect option entry.
            default:
                break;
        }
        return result;
    }
   ```

1. À présent, dans Program.cs, l’appel statique est marqué d’un trait ondulé rouge. Pour résoudre ce problème, créez une `calculator` variable en ajoutant la ligne suivante juste avant la boucle while :

   ```csharp
   Calculator calculator = new Calculator();
   ```

   Et modifiez le site d’appel de `DoOperation` comme suit :

   ```csharp
   result = calculator.DoOperation(cleanNum1, cleanNum2, op);
   ```

1. Réexécutez le programme, puis, lorsque vous avez terminé, cliquez avec le bouton droit sur le nœud du projet et choisissez **ouvrir le dossier dans l’Explorateur de fichiers**, puis accédez au dossier de sortie dans l’Explorateur de fichiers. Il peut s’agir de *bin/debug/netcoreapp 3.1*et ouvrir le fichier *Calculator. log* .

    ```output
    Starting Calculator Log
    Started 7/9/2020 1:58:19 PM
    1 + 2 = 3
    3 * 3 = 9
    ```

## <a name="add-a-nuget-package-write-to-a-json-file"></a>Ajouter un package NuGet : écrire dans un fichier JSON

1. Supposons à présent que nous souhaitons générer les opérations au format JSON, un format très répandu et portable pour le stockage des données d’objet. Pour implémenter cette fonctionnalité, vous devez référencer le package NuGet Newtonsoft.Jssur. Les packages NuGet constituent le vecteur principal de distribution des bibliothèques de classes .NET. Dans **Explorateur de solutions**, cliquez avec le bouton droit sur le nœud **références** du projet CalculatorLibrary, puis choisissez **gérer les packages NuGet**.

   ![Capture d’écran de la gestion des packages NuGet dans le menu contextuel](media/vs-2019/calculator2-manage-nuget-packages-dark2.png)

   Le gestionnaire de package NuGet s’ouvre.

   ![Capture d’écran du Gestionnaire de package NuGet](media/vs-2019/calculator2-nuget-package-manager-dark.png)

1. Recherchez Newtonsoft.Jssur le package, puis choisissez **installer**.

   ![Capture d’écran des informations du package NuGet Newtonsoft](media/vs-2019/calculator2-nuget-newtonsoft-json-dark2.png)

   Le package est téléchargé et ajouté à votre projet et une nouvelle entrée s’affiche dans le nœud Références de **Explorateur de solutions**.

1. Ajoutez une directive using pour l' Newtonsoft.Jsdu package au début de *CalculatorLibrary.cs*.

   ```csharp
   using Newtonsoft.Json;
   ```

1. À présent, remplacez le constructeur de Calculator par le code suivant et créez l’objet membre JsonWriter :

   ```csharp
        JsonWriter writer;

        public Calculator()
        {
            StreamWriter logFile = File.CreateText("calculatorlog.json");
            logFile.AutoFlush = true;
            writer = new JsonTextWriter(logFile);
            writer.Formatting = Formatting.Indented;
            writer.WriteStartObject();
            writer.WritePropertyName("Operations");
            writer.WriteStartArray();
        }
   ```

1. Modifiez la `DoOperation` méthode pour ajouter le code du writer JSON :

   ```csharp
        public double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error.
            writer.WriteStartObject();
            writer.WritePropertyName("Operand1");
            writer.WriteValue(num1);
            writer.WritePropertyName("Operand2");
            writer.WriteValue(num2);
            writer.WritePropertyName("Operation");
            // Use a switch statement to do the math.
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    writer.WriteValue("Add");
                    break;
                case "s":
                    result = num1 - num2;
                    writer.WriteValue("Subtract");
                    break;
                case "m":
                    result = num1 * num2;
                    writer.WriteValue("Multiply");
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor.
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                        writer.WriteValue("Divide");
                    }
                    break;
                // Return text for an incorrect option entry.
                default:
                    break;
            }
            writer.WritePropertyName("Result");
            writer.WriteValue(result);
            writer.WriteEndObject();

            return result;
        }
   ```

1. Vous devez ajouter une méthode pour terminer la syntaxe JSON une fois que l’utilisateur a terminé d’entrer les données d’opération.

   ```csharp
    public void Finish()
    {
        writer.WriteEndArray();
        writer.WriteEndObject();
        writer.Close();
    }
   ```

1. Et dans *Program.cs*, ajoutez un appel pour terminer à la fin.

   ```csharp
            // And call to close the JSON writer before return
            calculator.Finish();
            return;
        }
   ```

1. Générez et exécutez l’application, et une fois que vous avez terminé d’entrer quelques opérations, fermez l’application correctement à l’aide de la commande « n ».  À présent, ouvrez le fichier consolelog.jssur et vous devriez voir un résultat semblable à ce qui suit :

   ```json
   {
    "Operations": [
        {
        "Operand1": 2.0,
        "Operand2": 3.0,
        "Operation": "Add",
        "Result": 5.0
        },
        {
        "Operand1": 3.0,
        "Operand2": 4.0,
        "Operation": "Multiply",
        "Result": 12.0
        }
    ]
   }
   ```

## <a name="next-steps"></a>Étapes suivantes

Félicitations ! Vous avez terminé ce didacticiel. Pour plus d’informations, passez aux tutoriels suivants.

> [!div class="nextstepaction"]
> [Continuer avec d’autres tutoriels C#](/dotnet/csharp/tutorials/)

> [!div class="nextstepaction"]
> [Continuer avec l’IDE de Visual Studio vue d’ensemble](/../visual-studio-ide.md)

## <a name="see-also"></a>Voir aussi

* [C# IntelliSense](../../ide/visual-csharp-intellisense.md)
* [Apprendre à déboguer du code C# dans Visual Studio](tutorial-debugger.md)
