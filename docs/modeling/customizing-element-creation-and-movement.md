---
title: Personnalisation de la création et du mouvement des éléments
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.elementmergedirective
helpviewer_keywords:
- Domain-Specific Language, element merge directives
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 00026cd53a67a216e126bcc5de92a136a6359331
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60043522"
---
# <a name="customizing-element-creation-and-movement"></a>Personnalisation de la création et du mouvement des éléments

Vous pouvez autoriser un élément à faire glisser vers un autre, à partir de la boîte à outils ou dans un collage ou de l’opération de déplacement. Vous pouvez avoir les éléments déplacés liés aux éléments cibles, à l’aide de relations que vous spécifiez.

Une directive de fusion d’élément (EMD) Spécifie que se passe-t-il quand un élément de modèle est *fusionné* dans un autre élément de modèle. Cela se produit lorsque :

- L’utilisateur fait glisser à partir de la boîte à outils vers le diagramme ou une forme.

- L’utilisateur crée un élément à l’aide d’un menu Ajouter dans l’Explorateur ou d’une forme de compartiment.

- L’utilisateur déplace un élément d’un couloir à un autre.

- L’utilisateur colle un élément.

- Votre code de programme appelle la directive de fusion d’élément.

Bien que les opérations de création peuvent sembler être différentes des opérations de copie, elles fonctionnent réellement de la même façon. Lorsqu’un élément est ajouté, par exemple à partir de la boîte à outils, un prototype de celui-ci est répliqué. Le prototype est fusionné dans le modèle dans la même manière que les éléments qui ont été copiés à partir d’une autre partie du modèle.

La responsabilité d’une directive EMD consiste à déterminer la façon dont un objet ou un groupe d’objets doit être fusionné dans un emplacement particulier dans le modèle. En particulier, il détermine quelles sont les relations doivent être instanciées pour lier le groupe fusionné dans le modèle. Vous pouvez également personnaliser pour définir les propriétés et à créer des objets supplémentaires.

