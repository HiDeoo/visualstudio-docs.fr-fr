---
title: Création d’un langage spécifique à un domaine basé sur Windows Forms | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 452318ff-8ecf-46d0-8ca0-4013d0cdafaf
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: cea3b76575e1da2e846e230580c6cfa50ef9b207
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72651265"
---
# <a name="creating-a-windows-forms-based-domain-specific-language"></a>Création d'un langage spécifique à un domaine basé sur Windows Forms
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez utiliser Windows Forms pour afficher l’état d’un modèle de langage spécifique à un domaine (DSL), au lieu d’utiliser un diagramme DSL. Cette rubrique vous guide tout au long de la liaison d’un Windows Form à un langage DSL, à l’aide du [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Kit de développement logiciel de visualisation et de modélisation.

 ![DSL&#45;Wpf&#45;2](../modeling/media/dsl-wpf-2.png "DSL-Wpf-2") Instance DSL, présentant une interface utilisateur Windows Form et l’Explorateur de modèles.

## <a name="creating-a-windows-forms-dsl"></a>Création d’un Windows Forms DSL
 Le modèle DSL du **Concepteur WinForm minimal** crée un DSL minimal que vous pouvez modifier en fonction de vos propres exigences.

#### <a name="to-create-a-minimal-winforms-dsl"></a>Pour créer un DSL WinForms minimal

1. Créez un DSL à partir du modèle de **Concepteur WinForm minimal** .

    Dans cette procédure pas à pas, les noms suivants sont utilisés :

   |                       |                 |
   |-----------------------|-----------------|
   | Nom de la solution et du DSL |     FarmApp     |
   |       Espace de noms       | Société. FarmApp |

2. Expérimentez l’exemple initial fourni par le modèle :

   1. Transformez tous les modèles.

   2. Générez et exécutez l’exemple (**CTRL + F5**).

   3. Dans l’instance expérimentale de Visual Studio, ouvrez le `Sample` fichier dans le projet de débogage.

        Notez qu’il est affiché dans un contrôle de Windows Forms.

        Vous pouvez également voir les éléments du modèle affichés dans l’Explorateur.

        Ajoutez des éléments dans le formulaire ou l’Explorateur, et Notez qu’ils apparaissent dans l’autre affichage.

   Dans l’instance principale de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , notez les points suivants sur la solution DSL :

- `DslDefinition.dsl` ne contient aucun élément de diagramme. Cela est dû au fait que vous n’utiliserez pas de diagrammes DSL pour afficher les modèles d’instance de ce DSL. Au lieu de cela, vous allez lier un Windows Form au modèle, et les éléments du formulaire afficheront le modèle.

- En plus des `Dsl` projets et `DslPackage` , la solution contient un troisième projet nommé `UI.` projet d' **interface utilisateur** qui contient la définition d’un contrôle de Windows Forms. `DslPackage` dépend de `UI` , et `UI` dépend de `Dsl` .

- Dans le `DslPackage` projet, `UI\DocView.cs` contient le code qui affiche le contrôle Windows Forms défini dans le `UI` projet.

- Le `UI` projet contient un exemple fonctionnel d’un contrôle de formulaire lié au DSL. Toutefois, il ne fonctionnera pas lorsque vous aurez modifié la définition DSL. Le `UI` projet contient :

  - Une classe Windows Forms nommée `ModelViewControl` .

  - Fichier nommé `DataBinding.cs` qui contient une définition partielle supplémentaire de `ModelViewControl` . Pour afficher son contenu, dans **Explorateur de solutions**, ouvrez le menu contextuel du fichier, puis choisissez **afficher le code**.

### <a name="about-the-ui-project"></a>À propos du projet d’interface utilisateur
 Lorsque vous mettez à jour le fichier de définition DSL pour définir votre propre DSL, vous devez mettre à jour le contrôle dans le `UI` projet pour afficher votre DSL. Contrairement aux `Dsl` `DslPackage` projets et, l’exemple `UI` de projet n’est pas généré à partir de `DslDefinitionl.dsl` . Vous pouvez ajouter des fichiers. TT pour générer le code si vous le souhaitez, bien que cela ne soit pas abordé dans cette procédure pas à pas.

## <a name="updating-the-dsl-definition"></a>Mise à jour de la définition DSL
 La définition DSL suivante est utilisée dans cette procédure pas à pas.

 ![DSL&#45;WPF&#45;1](../modeling/media/dsl-wpf-1.png "DSL-Wpf-1")

#### <a name="to-update-the-dsl-definition"></a>Pour mettre à jour la définition DSL

1. Ouvrez DslDefinition. DSL dans le concepteur DSL.

2. Supprimer **ExampleElement**

3. Renommez la classe de domaine **ExampleModel** en `Farm` .

     Donnez-lui des propriétés de domaine supplémentaires nommées `Size` de type **Int32**et `IsOrganic` de type **Boolean**.

    > [!NOTE]
    > Si vous supprimez la classe de domaine racine, puis créez une nouvelle racine, vous devez réinitialiser la propriété de la classe racine de l’éditeur. Dans l' **Explorateur DSL**, sélectionnez **éditeur**. Ensuite, dans la Fenêtre Propriétés, définissez la **classe racine** sur `Farm` .

4. Utilisez l’outil **classe de domaine nommée** pour créer les classes de domaine suivantes :

    - `Field` : Attribuez à cette propriété de domaine supplémentaire nommée `Size` .

    - `Animal` – Dans le Fenêtre Propriétés, définissez le **modificateur d’héritage** sur **abstract**.

5. Utilisez l’outil **classe de domaine** pour créer les classes suivantes :

    - `Sheep`

    - `Goat`

6. Utilisez l’outil d' **héritage** pour faire `Goat` et `Sheep` hériter de `Animal` .

7. Utilisez l’outil d' **incorporation** pour incorporer `Field` et `Animal` sous `Farm` .

8. Vous souhaiterez peut-être nettoyer le diagramme. Pour réduire le nombre d’éléments en double, utilisez la commande **Placer la sous-arborescence ici** dans le menu contextuel des éléments feuille.

9. **Transformez tous les modèles** dans la barre d’outils de Explorateur de solutions.

10. Générez le projet **DSL** .

    > [!NOTE]
    > À ce niveau, les autres projets ne seront pas générés sans erreur. Toutefois, nous voulons générer le projet DSL afin que son assembly soit accessible à l’Assistant source de données.

## <a name="updating-the-ui-project"></a>Mise à jour du projet d’interface utilisateur
 À présent, vous pouvez créer un nouveau contrôle utilisateur qui affichera les informations stockées dans le modèle DSL. Le moyen le plus simple de connecter le contrôle utilisateur au modèle est d’utiliser des liaisons de données. Le type d’adaptateur de liaison de données nommé **ModelingBindingSource** est conçu spécifiquement pour connecter des DSL à des interfaces non-VMSDK.

#### <a name="to-define-your-dsl-model-as-a-data-source"></a>Pour définir votre modèle DSL comme source de données

1. Dans le menu **données** , choisissez **afficher les sources de données**.

     La fenêtre **Sources de données** s’ouvre.

     Choisissez **Ajouter une nouvelle source de données**. L' **Assistant Configuration de source de données** s’ouvre.

2. Choisissez **objet**, **suivant**.

     Développez **DSL**, **Company. FarmApp**, puis sélectionnez **batterie**, qui est la classe racine de votre modèle. Cliquez sur **Terminer**.

     Dans Explorateur de solutions, le projet d' **interface utilisateur** contient désormais **Properties\DataSources\Farm.DataSource**

     Les propriétés et les relations de votre classe de modèle s’affichent dans la fenêtre sources de données.

     ![DslWpf&#45;3](../modeling/media/dslwpf-3.png "DslWpf-3")

#### <a name="to-connect-your-model-to-a-form"></a>Pour connecter votre modèle à un formulaire

1. Dans le projet d' **interface utilisateur** , supprimez tous les fichiers. cs existants.

2. Ajoutez un nouveau fichier de **contrôle utilisateur** nommé `FarmControl` au projet d' **interface** utilisateur.

3. Dans la fenêtre **sources de données** , dans le menu déroulant de la batterie de **serveurs**, choisissez **Détails**.

    Laissez les paramètres par défaut pour les autres propriétés.

4. Ouvrez FarmControl.cs en mode conception.

    Faites glisser **Farm** depuis la fenêtre sources de données vers FarmControl.

    Un ensemble de contrôles s’affiche, un pour chaque propriété. Les propriétés de relation ne génèrent pas de contrôles.

5. Supprimez **farmBindingNavigator**. Cela est également généré automatiquement dans le `FarmControl` Concepteur, mais il n’est pas utile pour cette application.

6. À l’aide de la boîte à outils, créez deux instances de **DataGridView**et nommez-les `AnimalGridView` et `FieldGridView` .

   > [!NOTE]
   > Une autre étape consiste à faire glisser les éléments animaux et champs de la fenêtre sources de données vers le contrôle. Cette action crée automatiquement des grilles de données et des liaisons entre l’affichage de grille et la source de données. Toutefois, cette liaison ne fonctionne pas correctement pour DSL. Par conséquent, il est préférable de créer manuellement les grilles et les liaisons de données.

7. Si la boîte à outils ne contient pas l’outil **ModelingBindingSource** , ajoutez-la. Dans le menu contextuel de l’onglet **données** , choisissez **choisir les éléments**. Dans la boîte de dialogue **choisir des éléments de boîte à outils** , sélectionnez **ModelingBindingSource** sous l' **onglet .NET Framework**.

8. À l’aide de la boîte à outils, créez deux instances de **ModelingBindingSource**et nommez-les `AnimalBinding` et `FieldBinding` .

9. Définissez la propriété **DataSource** de chaque **ModelingBindingSource** sur **farmBindingSource**.

     Définissez la propriété **DataMember** sur **animaux** ou **champs**.

10. Affectez à la propriété **DataSource** de la valeur `AnimalGridView` `AnimalBinding` et de  `FieldGridView` à `FieldBinding` .

11. Ajustez la disposition du contrôle de la batterie de serveurs à votre goût.

    Le **ModelingBindingSource** est un adaptateur qui exécute plusieurs fonctions spécifiques à DSL :

- Elle encapsule les mises à jour dans une transaction de magasin VMSDK.

   Par exemple, lorsque l’utilisateur supprime une ligne de la grille de la vue de données, une liaison normale génère une exception de transaction.

- Cela garantit que, lorsque l’utilisateur sélectionne une ligne, le Fenêtre Propriétés affiche les propriétés de l’élément de modèle correspondant, au lieu de la ligne de la grille de données.

  ![DslWpf4](../modeling/media/dslwpf4.png "DslWpf4") Schéma de liens entre les sources de données et les vues.

#### <a name="to-complete-the-bindings-to-the-dsl"></a>Pour effectuer les liaisons au DSL

1. Ajoutez le code suivant dans un fichier de code séparé dans le projet d' **interface utilisateur** :

    ```csharp
    using System.ComponentModel;
    using Microsoft.VisualStudio.Modeling;
    using Microsoft.VisualStudio.Modeling.Design;

    namespace Company.FarmApp
    {
      partial class FarmControl
      {
        public IContainer Components { get { return components; } }

        /// <summary>Binds the WinForms data source to the DSL model.
        /// </summary>
        /// <param name="nodelRoot">The root element of the model.</param>
        public void DataBind(ModelElement modelRoot)
        {
          WinFormsDataBindingHelper.PreInitializeDataSources(this);
          this.farmBindingSource.DataSource = modelRoot;
          WinFormsDataBindingHelper.InitializeDataSources(this);
        }
      }
    }
    ```

2. Dans le projet **DslPackage** , modifiez **DslPackage\DocView.TT** pour mettre à jour la définition de variable suivante :

    ```csharp
    string viewControlTypeName = "FarmControl";
    ```

## <a name="testing-the-dsl"></a>Test du DSL
 La solution DSL peut désormais être générée et exécutée, bien que vous puissiez souhaiter ajouter d’autres améliorations ultérieurement.

#### <a name="to-test-the-dsl"></a>Pour tester le DSL

1. Créez et exécutez la solution.

2. Dans l’instance expérimentale de Visual Studio, ouvrez l' **exemple** de fichier.

3. Dans l **'Explorateur FarmApp**, ouvrez le menu contextuel du nœud racine de la **batterie de serveurs** , puis choisissez **Ajouter un nouveau caprin**.

     `Goat1` apparaît dans la vue **animaux** .

    > [!WARNING]
    > Vous devez utiliser le menu contextuel sur le nœud de la **batterie de serveurs** , et non sur le nœud **animaux** .

4. Sélectionnez le nœud racine de la **batterie de serveurs** et affichez ses propriétés.

     Dans le mode formulaire, modifiez le **nom** ou la **taille** de la batterie de serveurs.

     Lorsque vous quittez chaque champ du formulaire, la propriété correspondante change dans le Fenêtre Propriétés.

## <a name="enhancing-the-dsl"></a>Amélioration de la DSL

#### <a name="to-make-the-properties-update-immediately"></a>Pour que les propriétés soient mises à jour immédiatement

1. En mode création de FarmControl.cs, sélectionnez un champ simple, tel que nom, taille ou IsOrganic.

2. Dans le Fenêtre Propriétés, développez **DataBindings** et ouvrez **(avancé)**.

     Dans la boîte de dialogue **mise en forme et liaison avancée** , sous **mode de mise à jour**de la source de données, choisissez **OnPropertyChanged**.

3. Créez et exécutez la solution.

     Vérifiez que lorsque vous modifiez le contenu du champ, la propriété correspondante du modèle de batterie change immédiatement.

#### <a name="to-provide-add-buttons"></a>Pour fournir des boutons ajouter

1. En mode création de FarmControl.cs, utilisez la boîte à outils pour créer un bouton sur le formulaire.

    Modifiez le nom et le texte du bouton, par exemple `New Sheep` .

2. Ouvrez le code derrière le bouton (par exemple en double-cliquant dessus).

    Modifiez-la comme suit :

   ```csharp
   private void NewSheepButton_Click(object sender, EventArgs e)
   {
     using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))
     {
       elementOperations.MergeElementGroup(farm,
         new ElementGroup(new Sheep(farm.Partition)));
       t.Commit();
     }
   }

   // The following code is shared with other add buttons:
   private ElementOperations operationsCache = null;
   private ElementOperations elementOperations
   {
     get
     {
       if (operationsCache == null)
       {
         operationsCache = new ElementOperations(farm.Store, farm.Partition);
       }
       return operationsCache;
     }
   }
   private Farm farm
   {
     get { return this.farmBindingSource.DataSource as Farm; }
   }

   ```

    Vous devrez également insérer la directive suivante :

   ```csharp

   using Microsoft.VisualStudio.Modeling;

   ```

3. Ajoutez des boutons similaires pour les caprins et les champs.

4. Créez et exécutez la solution.

5. Vérifiez que le nouveau bouton ajoute un élément. Le nouvel élément doit s’afficher à la fois dans l’Explorateur FarmApp et dans la vue de grille de données appropriée.

    Vous devez être en mesure de modifier le nom de l’élément dans la vue de grille de données. Vous pouvez également le supprimer.

   ![DSL&#45;WPF&#45;2](../modeling/media/dsl-wpf-2.png "DSL-Wpf-2")

### <a name="about-the-code-to-add-an-element"></a>À propos du code pour ajouter un élément
 Pour les nouveaux boutons d’élément, le code de remplacement suivant est légèrement plus simple.

```csharp
private void NewSheepButton_Click(object sender, EventArgs e)
{
  using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))
  {
    farm.Animals.Add(new Sheep(farm.Partition)); ;
    t.Commit();
  }
}

```

 Toutefois, ce code ne définit pas de nom par défaut pour le nouvel élément. Elle n’exécute pas de fusion personnalisée que vous avez peut-être définie dans les **directives de fusion d’éléments** du DSL, et n’exécute aucun code de fusion personnalisé qui aurait pu être défini.

 Par conséquent, nous vous recommandons <xref:Microsoft.VisualStudio.Modeling.ElementOperations> d’utiliser pour créer des éléments. Pour plus d’informations, consultez Personnalisation de la [création et du déplacement d’éléments](../modeling/customizing-element-creation-and-movement.md).

## <a name="see-also"></a>Voir aussi
 [Comment définir un langage spécifique à un domaine pour l'](../modeling/how-to-define-a-domain-specific-language.md) [écriture de code pour personnaliser un](../modeling/writing-code-to-customise-a-domain-specific-language.md) [Kit de développement logiciel (SDK) de modélisation de langage spécifique à un domaine pour Visual Studio-langages spécifiques](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md) à un domaine
