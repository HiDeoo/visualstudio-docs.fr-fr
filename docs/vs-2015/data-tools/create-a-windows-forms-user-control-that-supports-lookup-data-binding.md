---
title: Créer un contrôle utilisateur Windows Forms qui prend en charge la liaison de données de recherche | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data binding, user controls
- LookupBindingPropertiesAttribute class, examples
- user controls [Visual Basic], creating
ms.assetid: c48b4d75-ccfc-4950-8b14-ff8adbfe4208
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 48891f82667270f04af49c60122c63f8d3a943f7
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72668775"
---
# <a name="create-a-windows-forms-user-control-that-supports-lookup-data-binding"></a>Créer un contrôle utilisateur Windows Forms prenant en charge la liaison de données de recherche
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour afficher des données dans Windows Forms, vous pouvez choisir des contrôles existants dans la **Boîte à outils** ou créer des contrôles personnalisés si votre application requiert des fonctionnalités qui ne sont pas disponibles dans les contrôles standard. Cette procédure pas à pas vous indique comment créer un contrôle qui implémente l'objet <xref:System.ComponentModel.LookupBindingPropertiesAttribute>. Les contrôles qui implémentent <xref:System.ComponentModel.LookupBindingPropertiesAttribute> peuvent contenir trois propriétés pouvant être liées aux données. Ce type de contrôles est similaire à <xref:System.Windows.Forms.ComboBox>.

 Pour plus d’informations sur la création de contrôles, consultez [développement de contrôles Windows Forms au moment du design](https://msdn.microsoft.com/library/e5a8e088-7ec8-4fd9-bcb3-9078fd134829).

 Quand vous créez des contrôles utilisables dans des scénarios de liaison de données, vous devez implémenter l’un des attributs de liaison de données suivants :

|Utilisation des attributs de liaison de données|
|-----------------------------------|
|Implémentez <xref:System.ComponentModel.DefaultBindingPropertyAttribute> sur des contrôles simples, comme <xref:System.Windows.Forms.TextBox>, qui affichent une seule colonne (ou propriété) de données. Pour plus d’informations, consultez [créer un Windows Forms contrôle utilisateur qui prend en charge la liaison de données simple](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).|
|Implémentez <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> sur des contrôles, comme <xref:System.Windows.Forms.DataGridView>, qui affichent des listes (ou tables) de données. Pour plus d’informations, consultez [créer un Windows Forms contrôle utilisateur qui prend en charge la liaison de données complexe](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).|
|Implémentez <xref:System.ComponentModel.LookupBindingPropertiesAttribute> sur des contrôles, comme <xref:System.Windows.Forms.ComboBox>, qui affichent des listes (ou tables) de données, mais doivent également présenter une seule colonne ou propriété. (Ce processus est décrit dans cette page de procédure pas à pas.)|

 Cette procédure pas à pas crée un contrôle de recherche qui effectue une liaison vers les données de deux tables. Cet exemple utilise les tables `Customers` et `Orders` de l'exemple de base de données Northwind. Le contrôle de recherche sera lié au champ `CustomerID` de la table `Orders`. Il utilisera cette valeur pour rechercher le `CompanyName` dans la table `Customers`.

 Pendant cette procédure pas à pas, vous allez apprendre à :

- Créez une nouvelle **application Windows**.

- Ajouter un nouveau **Contrôle utilisateur** à votre projet.

- Concevoir visuellement le contrôle utilisateur.

- Implémenter l'attribut `LookupBindingProperty`.

- Créez un DataSet à l’aide de l’Assistant **configuration de source de données** .

- Définir la colonne **CustomerID** de la table **Orders** dans la fenêtre **Sources de données** pour qu’elle utilise le nouveau contrôle.

- Créer un formulaire pour afficher des données dans le nouveau contrôle.

## <a name="prerequisites"></a>Prérequis
 Pour réaliser cette procédure pas à pas, vous aurez besoin des éléments suivants :

- avoir accès à l'exemple de base de données Northwind.

## <a name="create-a-windows-application"></a>Créer une application Windows
 La première étape consiste à créer une **application Windows**.

#### <a name="to-create-the-new-windows-project"></a>Pour créer un projet Windows

1. Dans Visual Studio, dans le menu **fichier** , créez un nouveau **projet**.

2. Nommez le projet **LookupControlWalkthrough**.

3. Sélectionnez **Windows Forms application**, puis cliquez sur **OK**.

     Le projet **LookupControlWalkthrough** est créé et ajouté à l’**Explorateur de solutions**.

## <a name="add-a-user-control-to-the-project"></a>Ajouter un contrôle utilisateur au projet
 Cette procédure pas à pas crée un contrôle de recherche à partir d’un **Contrôle utilisateur** : ajoutez donc un élément **Contrôle utilisateur** au projet **LookupControlWalkthrough**.

#### <a name="to-add-a-user-control-to-the-project"></a>Pour ajouter un contrôle utilisateur au projet

1. Dans le menu **Projet**, sélectionnez **Ajouter un contrôle utilisateur**.

2. Tapez `LookupBox` dans la zone **nom** , puis cliquez sur **Ajouter**.

     Le contrôle **LookupBox** est ajouté à l’**Explorateur de solutions** et s’ouvre dans le concepteur.

## <a name="design-the-lookupbox-control"></a>Concevoir le contrôle LookupBox

#### <a name="to-design-the-lookupbox-control"></a>Pour concevoir le contrôle LookupBox

- Faites glisser un <xref:System.Windows.Forms.ComboBox> depuis la **Boîte à outils** vers l’aire de conception du contrôle utilisateur.

## <a name="add-the-required-data-binding-attribute"></a>Ajouter l’attribut de liaison de données requis
 Pour des contrôles de recherche prenant en charge la liaison de données, vous pouvez implémenter l’attribut<xref:System.ComponentModel.LookupBindingPropertiesAttribute>.

#### <a name="to-implement-the-lookupbindingproperties-attribute"></a>Pour implémenter l'attribut LookupBindingProperties

1. Faites passer le contrôle **LookupBox** en mode Code. (Dans le menu **Affichage**, choisissez **Code**.)

2. Remplacez le code de `LookupBox` par le code suivant :

     [!code-csharp[VbRaddataDisplaying#5](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/LookupBox.cs#5)]
     [!code-vb[VbRaddataDisplaying#5](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/LookupBox.vb#5)]

3. Dans le menu **générer** , choisissez **générer la solution**.

## <a name="create-a-data-source-from-your-database"></a>Créer une source de données à partir de votre base de données
 Cette étape crée une source de données à l’aide de l’Assistant **Configuration de source de données** basée sur les tables `Customers` et `Orders` de l’exemple de base de données Northwind. Vous devez avoir accès à l'exemple de base de données Northwind pour créer la connexion. Pour plus d’informations sur la configuration de l’exemple de base de données Northwind, consultez [installer des exemples de bases de données SQL Server](../data-tools/install-sql-server-sample-databases.md).

#### <a name="to-create-the-data-source"></a>Pour créer la source de données

1. Dans le menu **Données** , cliquez sur **Afficher les sources de données**.

2. Dans la fenêtre **sources de données** , sélectionnez Ajouter une **nouvelle source de données** pour démarrer l’Assistant Configuration de source de **données** .

3. Sélectionnez **Base de données** dans la page **Choisir un type de source de données** , puis cliquez sur **Suivant**.

4. Dans la page **Choisir votre connexion de données**, effectuez l’une des opérations suivantes :

    - Si une connexion de données à l’exemple de base de données Northwind est disponible dans la liste déroulante, sélectionnez-la.

    - Sélectionnez **Nouvelle connexion** pour afficher la boîte de dialogue **Ajouter/Modifier la connexion**.

5. Si votre base de données nécessite un mot de passe, sélectionnez l’option pour inclure les données sensibles, puis cliquez sur **Suivant**.

6. Dans la page **enregistrer la chaîne de connexion dans le fichier de configuration de l’application** , cliquez sur **suivant**.

7. Dans la page **Choisir vos objets de base de données**, développez le nœud **Tables**.

8. Sélectionnez les tables `Customers` et `Orders`, puis cliquez sur **Terminer**.

     **NorthwindDataSet** est ajouté à votre projet et les `Customers` `Orders` tables et s’affichent dans la fenêtre sources de **données** .

## <a name="set-the-customerid-column-of-the-orders-table-to-use-the-lookupbox-control"></a>Définir la colonne CustomerID de la table Orders pour qu’elle utilise le contrôle LookupBox
 Dans la fenêtre **Sources de données**, vous pouvez définir le contrôle à créer avant de faire glisser des éléments vers votre formulaire.

#### <a name="to-set-the-customerid-column-to-bind-to-the-lookupbox-control"></a>Pour définir la colonne CustomerID pour qu'elle soit liée au contrôle LookupBox

1. Ouvrez **Form1** dans le concepteur.

2. Développez le nœud **Customers** dans la fenêtre **Sources de données**.

3. Développez le nœud **Orders** (inclus dans le nœud **Customers** sous la colonne **Fax**).

4. Cliquez sur la flèche déroulante du nœud **Orders** et choisissez **Détails** dans la liste de contrôles.

5. Cliquez sur la flèche déroulante de la colonne **CustomerID** (dans le nœud **Orders**), puis choisissez **Personnaliser**.

6. Sélectionnez **LookupBox** dans la liste des **Contrôles associés** de la boîte de dialogue **Options de personnalisation de l’interface utilisateur des données**.

7. Cliquez sur **OK**.

8. Cliquez sur la flèche de déroulement de la colonne **CustomerID** et choisissez **LookupBox**.

## <a name="addcontrols-to-the-form"></a>Addcontrols au formulaire
 Pour créer des contrôles liés aux données, vous pouvez faire glisser des éléments depuis la fenêtre **Sources de données** vers **Form1**.

#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Pour créer des contrôles liés aux données dans le formulaire Windows

- Faites glisser le nœud **Orders** de la fenêtre **sources de données** vers le Windows Form, puis vérifiez que le contrôle **LookupBox** est utilisé pour afficher les données dans la `CustomerID` colonne.

## <a name="bind-the-control-to-look-up-companyname-from-the-customers-table"></a>Lier le contrôle pour rechercher CompanyName dans la table Customers

#### <a name="to-setup-the-lookup-bindings"></a>Pour configurer les liaisons de recherche

- Sélectionnez le nœud **Customers** principal dans la fenêtre **sources de données** et faites-le glisser sur la zone de liste déroulante dans **CustomerIDLookupBox** sur **Form1**.

     Ceci configure la liaison des données pour afficher le `CompanyName` de la table `Customers` tout en conservant la valeur de `CustomerID` de la table `Orders`.

## <a name="running-the-application"></a>Exécution de l'application

#### <a name="to-run-the-application"></a>Pour exécuter l’application

- Appuyez sur F5 pour exécuter l'application.

- Parcourez quelques enregistrements et vérifiez que le `CompanyName` apparaît dans le contrôle `LookupBox`.

## <a name="see-also"></a>Voir aussi
 [Lier des contrôles Windows Forms à des données dans Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