![DSL&#45;EMD&#95;Merge](../modeling/media/dsl-emd_merge.png)

Une directive EMD est générée automatiquement lorsque vous définissez une relation d’incorporation. Cette valeur par défaut EMD crée une instance de la relation lorsque les utilisateurs ajoutent de nouvelles instances enfant au parent. Vous pouvez modifier ces EMDs par défaut, par exemple en ajoutant du code personnalisé.

Vous pouvez également ajouter vos propres EMDs dans la définition DSL, pour permettre aux utilisateurs de faire glisser ou coller des différentes combinaisons des classes fusionnés et de réception.

## <a name="defining-an-element-merge-directive"></a>Définition d’une Directive de fusion d’élément

Vous pouvez ajouter des directives de fusion d’élément pour les classes de domaine, des relations de domaine, des formes, des connecteurs et des diagrammes. Vous pouvez ajouter ou les trouver dans l’Explorateur DSL sous la classe de domaine de réception. La classe de récepteur est la classe de domaine de l’élément qui est déjà dans le modèle, et sur lequel l’élément nouveau ou copié est fusionnée.

![DSL&#45;EMD&#95;Details](../modeling/media/dsl-emd_details.png)

Le **l’indexation de la classe** est la classe de domaine d’éléments qui peuvent être fusionnées dans les membres de la classe réceptrice. Instances de sous-classes de la classe de l’indexation sont également fusionnés par cette EMD, sauf si vous définissez **s’applique aux sous-classes** sur False.

Il existe deux types de directive de fusion :

- Un **processus de fusion** directive spécifie les relations par lequel le nouvel élément doit être lié dans l’arborescence.

- Un **avant fusion** directive redirige le nouvel élément à un autre élément de réception, généralement un parent.

Vous pouvez ajouter du code personnalisé aux directives de fusion :

- Définissez **acceptation personnalisée d’utilise** pour ajouter votre propre code pour déterminer si une instance particulière de l’élément d’indexation doit être fusionnée dans l’élément cible. Lorsque l’utilisateur fait glisser à partir de la boîte à outils, le pointeur « non valide » montre si votre code n’autorise pas la fusion.

   Par exemple, vous pouvez autoriser la fusion uniquement lorsque l’élément cible est dans un état particulier.

- Définissez **fusion personnalisée utilise** pour ajouter indicatif propre pour définir les modifications apportées au modèle lors de la fusion est effectuée.

   Par exemple, vous pouvez définir des propriétés dans l’élément fusionné à partir de son nouvel emplacement dans le modèle à l’aide des données.

> [!NOTE]
> Si vous écrivez du code de fusion personnalisée, elle affecte uniquement les fusions qui sont effectuées en utilisant cette EMD. S’il existe des autres EMDs qui fusionnent le même type d’objet, ou en l’absence d’autre code personnalisé qui crée ces objets sans utiliser le EMD, puis elles ne seront pas affectées par votre code personnalisé de fusion.
>
> Si vous souhaitez vous assurer qu’un nouvel élément ou une nouvelle relation est toujours traitée par votre code personnalisé, vous pouvez définir un `AddRule` sur la relation d’incorporation et un `DeleteRule` sur la classe de domaine de l’élément. Pour plus d’informations, consultez [propager les modifications dans le modèle de règles](../modeling/rules-propagate-changes-within-the-model.md).

## <a name="example-defining-an-emd-without-custom-code"></a>Exemple : Définition d’une directive EMD sans code personnalisé

L’exemple suivant permet aux utilisateurs de créer un élément et un connecteur en même temps en faisant glisser à partir de la boîte à outils vers une forme existante. L’exemple ajoute une directive EMD à la définition DSL. Avant cette modification, les utilisateurs peuvent faire glisser outils sur le diagramme, mais pas sur des formes existantes.

Les utilisateurs peuvent également coller des éléments sur d’autres éléments.

### <a name="to-let-users-create-an-element-and-a-connector-at-the-same-time"></a>Pour permettre aux utilisateurs de créer un élément et un connecteur en même temps

1. Créer un nouveau langage DSL à l’aide de la **langage Minimal** modèle de solution.

    Lorsque vous exécutez ce DSL, il vous permet de créer des formes et des liens entre les formes. Vous ne pouvez pas faire glisser un nouveau **ExampleElement** forme à partir de la boîte à outils vers une forme existante.

2. Pour permettre aux utilisateurs de fusionner les éléments sur `ExampleElement` formes, créer un nouveau EMD dans le `ExampleElement` de classe de domaine :

   1. Dans **Explorateur DSL**, développez **Classes de domaine**. Avec le bouton droit `ExampleElement` puis cliquez sur **ajouter nouvelle Directive de fusion**.

   2. Assurez-vous que le **détails DSL** fenêtre est ouverte, afin que vous puissiez voir les détails de la nouvelle EMD. (Menu : **Afficher**, **autres Windows**, **détails DSL**.)

3. Définir le **classe d’indexation** dans la fenêtre Détails DSL, pour définir quelle classe d’éléments peut être fusionné sur `ExampleElement` objets.

    Pour cet exemple, sélectionnez `ExampleElements`, de sorte que l’utilisateur peut faire glisser des éléments nouveaux éléments existants.

    Notez que la classe d’indexation devient le nom de la EMD dans l’Explorateur DSL.

4. Sous **fusion de processus en créant des liens**, ajoutez deux chemins d’accès :

   - Un chemin d’accès lie le nouvel élément de modèle parent. L’expression de chemin d’accès que vous devrez entrer parcourt à partir de l’élément existant, de la relation d’incorporation au modèle parent. Enfin, il spécifie le rôle dans le nouveau lien auquel le nouvel élément sera être affecté. Le chemin d’accès est la suivante :

      `ExampleModelHasElements.ExampleModel/!ExampleModel/.Elements`

   - Le chemin d’accès lie le nouvel élément à l’élément existant. L’expression de chemin d’accès spécifie la relation de référence et le rôle auquel le nouvel élément sera être affecté. Ce chemin d’accès est la suivante :

      `ExampleElementReferencesTargets.Sources`

      Vous pouvez utiliser l’outil de navigation de chemin d’accès pour créer chaque chemin d’accès :

      1. Sous **fusion de processus en créant des liens à des chemins d’accès**, cliquez sur  **\<ajouter le chemin d’accès >**.

      2. Cliquez sur la flèche déroulante à droite de l’élément de liste. Une arborescence s’affiche.

      3. Développez les nœuds dans l’arborescence pour former le chemin d’accès que vous souhaitez spécifier.

5. Tester la solution DSL :

   1. Appuyez sur **F5** pour régénérer et exécuter la solution.

        La reconstruction prendra plus de temps que d’habitude, car le code généré sera actualisé à partir de modèles de texte à se conformer à la nouvelle définition DSL.

   2. Au démarrage de l’instance expérimentale de Visual Studio, ouvrez un fichier de modèle de votre DSL. Créer des éléments de l’exemple.

   3. Faites glisser à partir de la **élément exemple** outil sur une forme existante.

        Une nouvelle forme s’affiche, et il est lié à la forme existante avec un connecteur.

   4. Copier une forme existante. Sélectionnez une autre forme et collez.

        Une copie de la première forme est créée.  Il a un nouveau nom, et il est lié à la deuxième forme avec un connecteur.

Notez les points suivants à partir de cette procédure :

- En créant des Directives de fusion d’éléments, vous pouvez autoriser n’importe quelle classe d’élément pour accepter n’importe quel autre. Le EMD est créé dans la classe de domaine de réception et de la classe de domaine accepté est spécifiée dans le **Index, classe** champ.

- En définissant les chemins d’accès, vous pouvez spécifier quels liens doivent être utilisé pour connecter le nouvel élément au modèle existant.

     Les liens que vous spécifiez doivent inclure une relation d’incorporation.

- Le EMD affecte à la création de la boîte à outils ainsi que les opérations de collage.

     Si vous écrivez du code personnalisé qui crée de nouveaux éléments, vous pouvez appeler explicitement la EMD à l’aide de la `ElementOperations.Merge` (méthode). Cela permet de s’assurer que votre code lie les nouveaux éléments dans le modèle de la même façon que les autres opérations. Pour plus d’informations, consultez [personnalisation du comportement de copie](../modeling/customizing-copy-behavior.md).

## <a name="example-adding-custom-accept-code-to-an-emd"></a>Exemple : Ajout de code pour une directive EMD acceptation personnalisée

En ajoutant le code personnalisé à une directive EMD, vous pouvez définir le comportement de fusion plus complexe. Cet exemple simple empêche l’ajout d’un nombre fixe d’éléments vers le diagramme de l’utilisateur. L’exemple modifie la valeur par défaut EMD qui accompagne une relation d’incorporation.

### <a name="to-write-custom-accept-code-to-restrict-what-the-user-can-add"></a>Pour écrire du code d’acceptation personnalisée pour limiter ce que l’utilisateur peut ajouter

1. Créer une solution DSL à l’aide de la **langage Minimal** modèle de solution. Ouvrez le diagramme de définition DSL.

2. Dans l’Explorateur DSL, développez **Classes de domaine**, `ExampleModel`, **Directives de fusion d’éléments**. Sélectionnez la directive de fusion d’élément nommé `ExampleElement`.

     Cette EMD contrôle comment l’utilisateur peut créer nouveau `ExampleElement` objets dans le modèle, par exemple en faisant glisser à partir de la boîte à outils.

3. Dans le **détails DSL** fenêtre, sélectionnez **acceptation personnalisée d’utilise**.

4. Régénérez la solution. Cela prendra plus de temps que d’habitude, car le code généré sera actualisé à partir du modèle.

     Une erreur de build seront signalées, similaire à : « Company.ElementMergeSample.ExampleElement ne contient pas une définition pour CanMergeExampleElement... »

     Vous devez implémenter la méthode `CanMergeExampleElement`.

5. Créer un nouveau fichier de code dans le **Dsl** projet. Remplacez son contenu par le code suivant et remplacez l’espace de noms l’espace de noms de votre projet.

    ```csharp
    using Microsoft.VisualStudio.Modeling;

    namespace Company.ElementMergeSample // EDIT.
    {
      partial class ExampleModel
      {
        /// <summary>
        /// Called whenever an ExampleElement is to be merged into this ExampleModel.
        /// This happens when the user pastes an ExampleElement
        /// or drags from the toolbox.
        /// Determines whether the merge is allowed.
        /// </summary>
        /// <param name="rootElement">The root element in the merging EGP.</param>
        /// <param name="elementGroupPrototype">The EGP that the user wants to merge.</param>
        /// <returns>True if the merge is allowed</returns>
        private bool CanMergeExampleElement(ProtoElementBase rootElement, ElementGroupPrototype elementGroupPrototype)
        {
          // Allow no more than 4 elements to be added:
          return this.Elements.Count < 4;
        }
      }
    }
    ```

    Cet exemple simple restreint le nombre d’éléments qui peuvent être fusionnées dans le modèle parent. Pour des conditions plus intéressantes, la méthode peut inspecter les propriétés et les liens de l’objet de réception. Il peut également inspecter les propriétés des éléments de fusionnées, qui sont exécutées dans un <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype>. Pour plus d’informations sur `ElementGroupPrototypes`, consultez [personnalisation du comportement de copie](../modeling/customizing-copy-behavior.md). Pour plus d’informations sur la façon d’écrire du code qui lit un modèle, consultez [navigation et la mise à jour un modèle dans le Code de programme](../modeling/navigating-and-updating-a-model-in-program-code.md).

6. Tester la solution DSL :

    1. Appuyez sur **F5** pour régénérer la solution. Lorsque l’instance expérimentale de Visual Studio s’ouvre, ouvrez une instance de votre DSL.

    2. Créer de nouveaux éléments de plusieurs façons :

        - Faites glisser à partir de la **élément exemple** outil sur le diagramme.

        - Dans le **Explorateur de modèles d’exemple**, cliquez sur le nœud racine, puis cliquez sur **ajouter un nouvel élément d’exemple**.

        - Copiez et collez un élément sur le diagramme.

    3. Vérifiez que vous ne pouvez pas utiliser une des manières suivantes pour ajouter plus de quatre éléments au modèle. Il s’agit, car ils utilisent tous la Directive de fusion.

## <a name="example-adding-custom-merge-code-to-an-emd"></a>Exemple : Ajout de code personnalisé de fusion à une directive EMD

Dans le code de la fusion personnalisée, vous pouvez définir ce qui se passe lorsque l’utilisateur fait glisser un outil ou colle un élément sur un élément. Il existe deux façons de définir une fusion personnalisée :

1. Définissez **utilise une fusion personnalisée** et fournir le code requis. Votre code remplace le code généré de fusion. Utilisez cette option si vous souhaitez complètement redéfinir ce que fait la fusion.

2. Remplacer le `MergeRelate` (méthode) et éventuellement le `MergeDisconnect` (méthode). Pour ce faire, vous devez définir le **génère une Double dérivée** propriété de la classe de domaine. Votre code peut appeler le code généré de fusion dans la classe de base. Utilisez cette option si vous souhaitez effectuer des opérations supplémentaires une fois la fusion a été effectuée.

   Ces approches affectent uniquement les fusions qui sont effectuées en utilisant cette EMD. Si vous souhaitez affecter toutes les façons dans laquelle l’élément fusionné peut être créée, une alternative consiste à définir un `AddRule` sur la relation d’incorporation et un `DeleteRule` sur la classe de domaine fusionnée. Pour plus d’informations, consultez [propager les modifications dans le modèle de règles](../modeling/rules-propagate-changes-within-the-model.md).

### <a name="to-override-mergerelate"></a>Pour remplacer MergeRelate

1. Dans la définition DSL, assurez-vous que vous avez défini le EMD auquel vous souhaitez ajouter le code. Si vous le souhaitez, vous pouvez ajouter des chemins d’accès et définir accepter du code personnalisé comme décrit dans les sections précédentes.

2. Dans le diagramme DslDefinition, sélectionnez la classe réceptrice de la fusion. En règle générale, c’est la classe à la fin de la source d’une relation d’incorporation.

     Par exemple, dans une solution DSL générée à partir de la solution de langage Minimal, sélectionnez `ExampleModel`.

3. Dans le **propriétés** fenêtre, définissez **génère une Double dérivée** à **true**.

4. Régénérez la solution.

5. Inspecter le contenu de **Dsl\Generated Files\DomainClasses.cs**. Recherche de méthodes nommées `MergeRelate` et examinez leur contenu. Cela vous aidera à écrire vos propres versions.

6. Dans un nouveau fichier de code, écrivez une classe partielle pour la classe réceptrice et remplacer le `MergeRelate` (méthode). N’oubliez pas d’appeler la méthode de base. Exemple :

    ```csharp
    partial class ExampleModel
    {
      /// <summary>
      /// Called when the user drags or pastes an ExampleElement onto the diagram.
      /// Sets the time of day as the name.
      /// </summary>
      /// <param name="sourceElement">Element to be added</param>
      /// <param name="elementGroup">Elements to be merged</param>
      protected override void MergeRelate(ModelElement sourceElement, ElementGroup elementGroup)
      {
        // Connect the element according to the EMD:
        base.MergeRelate(sourceElement, elementGroup);

        // Custom actions:
        ExampleElement mergingElement = sourceElement as ExampleElement;
        if (mergingElement != null)
        {
          mergingElement.Name = DateTime.Now.ToLongTimeString();
        }
      }
    }
    ```

### <a name="to-write-custom-merge-code"></a>Pour écrire du code personnalisé de fusion

1. Dans **Dsl\Generated Code\DomainClasses.cs**, inspecter des méthodes nommées `MergeRelate`. Ces méthodes créent des liens entre un nouvel élément et le modèle existant.

    Par ailleurs, inspectez les méthodes nommées `MergeDisconnect`. Ces méthodes dissocier un élément à partir du modèle lorsqu’il est à supprimer.

2. Dans **Explorateur DSL**, sélectionnez ou créez la Directive de fusion que vous souhaitez personnaliser. Dans le **détails DSL** fenêtre, définissez **utilise une fusion personnalisée**.

    Lorsque vous définissez cette option, le **processus de fusion** et **avant fusion** options sont ignorées. Votre code est utilisé à la place.

3. Régénérez la solution. Il sera plus longue que d’habitude, car les fichiers de code généré seront actualisées à partir du modèle.

    Messages d’erreur seront affiche. Double-cliquez sur les messages d’erreur pour afficher les instructions dans le code généré. Ces instructions vous demandent de fournir deux méthodes, `MergeRelate` *YourDomainClass* et `MergeDisconnect` *YourDomainClass*

4. Écrire les méthodes dans une définition de classe partielle dans un fichier de code séparé. Les exemples que vous inspecté précédemment doivent proposer ce dont vous avez besoin.

   Personnalisé fusionner du code n’affecteront pas de code qui crée des objets et relations directement et n’affecte pas les autres EMDs. Pour vous assurer que vos modifications supplémentaires sont implémentées, quel que soit la façon dont l’élément est créé, envisagez l’écriture un `AddRule` et une `DeleteRule` à la place. Pour plus d’informations, consultez [propager les modifications dans le modèle de règles](../modeling/rules-propagate-changes-within-the-model.md).

## <a name="redirecting-a-merge-operation"></a>Redirection d’une opération de fusion

Une directive de fusion vers l’avant redirige la cible d’une opération de fusion. En règle générale, la nouvelle cible est le parent d’incorporation de la cible initiale.

Par exemple, dans une solution DSL qui a été créée avec le modèle de diagramme de composant, les Ports sont incorporés dans les composants. Ports sont affichés sous forme de petites formes sur le bord d’une forme de composant. L’utilisateur crée des ports en faisant glisser l’outil de Port sur une forme de composant. Mais parfois, l’utilisateur par inadvertance fait glisser l’outil Port un port existant, au lieu du composant, et l’opération échoue. Il s’agit d’une simple erreur lorsqu’il y a plusieurs ports existants. Pour aider l’utilisateur afin d’éviter cette nuisance, vous pouvez autoriser les ports pour les faire glisser vers un port existant, mais que l’action redirigée vers le composant parent. L’opération fonctionne comme si l’élément cible ont été le composant.

Vous pouvez créer une directive de fusion vers l’avant dans la solution de modèle de composant. Si vous compilez et exécutez la solution d’origine, vous devez voir que les utilisateurs peuvent faire glisser n’importe quel nombre de **Port d’entrée** ou **Port de sortie** éléments à partir de la **boîte à outils** à un **Composant** élément. Toutefois, ils ne peuvent pas faire glisser un port à un port existant. Les alertes de pointeur indisponible que ce déplacement n’est pas activés. Toutefois, vous pouvez créer une directive de fusion vers l’avant afin qu’un port qui est accidentellement supprimé sur un **Port d’entrée** est transféré à la **composant** élément.

### <a name="to-create-a-forward-merge-directive"></a>Pour créer une directive de fusion vers l’avant

1. Créer un [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] solution à l’aide du modèle de modèle de composant.

2. Afficher le **Explorateur DSL** en ouvrant DslDefinition.dsl.

3. Dans le **Explorateur DSL**, développez **Classes de domaine**.

4. Le **ComponentPort** de classe de domaine abstraite est la classe de base des deux **InPort** et **OutPort**. Avec le bouton droit **ComponentPort** puis cliquez sur **ajouter nouvelle Directive de fusion**.

    Un nouveau **Directive de fusion** nœud apparaît sous la **Directives de fusion d’éléments** nœud.

5. Sélectionnez le **Directive de fusion** nœud et ouvrez le **détails DSL** fenêtre.

6. Dans la liste de classe de l’indexation, sélectionnez **ComponentPort**.

7. Sélectionnez **transférer la fusion à une autre classe de domaine**.

8. Dans la liste de sélection de chemin d’accès, développez **ComponentPort**, développez **ComponentHasPorts**, puis sélectionnez **composant**.

    Le nouveau chemin d’accès doit se présenter comme ceci :

    **ComponentHasPorts.Component/!Component**

9. Enregistrer la solution et puis transformer les modèles en cliquant sur le bouton plus à droite sur la **l’Explorateur de solutions** barre d’outils.

10. Générez et exécutez la solution. Une nouvelle instance de Visual Studio s’affiche.

11. Dans **l’Explorateur de solutions**, ouvrez Sample.mydsl. Le diagramme et le **boîte à outils ComponentLanguage** s’affichent.

12. Faites glisser un **Port d’entrée** à partir de la **boîte à outils** vers un autre **Port d’entrée.** Ensuite, faites glisser un **OutputPort** à un **InputPort** et ensuite à un autre **OutputPort**.

     Vous ne verrez pas le pointeur non disponible, et vous devez pouvoir supprimer le nouveau **Port d’entrée** sur celui existant. Sélectionnez la nouvelle **Port d’entrée** et faites-le glisser vers un autre point la **composant**.

## <a name="see-also"></a>Voir aussi

- [Navigation et mise à jour d’un modèle dans le code de programme](../modeling/navigating-and-updating-a-model-in-program-code.md)
- [Personnalisation des outils et de la boîte à outils](../modeling/customizing-tools-and-the-toolbox.md)
- [Exemple de diagrammes de circuit DSL](https://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)