---
title: Apprenez à déboguer les applications multithread
description: Débogage en utilisant les fenêtres Espion parallèle et les piles parallèles dans Visual Studio
ms.custom: H1HackMay2017
ms.date: 08/01/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multithreaded debugging, tutorial
- tutorials, multithreaded debugging
ms.assetid: 62df746b-b0f6-4df4-83cf-b1d9d2e72833
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 11cb05ea81f086cf8c26e3058850968a909b84e3
ms.sourcegitcommit: 0cf1e63b6e0e6a0130668278489b21a6e5038084
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39468681"
---
# <a name="get-started-debugging-multithreaded-applications-in-visual-studio"></a>Commencer le débogage d’applications multithread dans Visual Studio
Visual Studio fournit plusieurs outils et les éléments d’interface utilisateur pour vous aider à déboguer les applications multithread. Ce didacticiel montre comment utiliser des marqueurs de thread, le **piles parallèles** fenêtre, le **espion parallèle** fenêtre, points d’arrêt conditionnels et les points d’arrêt de filtre. Ce didacticiel vous prendra que quelques minutes, mais comment la compléter vous familiarisera avec les fonctionnalités de débogage d’applications multithread.

|         |         |
|---------|---------|
|  ![Icône représentant une caméra pour les vidéos](../install/media/video-icon.png "Regarder une vidéo")  |    [Regardez une vidéo](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugging-Multi-threaded-Apps-in-Visual-Studio-2017-MoZPKMD6D_111787171) sur le débogage multithread qui montre des étapes similaires. |

Autres rubriques fournissent des informations supplémentaires sur l’utilisation d’autres outils de débogage multithreads :

- Pour une rubrique similaire qui montre comment utiliser le **emplacement de débogage** barre d’outils et les **Threads** fenêtre, consultez [procédure pas à pas : déboguer une Application multithread](../debugger/how-to-use-the-threads-window.md).

- Pour une rubrique similaire avec un exemple qui utilise <xref:System.Threading.Tasks.Task> (code managé) et le runtime d’accès concurrentiel (C++), consultez [procédure pas à pas : débogage d’une Application parallèle](../debugger/walkthrough-debugging-a-parallel-application.md). Pour des conseils de débogage générales qui s’appliquent aux types d’applications multithreads plus, lisez cette rubrique et la rubrique liée.
  
Pour commencer ce didacticiel, vous avez besoin d’un projet d’application multithread. Pour créer ce projet, procédez comme suit.  
  
#### <a name="to-create-the-multithreaded-app-project"></a>Pour créer le projet d’application multithread  
  
1.  Sur le **fichier** menu, choisissez **New** puis cliquez sur **projet**.  
  
     La boîte de dialogue **Nouveau projet** s’affiche.  
  
2.  Cliquez sur le langage de votre choix : **Visual C#**, **Visual C++**, ou **Visual Basic**.  
  
3.  Sous **Windows Desktop**, choisissez **application Console**.  
  
4.  Dans le **nom** zone, entrez le nom MyThreadWalkthroughApp.  
  
5.  Cliquez sur **OK**.  
  
     Un nouveau projet console s'affiche. Lorsque le projet a été créé, un fichier source s'affiche. Selon le langage que vous avez choisi, le fichier source peut être appelé Program.cs ou MyThreadWalkthroughApp.cpp Module1.vb.  
  
