---
title: Créer un contrôle utilisateur prenant en charge la liaison de données simples
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom controls [Visual Studio], Data Sources Window
- Data Sources Window, controls
ms.assetid: b1488366-6dfb-454e-9751-f42fd3f3ddfb
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 4b6bf3a790d1e6d8d4165bb489176010a43e7c19
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49925074"
---
# <a name="create-a-windows-forms-user-control-that-supports-simple-data-binding"></a>Créer un contrôle utilisateur Windows Forms qui prend en charge la liaison de données simple

Lors de l’affichage des données dans des formulaires dans les applications Windows, vous pouvez choisir des contrôles existants à partir de la **boîte à outils**, ou vous pouvez créer des contrôles personnalisés si votre application nécessite une fonctionnalité qui n’est pas disponible dans les contrôles standard. Cette procédure pas à pas vous indique comment créer un contrôle qui implémente l'objet <xref:System.ComponentModel.DefaultBindingPropertyAttribute>. Les contrôles qui implémentent <xref:System.ComponentModel.DefaultBindingPropertyAttribute> peuvent contenir une propriété pouvant être liée aux données. Ce type de contrôles est similaire à <xref:System.Windows.Forms.TextBox> ou <xref:System.Windows.Forms.CheckBox>.

Pour plus d’informations sur la création de contrôles, consultez [développement de contrôles Windows Forms au moment du Design](/dotnet/framework/winforms/controls/developing-windows-forms-controls-at-design-time).

Lorsque vous créez des contrôles utilisables dans les scénarios de liaison de données, vous devez implémenter un des attributs de liaison de données suivants :

|Utilisation d’attributs de liaison de données|
| - |
|Implémentez <xref:System.ComponentModel.DefaultBindingPropertyAttribute> sur des contrôles simples, comme <xref:System.Windows.Forms.TextBox>, qui affichent une seule colonne (ou propriété) de données. (Ce processus est décrit dans cette page de procédure pas à pas.)|
|Implémentez <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> sur des contrôles, comme <xref:System.Windows.Forms.DataGridView>, qui affichent des listes (ou tables) de données. Pour plus d’informations, consultez [créer un contrôle utilisateur Windows Forms qui prend en charge la liaison de données complexe](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).|
|Implémentez l'objet <xref:System.ComponentModel.LookupBindingPropertiesAttribute> sur des contrôles, comme <xref:System.Windows.Forms.ComboBox>, qui affichent des listes (ou tables) de données, mais doivent également présenter une seule colonne ou propriété. Pour plus d’informations, consultez [créer un contrôle utilisateur Windows Forms qui prend en charge la liaison de données de recherche](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).|

Cette procédure pas à pas crée un contrôle simple qui affiche les données d'une seule colonne dans une table. Cet exemple utilise la colonne `Phone` de la table `Customers` de l'exemple de base de données Northwind. Le contrôle utilisateur simple affiche les numéros de téléphone des clients dans un format de numéro de téléphone standard, en utilisant un <xref:System.Windows.Forms.MaskedTextBox> et en définissant le masque sur un numéro de téléphone.

Pendant cette procédure pas à pas, vous allez apprendre à :

-   Créer un nouveau **Windows Forms Application**.

-   Ajouter un nouveau **contrôle utilisateur** à votre projet.

-   Concevoir visuellement le contrôle utilisateur.

-   Implémenter l'attribut `DefaultBindingProperty`.

-   Créer un jeu de données avec le **Configuration de Source de données** Assistant.

-   Définir le **téléphone** colonne dans le **des Sources de données** fenêtre à utiliser le nouveau contrôle.

-   Créer un formulaire pour afficher des données dans le nouveau contrôle.

## <a name="prerequisites"></a>Prérequis

Cette procédure pas à pas utilise SQL Server Express LocalDB et la base de données Northwind.

