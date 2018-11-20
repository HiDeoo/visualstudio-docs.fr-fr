---
title: 'Procédure pas à pas : Débogage d’un formulaire Web | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Web pages [.NET Framework], debugging
- Web sites [.NET Framework], debugging
- ASP.NET, debugging Web applications
- Web applications [.NET Framework], debugging
- ASP.NET Web sites, debugging
- ASP.NET Web pages, debugging
- debugging ASP.NET Web applications, Web Forms
- debugging [Visual Studio], Web Forms
ms.assetid: e2b4fa14-8f5b-444d-a903-54070b784bd4
caps.latest.revision: 34
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7024a9abc58117bf28ed78de107b1c17ddad601f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51747258"
---
# <a name="walkthrough-debugging-a-web-form"></a>Procédure pas à pas : débogage d'un formulaire Web
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Les étapes de cette procédure pas à pas vous expliquent comment déboguer une application Web [!INCLUDE[vstecasp](../includes/vstecasp-md.md)], également connue sous le nom de Web Form. Il vous montre comment démarrer et arrêter l’exécution, définir des points d’arrêt et examiner des variables dans le **espion** fenêtre.  
  
> [!NOTE]
>  Pour exécuter cette procédure pas à pas, vous devez avoir des privilèges d'administrateur de l'ordinateur serveur. Par défaut, le processus [!INCLUDE[vstecasp](../includes/vstecasp-md.md)], aspnet_wp.exe ou w3wp.exe, s'exécute comme un processus [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]. Pour déboguer [!INCLUDE[vstecasp](../includes/vstecasp-md.md)], vous devez avoir des privilèges d'administrateur sur l'ordinateur où [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] s'exécute. Pour plus d'informations, voir [System Requirements](../debugger/aspnet-debugging-system-requirements.md).  
  
 Selon vos paramètres actifs ou votre édition, les boîtes de dialogue et les commandes de menu affichées peuvent différer de celles qui sont décrites dans l'aide. Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnalisation des paramètres de développement dans Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-the-web-form"></a>Pour créer le Web Form  
  
1.  Si une solution est déjà ouverte, fermez-la.  
  
2.  Sur le **fichier** menu, cliquez sur **New**, puis cliquez sur **Site Web**.  
  
     Le **nouveau Site Web** boîte de dialogue s’affiche.  
  
3.  Dans le **modèles** volet, cliquez sur **Site Web ASP.NET**.  
  
4.  Sur le **emplacement** ligne, cliquez sur **HTTP** dans la liste et dans la zone de texte, tapez **http://localhost/WebSite**.  
  
5.  Dans le **langage** , cliquez sur **Visual C#** ou **Visual Basic**.  
  
6.  Cliquez sur **OK**.  
  
     [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] crée un projet et affiche le code source HTML par défaut. Il crée également un nouveau répertoire virtuel nommé **site Web** sous **Site Web par défaut** dans IIS.  
  
7.  Cliquez sur le **conception** onglet sur la marge inférieure.  
  
8.  Cliquez sur le **boîte à outils** onglet dans la marge gauche ou sélectionnez-le dans la **vue** menu.  
  
     La **Boîte à outils** s'ouvre.  
  
9. Dans le **boîte à outils**, cliquez sur le **bouton** contrôler et ajoutez-le à l’aire de conception principale, Default.aspx.  
  
10. Dans le **boîte à outils**, cliquez sur le **zone de texte** contrôler et faites glisser le contrôle vers l’aire de conception principale, Default.aspx.  
  
11. Double-cliquez sur le contrôle Button que vous avez déposé.  
  
     Cette opération vous permet d'atteindre la page de codes : Default.aspx.cs pour C# ou Default.aspx.vb pour [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]. Le curseur doit se trouver dans la fonction `Button1_Click`.  
  
12. Dans la fonction `Button1_Click`, ajoutez le code suivant :  
  
    ```  
    ' Visual Basic  
    TextBox1.Text = "Button was clicked!"  
  
    // C#  
    TextBox1.Text = "Button was clicked!";  
    ```  
  
13. Dans le menu **Générer** , cliquez sur **Générer la solution**.  
  
     Le projet doit être généré sans erreur.  
  
     Vous pouvez maintenant commencer le débogage.  
  