6.  Supprimez le code qui s’affiche dans le fichier source et remplacez-le par l’exemple de code indiqué ici.

    ```csharp
    using System;
    using System.Threading;

    public class ServerClass
    {

        static int count = 0;
        // The method that will be called when the thread is started.
        public void InstanceMethod()
        {
            Console.WriteLine(
                "ServerClass.InstanceMethod is running on another thread.");

            int data = count++;
            // Pause for a moment to provide a delay to make
            // threads more apparent.
            Thread.Sleep(3000);
            Console.WriteLine(
                "The instance method called by the worker thread has ended.");
        }
    }

    public class Simple
    {
        public static void Main()
        {
            for (int i = 0; i < 10; i++)
            {
                CreateThreads();
            }
        }
        public static void CreateThreads()
        {
            ServerClass serverObject = new ServerClass();

            Thread InstanceCaller = new Thread(new ThreadStart(serverObject.InstanceMethod));
            // Start the thread.
            InstanceCaller.Start();

            Console.WriteLine("The Main() thread calls this after "
                + "starting the new InstanceCaller thread.");

        }
    }
    ```

    ```C++
    #include "stdafx.h"
    #include <thread>
    #include <iostream>
    #include <vector>

    using namespace;

    int count = 0;

    void doSomeWork() {

        cout << "The doSomeWork function is running on another thread." << endl;
        int data = count++;
        // Pause for a moment to provide a delay to make
        // threads more apparent.
        this_thread::sleep_for(chrono::seconds(3));
        cout << "The function called by the worker thread has ended." << endl;
    }

    int main() {
        vector<thread> threads;

        for (int i = 0; i < 10; ++i) {

            threads.push_back(thread(doSomeWork));
            cout << "The Main() thread calls this after starting the new thread" << endl;
        }

        for (auto& thread : threads) {
            thread.join();
        }

        return 0;
    }
    ```

    ```VB
    Imports System.Threading

    Public Class ServerClass
        ' The method that will be called when the thread is started.
        Public count = 0
        Public Sub InstanceMethod()
            Console.WriteLine(
                    "ServerClass.InstanceMethod is running on another thread.")

            Dim data = count + 1
            ' Pause for a moment to provide a delay to make
            ' threads more apparent.
            Thread.Sleep(3000)
            Console.WriteLine(
                    "The instance method called by the worker thread has ended.")
        End Sub

    End Class

    Public Class Simple

        Public Shared Sub Main()

            Dim ts As New ThreadStarter
            For index = 1 To 10
                ts.CreateThreads()
            Next

        End Sub

    End Class
    Public Class ThreadStarter
        Public Sub CreateThreads()
            Dim serverObject As New ServerClass()

            ' Create the thread object, passing in the
            ' serverObject.InstanceMethod method using a
            ' ThreadStart delegate.
            Dim InstanceCaller As New Thread(AddressOf serverObject.InstanceMethod)

            ' Start the thread.
            InstanceCaller.Start()

            Console.WriteLine("The Main() thread calls this after " _
                        + "starting the new InstanceCaller thread.")

        End Sub
    End Class
    ```
  
7.  Sur le **fichier** menu, cliquez sur **Enregistrer tout**.  
  
#### <a name="to-begin-the-tutorial"></a>Pour commencer le didacticiel  
  
-   Dans l’éditeur de code source, recherchez le code suivant : 
  
    ```csharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    this_thread::sleep_for(chrono::seconds(3));
    cout << "The function called by the worker thread has ended." << endl; 
    ```  

    ```VB
    Thread.Sleep(3000)
    Console.WriteLine()
    ```
  
#### <a name="to-start-debugging"></a>Pour démarrer le débogage  
  
1.  Cliquez dans la marge gauche de la `Thread.Sleep` ou `this_thread::sleep_for` instruction pour insérer un nouveau point d’arrêt.  
  
     Dans la marge à gauche de l’éditeur de code source, un cercle rouge apparaît. Cette bille indique qu'un point d'arrêt est désormais défini à cet emplacement. 
  