1.  Si vous n’avez pas SQL Server Express LocalDB, installez-le à partir de la [page de téléchargement de SQL Server Express](https://www.microsoft.com/sql-server/sql-server-editions-express), ou via le **le programme d’installation de Visual Studio**. Dans le **le programme d’installation de Visual Studio**, vous pouvez installer SQL Server Express LocalDB dans le cadre de la **stockage de données et de traitement** charge de travail, ou comme un composant individuel.

2.  Installer la base de données Northwind en suivant ces étapes :

    1. Dans Visual Studio, ouvrez le **Explorateur d’objets SQL Server** fenêtre. (Explorateur d’objets SQL Server est installé dans le cadre de la **stockage de données et de traitement** charge de travail dans le **le programme d’installation de Visual Studio**.) Développez le **SQL Server** nœud. Avec le bouton droit sur votre instance de base de données locale et sélectionnez **nouvelle requête**.

       Une fenêtre d’éditeur de requête s’ouvre.

    2. Copie le [script Transact-SQL de Northwind](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) dans votre Presse-papiers. Ce script T-SQL crée la base de données Northwind à partir de zéro et la remplit avec des données.

    3. Collez le script T-SQL dans l’éditeur de requête, puis choisissez le **Execute** bouton.

       Après une courte période, la requête est terminée en cours d’exécution et la base de données Northwind est créé.

## <a name="create-a-windows-forms-application"></a>Créer une Application de formulaires Windows

La première étape consiste à créer un **Windows Forms Application**:

1. Dans Visual Studio, sur le **fichier** menu, sélectionnez **New** > **projet**.

2. Développez le **Visual C#** ou **Visual Basic** dans le volet gauche, puis sélectionnez **Windows Desktop**.

3. Dans le volet central, sélectionnez le **Windows Forms application** type de projet.

4. Nommez le projet **SimpleControlWalkthrough**, puis choisissez **OK**.

     Le **SimpleControlWalkthrough** projet est créé et ajouté à **l’Explorateur de solutions**.

## <a name="add-a-user-control-to-the-project"></a>Ajouter un contrôle utilisateur au projet

Cette procédure pas à pas crée un contrôle simple pouvant être lié à des données à partir d’un **contrôle utilisateur**. Ajouter un **contrôle utilisateur** d’élément à la **SimpleControlWalkthrough** projet :

1.  À partir de la **projet** menu, choisissez **ajouter un contrôle utilisateur**.

2.  Type **PhoneNumberBox** dans la zone Nom, puis cliquez sur **ajouter**.

     Le **PhoneNumberBox** contrôle est ajouté à **l’Explorateur de solutions**et s’ouvre dans le concepteur.

## <a name="design-the-phonenumberbox-control"></a>Concevoir le contrôle PhoneNumberBox

Cette procédure pas à pas développe existant <xref:System.Windows.Forms.MaskedTextBox> pour créer le **PhoneNumberBox** contrôle :

1.  Faites glisser un <xref:System.Windows.Forms.MaskedTextBox> à partir de la **boîte à outils** aire de conception du contrôle utilisateur.

2.  Sélectionnez la balise active sur le <xref:System.Windows.Forms.MaskedTextBox> simplement faire glisser et choisissez **définir le masque**.

3.  Sélectionnez **numéro de téléphone** dans le **masque d’entrée** boîte de dialogue, puis cliquez sur **OK** pour définir le masque.

## <a name="add-the-required-data-binding-attribute"></a>Ajoutez l’attribut de liaison de données requis

Pour cette liaison de données prise en charge des contrôles simples, implémenter la <xref:System.ComponentModel.DefaultBindingPropertyAttribute>:

1.  Commutateur le **PhoneNumberBox** contrôle en mode code. (Sur le **vue** menu, choisissez **Code**.)

2.  Remplacez le code dans le **PhoneNumberBox** par le code suivant :

     [!code-csharp[VbRaddataDisplaying#3](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-simple-data-binding_1.cs)]
     [!code-vb[VbRaddataDisplaying#3](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-simple-data-binding_1.vb)]

3.  Dans le menu **Générer** , cliquez sur **Générer la solution**.

## <a name="create-a-data-source-from-your-database"></a>Créer une source de données à partir de votre base de données

Cette étape utilise le **Configuration de Source de données**Assistant pour créer une source de données selon le `Customers` table dans la base de données Northwind. Vous devez avoir accès à l'exemple de base de données Northwind pour créer la connexion. Pour plus d’informations sur la configuration de la base de données Northwind, consultez [Comment : installer les bases de données exemple](../data-tools/installing-database-systems-tools-and-samples.md).

1.  Dans le menu **Données** , cliquez sur **Afficher les sources de données**.

2.  Dans le **des Sources de données** fenêtre, sélectionnez **ajouter une nouvelle Source de données** pour démarrer le **Configuration de Source de données** Assistant.

3.  Sur le **choisir un Type de Source de données** page, sélectionnez **base de données**, puis cliquez sur **suivant**.

4.  Sur le **choisir votre connexion de données** page, effectuez l’une des opérations suivantes :

    -   Si une connexion de données à l’exemple de base de données Northwind est disponible dans la liste déroulante, sélectionnez-la.

    -   Sélectionnez **nouvelle connexion** pour lancer le **Ajouter/modifier la connexion** boîte de dialogue.

5.  Si votre base de données requiert un mot de passe, sélectionnez l’option pour inclure les données sensibles, puis cliquez sur **suivant**.

6.  Sur le **enregistrer la chaîne de connexion dans le fichier de Configuration de l’Application** , cliquez sur **suivant**.

7.  Sur le **choisir vos objets de base de données** page, développez le **Tables** nœud.

8.  Sélectionnez le `Customers` table, puis cliquez sur **Terminer**.

     Le **NorthwindDataSet** est ajouté à votre projet et le `Customers` table s’affiche dans le **des Sources de données** fenêtre.

## <a name="set-the-phone-column-to-use-the-phonenumberbox-control"></a>Définir la colonne phone pour utiliser le contrôle PhoneNumberBox

Dans le **des Sources de données** fenêtre, vous pouvez définir le contrôle à créer avant de faire glisser des éléments sur votre formulaire :

1.  Ouvrez **Form1** dans le concepteur.

2.  Développez le **clients** nœud dans le **des Sources de données** fenêtre.

3.  Cliquez sur la flèche déroulante du **clients** nœud, puis choisissez **détails** à partir de la liste de contrôle.

4.  Cliquez sur la flèche déroulante du **téléphone** colonne, puis choisissez **personnaliser**.

5.  Sélectionnez le **PhoneNumberBox** dans la liste des **contrôles associés** dans le **Options de personnalisation de l’interface utilisateur de données** boîte de dialogue.

6.  Cliquez sur la flèche déroulante du **téléphone** colonne, puis choisissez **PhoneNumberBox**.

## <a name="add-controls-to-the-form"></a>Ajouter des contrôles au formulaire

Vous pouvez créer les contrôles liés aux données en faisant glisser des éléments à partir de la **des Sources de données** fenêtre vers le formulaire.

Pour créer des contrôles liés aux données sur le formulaire, faites glisser le **clients** nœud à partir de la **des Sources de données** fenêtre vers le formulaire et vérifiez que le **PhoneNumberBox** contrôle est utilisé pour afficher les données dans le **téléphone** colonne.

     Data-bound controls with descriptive labels appear on the form, along with a tool strip (<xref:System.Windows.Forms.BindingNavigator>) for navigating records. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), CustomersTableAdapter, <xref:System.Windows.Forms.BindingSource>, and <xref:System.Windows.Forms.BindingNavigator> appear in the component tray.

## <a name="run-the-application"></a>Exécuter l'application

Appuyez sur **F5** pour exécuter l’application.

## <a name="next-steps"></a>Étapes suivantes

Selon les exigences de votre application, vous pouvez exécuter différentes étapes après la création d’un contrôle prenant en charge la liaison de données. Les étapes ultérieures sont habituellement celles-ci :

-   Positionnement de vos contrôles personnalisés dans une bibliothèque de contrôles pour pouvoir les réutiliser dans d'autres applications.

-   Création de contrôles prenant en charge des scénarios de liaison de données plus complexes. Pour plus d’informations, consultez [créer un contrôle utilisateur Windows Forms qui prend en charge la liaison de données complexe](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md) et [créer un contrôle utilisateur Windows Forms qui prend en charge la liaison de données de recherche](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).

## <a name="see-also"></a>Voir aussi

- [Lier des contrôles Windows Forms à des données dans Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Définir le contrôle à créer lors d’une opération de glisser-déplacer à partir de la fenêtre Sources de données](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)