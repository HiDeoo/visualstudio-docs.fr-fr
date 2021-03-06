---
title: 'Diagrammes de classes UML : indications | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- vs.teamarch.logicalclassdiagram.overrideoperationsdialog
helpviewer_keywords:
- UML diagrams, class
- diagrams - modeling, class
- UML, class diagrams
- class diagrams - UML
- diagrams - modeling, UML class
ms.assetid: 94dbfd55-b300-4b49-9049-0831ed849486
caps.latest.revision: 56
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 4f4fd6eed634da3aea956cddca8d2e1ff6220a94
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75850189"
---
# <a name="uml-class-diagrams-guidelines"></a>Diagrammes de classes UML : indications
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans Visual Studio, vous pouvez utiliser un *diagramme de classes UML* pour décrire les types de données et leurs relations indépendamment de leur implémentation. Le diagramme permet de se concentrer sur les aspects logiques des classes, plutôt que sur leur implémentation.

 Pour créer un diagramme de classes UML, dans le menu **architecture** , choisissez **nouveau diagramme UML ou diagramme de couche**.

 Pour connaître les versions de Visual Studio qui prennent en charge cette fonctionnalité, consultez [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

> [!NOTE]
> Cette rubrique concerne les diagrammes de classes UML. Il existe un autre genre de diagramme de classes, que vous pouvez créer et utiliser pour visualiser le code du programme. Consultez [conception et affichage des classes et des types](https://msdn.microsoft.com/library/ab7aty24.aspx).

## <a name="using-uml-class-diagrams"></a><a name="Using"></a> Utilisation de diagrammes de classes UML
 Vous pouvez utiliser un diagramme de classes UML à diverses fins :

- Pour fournir une description indépendante de l'implémentation des types utilisés dans un système et passés entre ses composants.

     Par exemple, le type Commande de repas peut être implémenté dans le code .NET de la couche métier, dans le XML au niveau des interfaces entre les différents composants, dans les bases de données SQL, ainsi que dans l'interface utilisateur du HTML. Bien que ces implémentations diffèrent dans les détails, la relation entre Commande de repas et les autres types, tels que Menu et Paiement, est toujours la même. Le diagramme de classes UML permet d'évoquer ces relations indépendamment des implémentations.

- Pour clarifier le glossaire des termes utilisés pour la communication entre l'application et ses utilisateurs, ainsi que dans les descriptions de leurs besoins. Consultez [Configuration requise pour les utilisateurs du modèle](../modeling/model-user-requirements.md).

     Par exemple, considérez les descriptions des récits utilisateur, des cas d’usage ou des autres exigences d’une application de restaurant. Dans une telle description, vous recherchez des termes tels que Menu, Commande, Repas, Prix, Paiement, etc. Vous pouvez dessiner un diagramme de classes UML qui définit les relations entre ces termes. Cela réduira le risque d'incohérences dans les descriptions d'impératifs, dans l'interface utilisateur et dans les documents d'aide.

### <a name="relationship-to-other-diagrams"></a>Relation aux autres diagrammes
 Un diagramme de classes UML est généralement dessiné avec d'autres diagrammes de modélisation, afin de fournir des descriptions des types qu'ils utilisent. En tous les cas, la représentation physique des types n'est pas impliquée par l'un des diagrammes.

 Diagramme d'activités

 Type des données traversant un nœud d'objet.

 Types de broches d'entrée et de sortie, et de nœuds de paramètres d'activités.

 Consultez [diagrammes d’activités UML : indications](../modeling/uml-activity-diagrams-guidelines.md).

 Diagramme de séquence

 Types de paramètres et de valeurs de retour de messages.

 Types des lignes de vie. La classe d'une ligne de vie doit inclure des opérations pour tous les messages qu'elle peut recevoir.

 Consultez [diagrammes de séquence UML : indications](../modeling/uml-sequence-diagrams-guidelines.md).

 Diagramme de composant

 Interfaces de composant, répertoriant leurs opérations.

 Consultez [diagrammes de composants UML : indications](../modeling/uml-component-diagrams-guidelines.md).

 Diagramme de cas d'usage

 Types mentionnés dans les descriptions des objectifs et des étapes d'un cas d'usage.

 Consultez [diagrammes de cas d’usage UML : indications](../modeling/uml-use-case-diagrams-guidelines.md).

## <a name="basic-steps-for-drawing-class-diagrams"></a><a name="BasicSteps"></a> Étapes de base pour le dessin de diagrammes de classes
 Pour obtenir des informations de référence sur les éléments des diagrammes de classes UML, consultez [diagrammes de classes UML : référence](../modeling/uml-class-diagrams-reference.md).

> [!NOTE]
> Les étapes détaillées de création des diagrammes de modélisation sont décrites dans [modifier des modèles et des diagrammes UML](../modeling/edit-uml-models-and-diagrams.md).

#### <a name="to-create-a-uml-class-diagram"></a>Pour créer un diagramme de classes UML

1. Dans le menu **architecture** , choisissez **nouveau diagramme UML ou diagramme de couche**.

2. Sous **modèles**, choisissez **diagramme de classes UML**.

3. Nommez le diagramme.

4. Dans **Ajouter au projet de modélisation**, sélectionnez un projet de modélisation existant dans votre solution, ou **créez un nouveau projet de modélisation**, puis choisissez **OK**.

     Un nouveau diagramme de classes apparaît avec la boîte à outils du **diagramme UMLClass** . La boîte à outils contient les relations et les éléments requis.

#### <a name="to-draw-a-uml-class-diagram"></a>Pour dessiner un diagramme de classes UML

1. Pour créer un type, choisissez l’outil de **classe**, d' **interface** ou d' **énumération** dans la boîte à outils, puis cliquez sur une partie vide du diagramme. (Si vous ne voyez pas la Boîte à Outils, appuyez sur Ctrl+Alt+X.)

2. Pour ajouter des attributs ou des opérations aux types, ou des littéraux à une énumération, choisissez l’en-tête **attributs**, **opérations** ou **littéraux** dans le type, puis appuyez sur entrée.

     Vous pouvez écrire une signature telle que `f(x:Boolean):Integer`. Consultez [attributs et opérations](#AttributesAndOperations).

     Pour ajouter plusieurs éléments rapidement, appuyez deux fois sur ENTRÉE à la fin de chaque élément. Vous pouvez utiliser les touches de direction pour vous déplacer vers le haut ou le bas de la liste.

3. Pour développer ou réduire un type, choisissez l'icône de chevron située en haut à gauche de celui-ci. Vous pouvez également développer et réduire la section **attributs** et **opérations** d’une classe ou d’une interface.

4. Pour dessiner des liens d'associations, d'héritage ou encore de dépendance entre les différents types, cliquez successivement sur l'outil approprié, sur le type source et sur le type cible.

5. Pour créer des types dans un package, créez un package à l’aide de l’outil **package** , puis créez de nouveaux types et packages dans le package. Vous pouvez également utiliser la commande de copie pour copier des types et les coller dans un package.

6. Un diagramme est une vue dans un modèle partagé entre les autres diagrammes du même projet. Pour afficher une arborescence du modèle complet, choisissez **affichage**, **autres fenêtres**, Explorateur de **modèles UML**.

## <a name="using-classes-interfaces-and-enumerations"></a><a name="UsingTypes"></a> Utilisation des classes, des interfaces et des énumérations
 Il existe trois genres standard de classifieurs disponibles dans la boîte à outils. Ces types sont appelés « *types* » dans ce document.

 ![Classe, énumération et interface](../modeling/media/uml-classguidetypes.png "UML_ClassGuideTypes")

- Utilisez des **classes** (1) pour représenter des types de données ou d’objet dans la plupart des cas.

- Utilisez les **interfaces** (2) dans un contexte où vous devez faire la différence entre des interfaces pures et des classes concrètes qui ont des implémentations internes. Cette différence est utile lorsque l'objectif du diagramme consiste à décrire une implémentation logicielle. Celle-ci est moins utile lorsque vous modélisez des données passives ou que vous définissez des concepts permettant de décrire les besoins des utilisateurs.

- Utilisez une **énumération** (3) pour représenter un type qui a un nombre limité de valeurs littérales, par exemple `Stop` et `Go` .

  - Ajoutez les valeurs littérales à l'énumération. Attribuez à chacune un nom bien distinct.

  - Si vous le souhaitez, vous pouvez également fournir une valeur numérique pour chaque valeur littérale. Ouvrez le menu contextuel du littéral dans l’énumération, choisissez **Propriétés**, puis tapez un nombre dans le champ **valeur** de la fenêtre **Propriétés** .

  Attribuez un nom unique à chaque type.

### <a name="getting-types-from-other-diagrams"></a>Obtention de types d'autres diagrammes
 Vous pouvez faire apparaître des types d'un autre diagramme dans votre diagramme de classes UML.

 Diagramme de classes UML

 Vous pouvez faire apparaître une classe sur plusieurs diagrammes de classes UML. Lorsque vous avez créé une classe sur un diagramme, faites glisser la classe de l' **Explorateur de modèles UML** vers l’autre diagramme.

 Cette opération est utile si vous souhaitez que chaque diagramme se concentre sur un groupe particulier de relations.

 Par exemple, vous pourriez afficher les associations entre une Commande de repas et le Menu de restaurant dans un diagramme, de même que celles entre Commande de repas et Paiement, dans un autre.

 Diagramme de composant

 Si vous avez défini des interfaces sur les composants dans un diagramme de composant, vous pouvez faire glisser une interface depuis l' **Explorateur de modèles UML** vers le diagramme de classes. Dans le diagramme de classes, vous pouvez définir des méthodes incluses dans l'interface.

 Consultez [diagrammes de composants UML : indications](../modeling/uml-component-diagrams-guidelines.md).

 Diagramme de séquence UML

 Vous pouvez créer des classes et des interfaces à partir de Lifeline dans un diagramme de séquence, puis faire glisser la classe de l' **Explorateur de modèles UML** vers un diagramme de classes UML. Chaque ligne de vie d'un diagramme de séquences représente une instance d'objet, de composant ou encore d'acteur.

 Pour créer une classe à partir d’une vie, ouvrez le menu contextuel de la vie, puis choisissez **créer une classe** ou **créer une interface**. Consultez [diagrammes de séquence UML : indications](../modeling/uml-sequence-diagrams-guidelines.md).

## <a name="attributes-and-operations"></a><a name="AttributesAndOperations"></a> Attributs et opérations
 Un attribut (4) est une valeur nommée que chaque instance de type peut posséder. L'accès à un attribut ne modifie pas l'état de l'instance.

 Une opération (5) est une méthode ou une fonction que les instances du type peuvent exécuter. Elle peut retourner une valeur. Si sa propriété **isQuery** a la valeur true, il ne peut pas modifier l’état de l’instance.

 Pour ajouter un attribut ou une opération à un type, ouvrez le menu contextuel du type, choisissez **Ajouter**, puis choisissez **attribut** ou **opération**.

 Pour afficher ses propriétés, ouvrez le menu contextuel de l’attribut ou de l’opération, puis choisissez **Propriétés**. Les propriétés s’affichent dans la fenêtre **Propriétés** .

 Pour afficher les propriétés des paramètres d’une opération, choisissez <strong>[...]</strong> dans la propriété **Parameters** . Une nouvelle boîte de dialogue de propriétés apparaît alors.

 Pour obtenir des informations détaillées concernant l'ensemble des propriétés qu'il est possible de définir, consultez :

- [Propriétés d’attributs dans des diagrammes de classes UML](../modeling/properties-of-attributes-on-uml-class-diagrams.md)

- [Propriétés d’opérations dans des diagrammes de classes UML](../modeling/properties-of-operations-on-uml-class-diagrams.md)

### <a name="types-of-attributes-and-operations"></a>Types d'attributs et d'opérations
 Chaque *type* d’un attribut ou d’une opération, et chaque type de paramètre, peut être l’un des suivants :

- **(aucun)** -vous pouvez conserver un type non spécifié dans la signature en omettant les deux-points précédents ( `:` ).

- Un des types primitifs standard : **Boolean**, **Integer**, **String**.

- Type défini dans votre modèle.

- Valeur paramétrable d’un type de modèle, modèle écrit \<Parameter> . Consultez [types de modèles](#Templates).

  Vous pouvez également écrire le nom d'un type que vous n'avez pas encore défini dans votre modèle. Le nom est listé sous **types non spécifiés** dans l’Explorateur de modèles UML.

> [!NOTE]
> Si vous définissez ensuite une classe ou une interface de ce nom dans votre modèle, les attributs et les opérations antérieurs feront encore référence à l'élément dans Types non spécifiés. Si vous souhaitez les modifier pour faire référence à la nouvelle classe, vous devez traiter chaque attribut ou opération et réinitialiser le type, en sélectionnant la nouvelle classe dans le menu déroulant.

#### <a name="multiple-types"></a>Types multiples
 Vous pouvez définir une multiplicité de type d'attribut, d'opération ou encore de paramètre.

 Les valeurs autorisées sont les suivantes :

 `[1]`

 Valeur du type donné. Il s'agit de la valeur par défaut.

 `[0..1]`

 **Null** ou une valeur du type donné.

 `[*]`

 Collection des nombres d’instances du type donné.

 `[1..*]`

 Collection d'au moins une instance du type donné.

 `[n..m]`

 Collection entre `n` et `m` instances du type donné.

 Si la multiplicité est supérieure à 1, vous pouvez également définir les propriétés suivantes :

- **IsOrdered** : si la valeur est true, la collection a un ordre défini.

- **IsUnique** : si la valeur est true, la collection ne contient aucune valeur en double.

### <a name="visibility"></a>Visibilité
 *Visibility* indique si l’attribut ou l’opération est accessible en dehors de la définition de classe. Les valeurs autorisées sont les suivantes :

 **Public**

 **+**

 Accessible à partir de tous les autres types.

 **Privé**

 **-**

 Accessible uniquement par la définition interne de ce type.

 **Package**

 **~**

 Accessible uniquement dans le package qui contient ce type, ainsi que dans tous les packages qui l'importent explicitement. Consultez [définition des espaces de noms et des packages](#Packages).

 **Protect**

 **#**

 Accessible uniquement par ce type et par ceux qui héritent de lui. Consultez [héritage](#Inheritance).

### <a name="setting-the-signature-of-an-attribute-or-an-operation"></a>Définition de la signature d'un attribut ou d'une opération
 La signature d'un attribut ou d'une opération est une collection de propriétés qui inclut sa visibilité, son nom, ses paramètres (pour les opérations) et son type.

 Vous pouvez écrire une signature directement dans le diagramme. Cliquez sur l'attribut ou sur l'opération pour la sélectionner, puis cliquez une nouvelle fois dessus.

 Écrivez la signature comme suit :

```
visibility attribute-name : Type
```

 \- ou -

```
visibility operation-name (parameter1 : Type1, ...) : Type
```

 Par exemple :

```
+ AddItem (item : MenuItem, quantity : Integer) : Boolean
```

 Utilisez la forme abrégée de visibilité. La valeur par défaut est `+` (public).

 Chaque type peut correspondre à des types que vous avez définis dans le modèle, à des types standard tels qu'Entier ou Chaîne ou encore au nom d'un nouveau type que vous n'avez pas encore défini.

> [!NOTE]
> Si vous écrivez un nom sans un type dans une liste de paramètres, il indique le nom du paramètre plutôt que celui de son type. Dans cet exemple, Élément de menu et Entier deviennent les noms de deux paramètres aux types non spécifiés :
>
> `AddItem(MenuItem, Integer) /* parameter names, not types! */`

 Pour définir la multiplicité d'un type dans une signature, écrivez la multiplicité entre crochets à la suite du nom de type. Par exemple :

```
+ AddItems (items : MenuItem [1..*])
+ MenuContent : MenuItem [*]
```

 Si l'attribut ou l'opération est statique, son nom apparaîtra souligné dans la signature. Si cela est abstrait, le nom s'affichera alors en italique.

 Toutefois, vous ne pouvez définir que les propriétés **is static** et **is abstract** dans la fenêtre **Propriétés** .

#### <a name="full-signature"></a>Signature complète
 Lorsque vous modifiez la signature d'un attribut ou d'une opération, certaines propriétés supplémentaires peuvent apparaître à la fin de la ligne et après chaque paramètre. Elles apparaissent entre accolades {…}. Vous pouvez modifier ou ajouter ces propriétés. Par exemple :

```
+ AddItems (items: MenuItem [1..*] {unique, ordered})
+ GetItems (filter: String) : MenuItem [*] {ordered, query}
```

 Ces propriétés sont les suivantes :

 `unique`

 **Est unique**

 La collection ne contient aucune valeur en double. S'applique aux types dont la multiplicité est supérieure à 1.

 `ordered`

 **Is Ordered**

 La collection est une séquence. Si la valeur false lui est affectée, il n'existe aucun premier élément défini. S'applique aux types dont la multiplicité est supérieure à 1.

 `query`

 **Is Query**

 L'opération ne modifie pas l'état de son instance. S'applique uniquement aux opérations.

 `/`

 **Is Derived**

 L'attribut est calculé à partir de valeurs d'autres attributs ou associations.

 « / » apparaît avant le nom d'un attribut. Par exemple :

```
/TotalPrice: Integer
```

 En général, la signature complète apparaît uniquement dans le diagramme pendant que vous le modifiez. Une fois la modification effectuée, les propriétés supplémentaires sont masquées. Si vous souhaitez voir la signature complète tout le temps, ouvrez le menu contextuel du type, puis choisissez afficher la **signature complète**.

## <a name="drawing-and-using-associations"></a><a name="Associations"></a> Dessiner et utiliser des associations
 Utilisez une association pour représenter tout genre de liaison entre deux éléments, indépendamment de la façon dont cette liaison est implémentée dans le logiciel. Par exemple, vous pouvez utiliser une association pour représenter un pointeur en langage C#, une relation dans une base de données ou encore une référence croisée entre deux parties d'un fichier XML. Elle peut représenter une association entre des objets du monde réel, tels que la Terre et le soleil. L'association n'indique pas comment le lien est représenté, mais seulement que les informations existent.

### <a name="properties-of-an-association"></a>Propriétés d'une association
 Après avoir créé une association, définissez-en les propriétés. Ouvrez le menu contextuel de l’Association, puis choisissez **Propriétés**.

 Outre les propriétés de l’Association dans son ensemble, chaque *rôle*, autrement dit, chaque terminaison de l’Association, a ses propres propriétés. Pour les afficher, développez les propriétés **premier rôle** et **deuxième rôle** .

 Quelques propriétés de chaque rôle sont directement visibles dans le diagramme. Les voici :

- Nom du rôle. Cette propriété apparaît à la fin appropriée de l'association dans le diagramme. Vous pouvez le définir sur le diagramme ou dans la fenêtre **Propriétés** .

- **Multiplicité**, qui a comme valeur par défaut **1**. Cette propriété apparaît également dans le diagramme, près de la fin appropriée de l'association.

- **Agrégation**. Cette propriété apparaît sous la forme d'un diamant, au niveau de l'une des extrémités du connecteur. Vous pouvez l'utiliser pour indiquer que les instances au niveau du rôle d'agrégation possèdent ou contiennent des instances de l'autre.

- **Est navigable**. Si la valeur true lui est affectée pour un seul rôle, une flèche s'affiche dans la direction navigable. Vous pouvez l'utiliser pour indiquer la navigabilité des liens et des relations de bases de données du logiciel.

  Pour obtenir des informations complètes sur ces propriétés et d’autres, consultez [propriétés d’associations dans des diagrammes de classes UML](../modeling/properties-of-associations-on-uml-class-diagrams.md).

### <a name="navigability"></a>Navigabilité
 Lorsque vous dessinez une association, celle-ci comporte une flèche à l'extrémité, ce qui signifie que l'association est navigable dans cette direction. Cela est utile si votre diagramme de classes représente des classes logicielles et que les associations représentent des pointeurs ou des références. Cependant, lorsque vous utilisez un diagramme de classes pour représenter des entités et des relations ou des concepts d'entreprise, il est moins approprié pour représenter la navigabilité. Dans ce cas, il est préférable de dessiner des associations sans flèches. Pour ce faire, vous pouvez affecter la valeur true à la propriété **is navigable** des deux extrémités de l’Association.

### <a name="attributes-and-associations"></a>Attributs et associations
 Une association est une représentation graphique de l'affichage d'un attribut. Par exemple, vous pouvez dessiner une association entre Restaurant et Menu au lieu de créer une classe Restaurant avec un attribut de type Menu.

 Chaque nom d'attribut devient un nom de rôle. Il apparaît à l'extrémité opposée de l'association par rapport au type propriétaire. Examinez, par exemple, `myMenu` dans l'illustration.

 En général, il est préférable de n'utiliser des attributs que pour les types que vous ne dessineriez pas dans le diagramme, comme les types primitifs.

 ![Association équivalente et attributs](../modeling/media/uml-classguideattrib.png "UML_ClassGuideAttrib")

## <a name="inheritance"></a><a name="Inheritance"></a> Inheritance
 Utilisez l’outil **héritage** pour créer les relations suivantes :

- Relation de *généralisation* entre un type spécialisé et un type général

   \- ou -

- Relation de *réalisation* entre une classe et une interface qu’elle implémente.

  Vous ne pouvez pas créer de boucle dans les relations d'héritage.

### <a name="generalization"></a>Généralisation
 La généralisation signifie que le type de spécialisation ou dérivé hérite d'attributs, d'opérations et d'associations du type général ou de base.

 Le type général apparaît à l'extrémité de la flèche de la relation.

 Les opérations et attributs hérités ne sont généralement pas affichés dans les types de spécialisation. Cependant, vous pouvez ajouter des opérations héritées à la liste des opérations du type de spécialisation. Cela est particulièrement utile si vous souhaitez substituer certaines des propriétés d'une opération dans le type de spécialisation, ou encore si vous souhaitez indiquer que le code d'implémentation doit s'en charger.

##### <a name="to-override-an-operations-definition-in-a-specializing-type"></a>Pour substituer une définition d'opération dans un type de spécialisation

1. Cliquez sur la relation de généralisation.

    Elle apparaît en surbrillance et une balise d'action apparaît près d'elle.

2. Cliquez sur la balise d’action, puis sur **remplacer les opérations**.

    La boîte de dialogue **opérations de remplacement** s’affiche.

3. Sélectionnez les opérations que vous souhaitez voir apparaître dans le type de spécialisation, puis cliquez sur **OK**.

   Les opérations que vous avez sélectionnées apparaissent à présent dans le type de spécialisation.

### <a name="realization"></a>Réalisation
 La réalisation signifie qu'une classe implémente les attributs et opérations spécifiés par l'interface. L'interface se situe au niveau de l'embout de flèche du connecteur.

 Lorsque vous créez un connecteur de réalisation, les opérations de l'interface sont automatiquement répliquées dans la classe de réalisation. Si vous ajoutez de nouvelles opérations à une interface, elles sont alors répliquées dans ses classes de réalisation.

 Après avoir créé une relation de réalisation, vous pouvez la convertir en notation de symbole d'interface. Cliquez avec le bouton droit sur la relation, puis choisissez **afficher comme Lollipop**.

 Cela vous permet d'afficher les interfaces qu'une classe implémente, sans encombrer les diagrammes de classes avec des liens de réalisation. Vous pouvez également afficher l'interface et les classes de réalisation dans des diagrammes séparés.

 ![Réalisation présentée avec connecteur et lollipop](../modeling/media/uml-classguiderealize.png "UML_ClassGuideRealize")

## <a name="template-types"></a><a name="Templates"></a> Types de modèles
 Vous pouvez définir un type générique ou de modèle qui peut être paramétrable par d'autres types ou valeurs.

 Par exemple, vous pouvez créer un dictionnaire générique paramétrable par des types de clés et de valeurs :

 ![Classe de modèle avec deux paramètres](../modeling/media/uml-classguidetemplate1.png "UML_ClassGuideTemplate1")

#### <a name="to-create-a-template-type"></a>Pour créer un type de modèle

1. Créez une classe ou une interface. Celle-ci figurera alors comme votre type de modèle. Nommez-la en conséquence. Par exemple, `Dictionary`.

2. Ouvrez le menu contextuel du nouveau type, puis choisissez **Propriétés**.

3. Dans la fenêtre **Propriétés** , cliquez sur **[...]** dans le champ **paramètres du modèle** .

    La boîte de dialogue **éditeur de collection de paramètres de modèle** s’affiche.

4. Choisissez **Ajouter**.

5. Affectez un nom de paramètre à la propriété de nom pour votre type de modèle (par exemple, `Key`).

6. Définissez le **genre de paramètre**. La valeur par défaut est **Class**.

7. Si vous souhaitez que le paramètre accepte uniquement les classes dérivées d’une classe de base particulière, définissez la valeur de la **restriction** sur la classe de base de votre choix.

8. Ajoutez autant de paramètres que nécessaire, puis choisissez **OK**.

9. Ajoutez des attributs et des opérations au type de modèle, comme vous le feriez pour d'autres classes.

     Vous pouvez utiliser des paramètres dont le type est **classe**, **interface** ou **énumération** dans la définition des attributs et des opérations. Par exemple, vous pouvez définir cette opération dans `Key` en utilisant des classes de paramètres `Value` et `Dictionary` :

     `Get(k : Key) : Value`

     Vous pouvez utiliser un paramètre dont le type est un **entier** comme limite dans une multiplicité. Par exemple, une valeur maximale de paramètre de nombre entier peut être utilisée pour définir la multiplicité d'un attribut sous la forme `[0..max]`.

   Après avoir créé des types de modèles, vous pouvez les utiliser pour définir des liaisons de modèles :

   ![Classe liée à partir du modèle Dictionary](../modeling/media/uml-classguidetemplate2.png "UML_ClassGuideTemplate2")

#### <a name="to-use-a-template-type"></a>Pour utiliser un type de modèle

1. Créez un type (par exemple, `AddressTable`).

2. Ouvrez le menu contextuel du nouveau type, puis choisissez **Propriétés**.

3. Dans la propriété **liaison de modèle** , sélectionnez le type de modèle, par exemple `Dictionary` , dans la liste déroulante.

4. Développez la propriété **liaison de modèle** .

     Une ligne apparaît pour chaque paramètre du type de modèle.

5. Affectez une valeur appropriée à chaque paramètre. Par exemple, affectez au paramètre `Key` une classe appelée `Name`.

## <a name="packages"></a><a name="Packages"></a> .
 Vous pouvez visualiser des packages dans un diagramme de classes UML. Un package est un conteneur pour d'autres éléments de modèles. Vous pouvez créer tout élément à l'intérieur d'un package. Dans le diagramme, les éléments se trouvant à l'intérieur du package se déplaceront en même temps que ce dernier.

 Vous pouvez utiliser la commande de réduction/développement pour masquer ou afficher le contenu du package.

 Consultez [définir des packages et des espaces de noms](../modeling/define-packages-and-namespaces.md).

## <a name="generating-code-from-uml-class-diagrams"></a><a name="generating"></a> Génération de code à partir de diagrammes de classes UML
 Pour démarrer l'implémentation des classes sur un diagramme de classes UML, il est possible de générer le code C# ou de personnaliser les modèles de génération du code. Pour démarrer la génération de code à l'aide des modèles C# fournis :

- Ouvrez le menu contextuel du diagramme ou d’un élément, choisissez **générer le code**, puis définissez les propriétés nécessaires.

     Pour plus d’informations sur la définition de ces propriétés et sur la personnalisation des modèles fournis, consultez [générer du code à partir de diagrammes de classes UML](../modeling/generate-code-from-uml-class-diagrams.md).

## <a name="see-also"></a>Voir aussi
 [Modifier des diagrammes et des modèles UML diagrammes de](../modeling/edit-uml-models-and-diagrams.md) [classes UML : modèle de référence](../modeling/uml-class-diagrams-reference.md) [spécifications des utilisateurs modèle](../modeling/model-user-requirements.md) [UML diagrammes de composants : référence](../modeling/uml-component-diagrams-reference.md) diagrammes de [séquence UML : référence](../modeling/uml-sequence-diagrams-reference.md) [diagrammes de cas d’usage UML :](../modeling/uml-use-case-diagrams-reference.md) référence [diagrammes de composants UML : référence](../modeling/uml-component-diagrams-reference.md)