2.  Sur le **déboguer** menu, cliquez sur **démarrer le débogage** (**F5**).  
  
     Visual Studio génère la solution, l’application commence à s’exécuter avec le débogueur attaché, puis l’application s’arrête au point d’arrêt.  
  
    > [!NOTE]
    > Si vous basculez le focus vers la fenêtre de console, cliquez sur dans le [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] fenêtre pour retourner le focus à [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
4.  Dans l’éditeur de code source, recherchez la ligne qui contient le point d’arrêt :  
  
    ```csharp  
    Thread.Sleep(3000);  
    ```  
  
    ```C++  
    this_thread::sleep_for(chrono::seconds(3)); 
    ```

    ```VB
    Thread.Sleep(3000)
    ```    
  
#### <a name="ShowThreadsInSource"></a>Pour découvrir le marqueur de thread  

1.  Dans la barre d’outils Déboguer, cliquez sur le **afficher les Threads dans la Source** bouton ![afficher les Threads dans la Source](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker").

2. Appuyez sur **F11** une fois pour la débogueur une ligne de code d’avance.
  
3.  Examinez la reliure située sur le côté gauche de la fenêtre. Sur cette ligne, vous verrez un *marqueur de thread* icône ![marqueur de Thread](../debugger/media/dbg-thread-marker.png "ThreadMarker") qui ressemble à deux threads de maillage. Le marqueur de thread indique qu'un thread est interrompu à cet emplacement.

    Notez qu’un marqueur de thread peut être partiellement masqué par un point d’arrêt. 
  
4.  Placez le pointeur sur le marqueur de thread. Un DataTip apparaît. Le DataTip vous indique le nom et le numéro d'ID de thread de chaque thread interrompu. Dans ce cas, le nom est probablement `<noname>`. 
  
5.  Cliquez sur le marqueur de thread pour afficher les options disponibles dans le menu contextuel.
    
## <a name="ParallelStacks"></a>Afficher l’emplacement de Threads

Dans le **piles parallèles** fenêtre, vous pouvez basculer entre une vue Threads et (pour la programmation basée sur les tâches) vue tâches et vous pouvez afficher des informations de pile des appels pour chaque thread. Dans cette application, nous pouvons utiliser la vue Threads.

1. Ouvrez le **piles parallèles** fenêtre en choisissant **Déboguer > Windows > piles parallèles**. Vous devez voir quelque chose de similaire à ceci (les informations exactes sera différentes selon l’emplacement actuel de chaque thread, votre matériel et votre langage de programmation).

    ![Fenêtre des piles parallèles](../debugger/media/dbg-multithreaded-parallel-stacks.png "ParallelStacksWindow")

    Dans cet exemple, de gauche à droite nous obtenir ces informations pour le code managé :
    
    - Le thread principal (côté gauche) a été arrêté sur `Thread.Start` (du point d’arrêt est indiqué par l’icône de marqueur de thread ![marqueur de Thread](../debugger/media/dbg-thread-marker.png "ThreadMarker")).
    - Deux threads ont entré le `ServerClass.InstanceMethod`, un d'entre eux est le thread actuel (flèche jaune), tandis que l’autre thread a cessé dans `Thread.Sleep`.
    - Un nouveau thread (à droite) démarre également (arrêté sur `ThreadHelper.ThreadStart`).

2.  Avec le bouton droit des entrées dans le **piles parallèles** fenêtre pour voir les options disponibles dans le menu contextuel.

    Vous pouvez effectuer différentes actions à partir de ces menus contextuels, mais pour ce didacticiel, nous allons présenter plusieurs de ces détails dans le **espion parallèle** fenêtre (sections suivantes).

    > [!NOTE]
    > Si vous ne souhaitez plus voir une liste permet d’afficher des informations sur chaque thread, utilisez la **Threads** fenêtre à la place. Consultez [procédure pas à pas : déboguer une Application multithread](../debugger/how-to-use-the-threads-window.md).

## <a name="set-a-watch-on-a-variable"></a>Définir un espion sur une Variable

1. Ouvrez le **espion parallèle** fenêtre en choisissant **Déboguer > Windows > espion parallèle > espion parallèle 1**.

2. Cliquez sur la cellule où vous voyez la `<Add Watch>` texte (ou la cellule d’en-tête vide dans la 4e colonne), type `data`, et appuyez sur ENTRÉE.

    Les valeurs de la variable de données pour chaque thread s’affichent dans la fenêtre.

3. Cliquez à nouveau dans la cellule où vous voyez la `<Add Watch>` texte (ou la cellule d’en-tête vide dans la colonne 5), type `count`, et appuyez sur ENTRÉE.

    Les valeurs de la variable de compteur pour chaque thread s’affichent dans la fenêtre. (Si vous ne voyez pas encore autant d’informations, essayez d’appuyer sur F11 à plusieurs reprises pour faire avancer l’exécution des threads dans le débogueur.)

    ![Fenêtre Espion parallèle](../debugger/media/dbg-multithreaded-parallel-watch.png "ParallelWatchWindow")

4. Cliquez sur un des lignes dans la fenêtre pour voir les options disponibles.

## <a name="flagging-and-unflagging-threads"></a>Ajout et suppression d'indicateur de threads  
Vous pouvez marquer les threads auxquels vous souhaitez accorder une attention particulière. Marquage des threads est un bon moyen pour effectuer le suivi des threads importants et ignorer les threads que vous ne vous souciez pas.  
  
#### <a name="to-flag-threads"></a>Pour ajouter des indicateurs de thread  

1. Dans le **espion parallèle** fenêtre, maintenez la touche MAJ ENFONCÉE et sélectionnez plusieurs lignes.

2. Avec le bouton droit et choisissez **indicateur**.

    À présent, tous les threads sélectionnés sont signalés. Maintenant, vous pouvez filtrer pour afficher uniquement les threads avec indicateur.
  
3.  Dans le **espion parallèle** fenêtre, recherchez le **afficher uniquement les Threads avec indicateur** bouton ![afficher les Threads avec indicateur](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker").  
  
4.  Cliquez sur le **afficher uniquement les Threads avec indicateur** bouton.  
  
    Seul le thread avec indicateur s'affiche désormais dans la liste.

    > [!TIP]
    > Lorsque vous avez des threads avec indicateur, vous pouvez cliquez sur une ligne de code dans l’éditeur de code et choisissez **exécuter les Threads avec indicateur au curseur** (veillez à choisir le code que tous les threads avec indicateur atteindront). Cela va suspendre des threads sur la ligne sélectionnée de code, ce qui facilite contrôler l’ordre d’exécution par [gel et libération des threads](#bkmk_freeze).

5.  Cliquez sur le **afficher uniquement les Threads avec indicateur** bouton pour revenir au **afficher tous les Threads** mode.
    
#### <a name="to-unflag-threads"></a>Pour supprimer l'indicateur de threads

Pour supprimer l’indicateur de threads, vous pouvez cliquer sur un ou plusieurs threads avec indicateur dans le **espion parallèle** fenêtre et choisissez **supprimer l’indicateur**.

## <a name="bkmk_freeze"></a> Gel et libération de l’exécution du thread 

> [!TIP]
> Vous pouvez figer et libérer (suspendre et reprendre) les threads pour contrôler l’ordre dans lequel threads exécutent le travail. Cela peut vous aider à résoudre les problèmes d’accès concurrentiel tels que les interblocages et conditions de concurrence critique.
  
#### <a name="to-freeze-and-unfreeze-threads"></a>Pour figer et dégeler les threads  
  
1.  Dans le **espion parallèle** fenêtre, avec toutes les lignes sélectionnées, le bouton droit et sélectionnez **Figer**.

    Dans la deuxième colonne, une icône de pause apparaît maintenant pour chaque ligne. L’icône de pause indique que le thread est figé.

2.  Désélectionnez les lignes en cliquant sur une seule ligne.

3.  Cliquez sur une ligne et sélectionnez **libérer**.

    L’icône de pause disparaît sur cette ligne, indiquant que le thread est figé n’est plus.

4.  Basculez vers l’éditeur de code et cliquez sur **F11**. Seul le thread non figé s’exécute.

    L’application peut également instancier certains nouveaux threads. Notez que les nouveaux threads sont sans indicateur et ne sont pas gelés.

## <a name="bkmk_follow_a_thread"></a> Suivez un seul Thread à l’aide de points d’arrêt conditionnels

Parfois, il peut être utile de suivre l’exécution d’un thread unique dans le débogueur. Une façon vous pouvez le faire consiste à bloquer les threads qui vous n'intéresse pas, mais dans certains scénarios vous pouvez souhaiter suivre un seul thread sans bloquer les autres threads (à la reproduction des bogues un particulier, par exemple). Pour suivre un thread sans bloquer les autres threads, vous devez éviter d’arrêt dans le code, à l’exception sur le thread qui vous intéresse. Vous pouvez le faire en définissant un [point d’arrêt conditionnel](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression).

Vous pouvez définir des points d’arrêt sur les différentes conditions, telles que le nom du thread ou l’ID de thread. Une autre méthode qui peut être utile consiste à définir la condition sur les données que vous savez sera unique à chaque thread. Il s’agit d’un scénario de débogage courantes, dans lequel vous êtes plus intéressé par une valeur de données particulière que dans n’importe quel thread particulier.

#### <a name="to-follow-a-single-thread"></a>Pour suivre un thread unique

1. Cliquez sur le point d’arrêt que vous avez créé précédemment et choisissez **Conditions**.

2. Dans le **les paramètres de point d’arrêt** fenêtre, tapez `data == 5` pour l’expression conditionnelle.

    ![Point d’arrêt conditionnel](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "ConditionalBreakpoint")

    > [!TIP]
    > Si vous êtes plus intéressé par un thread spécifique, puis utiliser un nom de thread ou un ID de thread pour la condition. Pour ce faire, le **les paramètres de point d’arrêt** fenêtre, sélectionnez **filtre** au lieu de **expression conditionnelle**et suivez les conseils de filtre. Voulez-vous nommer vos threads dans le code de votre application (étant donné que les ID de threads changer lorsque vous redémarrez le débogueur).

3. Fermer le **les paramètres de point d’arrêt** fenêtre.

4. Cliquez sur le redémarrage ![redémarrer une application](../debugger/media/dbg-tour-restart.png "RestartApp") bouton redémarrer votre session de débogage.

    Vous vous introduirez dans le code sur le thread pour lequel la variable de données est 5. Recherchez la flèche jaune (contexte actuel du débogueur) le **espion parallèle** fenêtre pour vérifier que.

5. Maintenant, vous pouvez ignorer le code (F10) et pas à pas détaillé (F11) de code et suivre l’exécution du thread unique.

    Tant que la condition de point d’arrêt est unique pour le thread, et le débogueur n’appuyez sur n’importe quel autre point d’arrêt sur d’autres threads (vous devrez peut-être désactiver les), vous pouvez ignorer le code et détaillé du code sans basculer vers d’autres threads.

    > [!NOTE]
    > Lorsque vous arrivez le débogueur, tous les threads seront exécutera. Toutefois, le débogueur ne s’arrête dans du code sur d’autres threads, sauf si un des autres threads atteint un point d’arrêt. 
  
## <a name="more-about-the-multithreaded-debugging-windows"></a>Plus d’informations sur les fenêtres de débogage multithreads 

#### <a name="to-switch-to-another-thread"></a>Pour basculer vers un autre thread 

- Pour basculer vers un autre thread, consultez [Comment : basculer vers un autre Thread pendant le débogage](../debugger/how-to-switch-to-another-thread-while-debugging.md) 

#### <a name="to-learn-more-about-the-parallel-stack-and-parallel-watch-windows"></a>Pour en savoir plus sur les fenêtres pile parallèles et Espion parallèle  
  
- Consultez [Comment : utiliser la fenêtre Pile parallèles](../debugger/using-the-parallel-stacks-window.md) 

- Consultez [Comment : utiliser la fenêtre Espion parallèle](../debugger/how-to-use-the-parallel-watch-window.md) 
  
## <a name="see-also"></a>Voir aussi  
 [Déboguer les Applications multithread](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Guide pratique pour basculer vers un autre thread pendant un débogage](../debugger/how-to-switch-to-another-thread-while-debugging.md)