### <a name="to-debug-the-web-form"></a>Pour déboguer le Web FOrm  
  
1.  Dans la fenêtre Default.aspx.cs ou Default.aspx.vb, cliquez sur la marge gauche de la ligne sur laquelle vous avez ajouté le texte :  
  
    ```  
    ' Visual Basic  
    TextBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
    ```  
  
     Un point rouge s'affiche et le texte de la ligne est surligné en rouge. Le point rouge représente un point d'arrêt. Lorsque vous exécutez l'application dans le débogueur, le débogueur interrompt l'exécution à l'emplacement du code où se trouve ce point d'arrêt. Vous pouvez afficher l'état de votre application et la déboguer. Pour plus d’informations, consultez [des points d’arrêt](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583).  
  
2.  Dans le menu **Déboguer**, cliquez sur **Démarrer le débogage**.  
  
3.  Le **débogage non activé** boîte de dialogue s’affiche. Sélectionnez **modifier le fichier Web.config pour activer le débogage** option, puis cliquez sur **OK**.  
  
     Internet Explorer démarre et affiche la page que vous venez de créer.  
  
4.  Dans Internet Explorer, cliquez sur le bouton.  
  
     Dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], cette opération vous permet d'atteindre la ligne où vous définissez votre point d'arrêt sur la page de codes Default.aspx.cs ou Default.aspx.vb. Cette ligne doit être surlignée en jaune. Vous pouvez à présent afficher les variables de votre application et contrôler son exécution. Votre application s'arrête et attend une commande de votre part.  
  
5.  Sur le **déboguer** menu, cliquez sur **Windows**, puis cliquez sur **espion**, puis cliquez sur **Espion1**.  
  
6.  Dans le **espion** fenêtre, tapez **TextBox1.Text**.  
  
     Le **espion** fenêtre affiche la valeur de la variable `TextBox1.Text`:  
  
    ```  
    ""  
    ```  
  
7.  Sur le **déboguer** menu, cliquez sur **pas à pas principal**.  
  
     La valeur de `TextBox1.Text` change dans le **espion** fenêtre à lire :  
  
    ```  
    "Button was clicked!"  
    ```  
  
8.  Sur le **déboguer** menu, cliquez sur **continuer**.  
  
9. Dans Internet Explorer, cliquez de nouveau sur le bouton.  
  
     L'exécution s'arrête de nouveau sur le point d'arrêt.  
  
10. Dans la fenêtre Default.aspx.cs ou Default.aspx.vb, cliquez sur le point rouge dans la marge de gauche.  
  
     Cela supprime le point d'arrêt.  
  
11. Sur le **déboguer** menu, cliquez sur **arrêter le débogage**.  
  
### <a name="to-attach-to-the-web-form-for-debugging"></a>Pour attacher au Web Form pour le débogage  
  
1.  Dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], vous pouvez attacher le débogueur à un processus en cours d'exécution. Pour un débogage plus efficace, compilez le fichier exécutable sous forme de version Debug avec des fichiers de symboles (PDB).  
  
2.  Dans la fenêtre Default.aspx.cs ou Default.aspx.vb, cliquez dans la marge de gauche pour définir à nouveau un point d'arrêt à la ligne que vous avez ajoutée :  
  
    ```  
    ' Visual Basic  
    TextBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
    ```  
  
3.  Sur le **déboguer** menu, cliquez sur **démarrer sans débogage**.  
  
     Le Web Form commence à s'exécuter sous Internet Explorer, mais le débogueur n'est pas attaché.  
  
4.  Attachez-le au processus [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]. Pour plus d’informations, consultez [débogage des Applications Web déployées](../debugger/debugging-deployed-web-applications.md).  
  
5.  Dans Internet Explorer, cliquez sur le bouton sur votre formulaire.  
  
     Dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], vous devez atteindre le point d'arrêt dans Default.aspx.cs, Default.aspx.vb ou Default.aspx.  
  
6.  Lorsque vous avez terminé le débogage, dans le **déboguer** menu, cliquez sur **arrêter le débogage**.  
  
## <a name="see-also"></a>Voir aussi  
 [Débogage d’applications ASP.NET et AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)



