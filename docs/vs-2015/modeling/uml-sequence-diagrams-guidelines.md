---
title: 'Diagrammes de séquence UML : indications | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- vs.teamarch.sequencediagram.linktosequencediagram
- vs.teamarch.logicalclassdiagram.createlifeline
- vs.teamarch.componentdiagram.createlifeline
helpviewer_keywords:
- diagrams - modeling, sequence
- sequence diagrams
- UML diagrams, sequence
- interactions, UML
- diagrams - modeling, UML sequence
- UML interactions
- UML, sequence diagrams
- UML sequence diagrams
- behaviors, UML
ms.assetid: 5990ef7c-ba60-4e20-a36d-e29c1fa6c8bb
caps.latest.revision: 55
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: cdd853307bdea28c48762a6a3f0416e698b577ff
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75850122"
---
# <a name="uml-sequence-diagrams-guidelines"></a>UML Sequence Diagrams: Guidelines
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans Visual Studio, vous pouvez dessiner un *diagramme de séquence* pour afficher une interaction. Une interaction est une séquence de messages entre des instances classiques de classes, de composants, de sous-systèmes ou d'acteurs.

 Les diagrammes de séquence UML font partie d'un modèle UML et ils existent uniquement dans des projets de modélisation UML. Pour créer un diagramme de séquence UML, dans le menu **architecture** , cliquez sur **nouveau diagramme UML ou diagramme de couche**. En général, vous trouverez plus d’informations sur les [éléments de diagramme de séquence UML](../modeling/uml-sequence-diagrams-reference.md) ou les [diagrammes de modélisation UML](../modeling/edit-uml-models-and-diagrams.md) . Pour une démonstration vidéo, consultez [esquisser des interactions à l’aide de diagrammes de séquence (2010)](https://channel9.msdn.com/Blogs/clinted/UML-with-VS-2010-Part-7-Sketching-Interactions-with-Sequence-Diagrams).

 Pour connaître les versions de Visual Studio qui prennent en charge cette fonctionnalité, consultez [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="in-this-topic"></a>Dans cette rubrique
 [Utilisation de diagrammes de séquence UML](#Using)

 [Étapes de base pour dessiner des diagrammes de séquence](#BasicSteps)

 [Création et utilisation de diagrammes de séquence simples](#Simple)

 [Classes et lignes de vie](#ClassesAndLifelines)

 [Création de séquences d'interaction réutilisables](#Multiple)

 [Réduction de groupes de lignes de vie](#Collapse)

 [Description de structures de contrôle avec des fragments](#Fragments)

## <a name="using-uml-sequence-diagrams"></a><a name="Using"></a> Utilisation de diagrammes de séquence UML
 Vous pouvez utiliser des diagrammes de séquence à diverses fins et à différents niveaux de détail du programme. Vous pouvez par exemple dessiner un diagramme de séquence dans les cas suivants :

- Si vous avez un diagramme de cas d'usage qui récapitule les utilisateurs de votre système et leurs objectifs, vous pouvez dessiner des diagrammes de séquence pour décrire comment les principaux composants du système interagissent pour remplir l'objectif de chaque cas d'usage. Pour plus d’informations, consultez [diagrammes de cas d’usage UML : indications](../modeling/uml-use-case-diagrams-guidelines.md).

- Si vous avez identifié des messages arrivant à une interface d'un composant, vous pouvez dessiner des diagrammes de séquence pour décrire comment les parties internes du composant interagissent pour obtenir le résultat nécessaire pour chaque message entrant. Pour plus d’informations, consultez [diagrammes de composants UML : indications](../modeling/uml-component-diagrams-guidelines.md).

  Les diagrammes de séquence présentent plusieurs avantages :

- Vous pouvez facilement voir comment les tâches sont réparties entre les composants.

- Vous pouvez identifier des modèles d'interaction qui rendent difficile la mise à jour du logiciel.

## <a name="relationship-to-other-diagrams"></a>Relation aux autres diagrammes
 Vous pouvez utiliser des diagrammes de séquence UML avec d'autres diagrammes de plusieurs façons.

#### <a name="lifelines-and-types"></a>Lignes de vie et types
 Les lignes de vie que vous dessinez dans un diagramme de séquence peuvent représenter des instances ordinaires des composants ou des classes de votre système. Vous pouvez créer des lignes de vie à partir de types, et inversement, et afficher les types dans des diagrammes de classes UML et des diagrammes de composants UML. Pour plus d’informations, consultez [classes et Lifeline](#ClassesAndLifelines).

#### <a name="parameter-types"></a>Types de paramètres
 Vous pouvez également décrire dans un diagramme de classes UML les types de paramètres et de valeurs retournées qui ont été utilisés dans les messages envoyés entre les lignes de vie.

#### <a name="use-case-details"></a>Détails de cas d'usage
 Un cas d'usage représente l'objectif d'un utilisateur, ainsi qu'une séquence d'étapes permettant d'atteindre cet objectif. La séquence d'étapes peut être décrite de plusieurs façons. Une option consiste à dessiner un diagramme de séquence qui montre les interactions entre les utilisateurs et les principaux composants du système. Pour plus d’informations, consultez [diagrammes de cas d’usage UML : indications](../modeling/uml-use-case-diagrams-guidelines.md).

## <a name="basic-steps-for-drawing-sequence-diagrams"></a><a name="BasicSteps"></a> Étapes de base pour le dessin de diagrammes de séquence
 Pour obtenir la liste complète des éléments des diagrammes de séquence, consultez [diagrammes de séquence UML : référence](../modeling/uml-sequence-diagrams-reference.md).

> [!NOTE]
> Les étapes détaillées de création des diagrammes de modélisation sont décrites dans modifier des [modèles et des diagrammes UML](../modeling/edit-uml-models-and-diagrams.md).

#### <a name="to-create-a-sequence-diagram"></a>Pour créer un diagramme de séquence

1. Dans le menu **architecture** , cliquez sur **nouveau diagramme UML ou diagramme de couche**.

2. Sous **modèles**, cliquez sur **diagramme de séquence UML**.

3. Nommez le diagramme.

4. Dans **Ajouter au projet de modélisation**, sélectionnez un projet de modélisation existant dans votre solution, ou **créez un nouveau projet de modélisation**, puis cliquez sur **OK**.

    Un nouveau diagramme de séquence apparaît avec la boîte à outils **diagramme de séquence** . La boîte à outils contient les éléments et connecteurs nécessaires.

   ![Parties d'un diagramme de séquence](../modeling/media/uml-sequence.png "UML_Sequence")

#### <a name="to-draw-a-sequence-diagram"></a>Pour dessiner un diagramme de séquence

1. Faites glisser les éléments de **vie** (1) de la **boîte à outils** vers le diagramme pour représenter les instances de classes, de composants, d’acteurs ou d’appareils.

    > [!NOTE]
    > Vous pouvez également créer une vie en faisant glisser une classe, une interface, un acteur ou un composant existant à partir de l' **Explorateur de modèles UML** vers le diagramme. Cette action crée une ligne de vie représentant une instance du type choisi.

2. Dessinez des messages pour montrer comment les lignes de vie collaborent pour atteindre un objectif spécifique.

     Pour créer un message (3, 4, 6, 7), cliquez sur un outil de message. Ensuite, cliquez sur la ligne de vie source au point d'où vous souhaitez que le message parte, puis cliquez sur la ligne de vie de destination.

     Une occurrence d'exécution (5) apparaît sur la ligne de vie de destination. L'occurrence d'exécution représente une période pendant laquelle l'instance exécute une méthode. Vous pouvez créer d'autres messages qui partent d'une occurrence d'exécution.

3. Pour afficher un message qui provient d'une source d'événement inconnue (9), ou qui diffuse à des destinataires inconnus (10), dessinez un message asynchrone depuis ou vers un espace vide sur le diagramme. Ces messages sont appelés *messages trouvés* (9) et *messages perdus* (10).

    > [!NOTE]
    > Pour déplacer un groupe de Lifeline qui ont perdu ou trouvé des messages, procédez comme suit pour sélectionner les clés de vie avant de les déplacer : dessinez un rectangle autour de ces dernières, ou appuyez sur la touche **CTRL** et maintenez-la enfoncée pendant que vous cliquez sur chaque vie. Si vous utilisez **Sélectionner tout** ou **CTRL** + **A** pour sélectionner toutes les Lifeline, puis les déplacer, les messages perdus ou trouvés attachés à ces dernières ne seront pas déplacés. Si ce scénario se produit, vous pouvez déplacer ces messages séparément.

4. Dessinez des diagrammes de séquence pour chaque message principal vers le même composant ou système.

#### <a name="to-change-the-order-of-messages"></a>Pour modifier l'ordre des messages

- Faites glisser un message vers le haut ou vers le bas dans sa ligne de vie. Vous pouvez le déplacer sur d'autres messages, ou dans ou hors d'un bloc d'exécution.

     \- ou -

- Cliquez sur le message et utilisez les flèches haut et **bas** pour ajuster les positions **des** messages. Utilisez les touches **MAJ + haut** et **Maj + Bas** pour modifier l’ordre des messages.

#### <a name="to-move-or-copy-message-sequences-on-the-sequence-diagram"></a>Pour déplacer ou copier des séquences de messages sur le diagramme de séquence

1. Cliquez avec le bouton droit sur un message (3, 4), puis cliquez sur **copier**.

2. Cliquez avec le bouton droit sur l’occurrence d’exécution (5) ou sur une vie (1) à partir de laquelle vous souhaitez envoyer le nouveau message, puis cliquez sur **coller**. Le nouvel expéditeur peut être sur un diagramme différent si vous le souhaitez.

     Une copie du message et de tous ses messages auxiliaires est ajoutée à la fin de l'occurrence d'exécution ou à la fin de la ligne de vie.

    > [!NOTE]
    > Le message collé apparaît toujours à la fin de l'occurrence d'exécution ou de la ligne de vie. Une fois que vous l'avez collé, vous pouvez le faire glisser jusqu'à une position antérieure.

#### <a name="to-display-and-edit-the-signature-text-for-a-message"></a>Pour afficher et modifier le texte de signature d'un message

- La ligne de vie cible doit être liée ou mappée à des types pour que le texte de la signature soit visible. Pour ce faire, effectuez l'une des étapes suivantes :

  - Cliquez avec le bouton droit sur la vie, puis choisissez **créer une classe**.

     -ou-

  - Sélectionnez la vie, appuyez sur **F4**, puis, dans la fenêtre **Propriétés** , définissez la propriété **type** sur un type existant ou spécifiez le nom d’un nouveau type. Cliquez avec le bouton droit sur l’étiquette du message, puis choisissez **créer une opération**.

    Le texte de la signature apparaît sous l'étiquette du message. Vous pouvez maintenant modifier le texte de la signature. Pour plus d’informations, consultez [classes et Lifeline](#ClassesAndLifelines).

#### <a name="to-improve-the-layout-of-a-sequence-diagram"></a>Pour améliorer la disposition d'un diagramme de séquence

- Cliquez avec le bouton droit sur une partie vide du diagramme, puis cliquez sur **réorganiser la disposition**.

- Pour annuler l’opération, cliquez sur **modifier**, puis sur **Annuler**.

#### <a name="to-change-the-package-that-owns-the-interaction"></a>Pour modifier le package propriétaire de l'interaction

1. Dans l' **Explorateur de modèles UML**, recherchez l’interaction affichée par le diagramme de séquence.

    > [!NOTE]
    > L’interaction n’apparaît pas dans l' **Explorateur de modèles UML** tant que vous n’avez pas ajouté la première vie au diagramme de séquence.

2. Faites glisser l'interaction vers le package.

     \- ou -

     Cliquez avec le bouton droit sur l’interaction, puis cliquez sur **couper**. Cliquez avec le bouton droit sur le package, puis cliquez sur **coller**.

## <a name="creating-and-using-simple-sequence-diagrams"></a><a name="Simple"></a> Création et utilisation de diagrammes de séquence simples
 La forme de diagramme de séquence la plus simple et la plus fréquente contient uniquement des lignes de vie et des messages. Un diagramme de ce type vous permet d'illustrer clairement une séquence typique d'interactions entre des objets dans votre conception ou entre votre système et ses utilisateurs. Cela suffit souvent à vous aider à discuter et à communiquer votre conception.

 Voici quelques éléments à prendre en compte quand vous dessinez un diagramme de séquence simple.

### <a name="types-of-message"></a>Types de messages
 Trois outils sont à votre disposition pour créer des messages.

- Utilisez l’outil **synchrone** pour décrire une interaction dans laquelle l’expéditeur attend que le destinataire renvoie une réponse (3).

     Une **<\<return>>** flèche s’affiche à la fin de l’occurrence d’exécution. Elle indique le retour du contrôle à l'expéditeur.

- Utilisez l’outil **asynchrone** pour décrire une interaction dans laquelle l’expéditeur peut continuer immédiatement sans attendre le récepteur (4).

- Utilisez l’outil **créer** pour décrire une interaction dans laquelle l’expéditeur crée le récepteur (8).

     Un message de création doit être le premier message reçu par le destinataire.

### <a name="annotating-the-interactions"></a>Annotation des interactions
 Pour décrire plus en détail la séquence, vous pouvez placer un **Commentaire** n’importe où sur le diagramme.

 À l’aide de **liens de commentaires**, vous pouvez lier un commentaire à des Lifeline, des exécutions, des utilisations d’interaction et des fragments.

> [!CAUTION]
> Quand vous souhaitez attacher un commentaire à un point particulier dans la séquence, liez-le à une occurrence d'exécution, une utilisation d'interaction ou un fragment. Ne le liez pas à une ligne de vie, car dans ce cas il ne reste pas attaché au point correct dans la séquence.

 Utilisez un commentaire pour :

- noter ce qui a été effectué à des points clés dans la séquence. Cela aide les lecteurs à voir les objectifs des interactions.

- décrire l'objectif global de l'intégralité de la séquence. Attachez le commentaire à l'occurrence d'exécution initiale ou laissez-le non attaché. Par exemple, « Le client a sélectionné des éléments dans le menu et un prix lui a été donné ».

- décrire les responsabilités de chaque ligne de vie. Attachez le commentaire à la ligne de vie. Par exemple, « Le Responsable des commandes recueille les choix du client dans le menu ».

- noter les exceptions ou alternatives qui peuvent être effectuées en guise d'alternative à la séquence typique illustrée. Par exemple « Le client peut choisir d'ignorer le reste de cette séquence ».

  - Vous pouvez utiliser des fragments comme alternative plus formelle à ce genre de remarque. Consultez [Description de structures de contrôle avec des fragments](#Fragments)

## <a name="deciding-the-scope-of-the-diagram"></a>Choix de la portée du diagramme
 Il est important d'identifier clairement ce que le diagramme est censé montrer.

#### <a name="initiating-event"></a>Événement de lancement
 Chaque diagramme doit montrer la séquence d'interactions qui résulte d'un événement de lancement. Par exemple :

- Un utilisateur initie un cas d'usage, par exemple l'ouverture de la page web pour l'achat d'un repas.

- Un message d'un composant système à un autre, par exemple l'interrogation de la disponibilité de certains articles qu'un client souhaite acheter.

- Un événement déclenché par un changement d'état, par exemple si la quantité en stock d'un article passe en dessous d'un seuil spécifique.

#### <a name="level-of-detail"></a>Niveau de détail
 Les diagrammes de séquence peuvent montrer différents niveaux de détail. Vous pouvez décider du niveau de détail dans deux dimensions distinctes presque indépendamment :

 Les lignes de vie peuvent représenter l'un des niveaux de détail suivants :

- Objets dans le code de programme, qui existe déjà ou que vous développez actuellement.

- Composants ou leurs sous-composants, généralement en omettant les façades, proxys et autres mécanismes de connexion.

- Votre système et les acteurs externes

  Les messages peuvent représenter l'un des niveaux de détail suivants :

- Messages logiciels dans le code de programme, à une API ou une interface web.

- Transactions ou sous-transactions, par exemple entre les utilisateurs et le système ou entre le code et la base de données.

- Cas d'usage : interactions majeures entre les utilisateurs et le système.

  Que vous exploriez du code existant ou que vous décriviez une nouvelle conception, il est souvent utile de dessiner et de discuter des vues les moins détaillées.

## <a name="describing-variations"></a>Description des variantes
 Le diagramme montre une séquence typique d'événements. Si vous souhaitez illustrer d'autres possibilités, telles que des scénarios de défaillance, vous pouvez adopter l'une des approches suivantes :

- Dessiner des diagrammes de séquence distincts pour décrire ces scénarios

- Utilisez la [Description de structures de contrôle avec des fragments](#Fragments) pour afficher des boucles, des alternatives, etc.

## <a name="assessing-the-design"></a>Évaluation de la conception
 Vous pouvez utiliser le diagramme pour évaluer la distribution des tâches entre ses objets ou composants. Une refactorisation peut être préférable si vous observez les modèles suivants :

- Une ligne de vie semble tout faire et effectuer des appels à tout le reste, tandis que les autres lignes de vie se contentent de répondre passivement.

- De nombreux messages coupent des lignes de vie. Chaque ligne de vie ne doit envoyer des messages qu'à quelques voisins et ne doit pas communiquer avec les voisins de ses voisins. Il est généralement possible de disposer les lignes de vie pour qu'il n'y ait que quelques endroits où les messages les croisent. Là où il y a des croisements, la ligne de vie cible ne doit pas non plus échanger des messages qui croisent les lignes de vie.

- Certaines lignes de vie semblent gérer plusieurs genres de tâches. Il doit être relativement facile de trouver une phrase succincte qui décrit les responsabilités de chaque ligne de vie et résume le travail qu'elle effectue en réponse à chaque message reçu.

## <a name="classes-and-lifelines"></a><a name="ClassesAndLifelines"></a> Classes et de la vie
 Les lignes de vie de vos diagrammes de séquence montrent des instances de classes ou d'interfaces de composants. Vous pouvez nommer une ligne de vie de deux manières :

|**Pour**|**Utiliser ce format**|
|--------------------------|-------------------------|
|Instance anonyme d'un type.<br /><br /> À utiliser si vous n'avez qu'une seule ligne de vie de chaque type.|*typeName*|
|Instance nommée d'un type.<br /><br /> À utiliser si vous souhaitez montrer une séquence qui implique plusieurs instances du même type.|*ObjectName*:*TypeName*|

### <a name="creating-lifelines-from-types"></a>Création de lignes de vie à partir de types
 Vous pouvez créer des lignes de vie à partir de classes que vous avez déjà définies, par exemple sur un diagramme de classes.

> [!NOTE]
> Assurez-vous qu'il existe déjà un diagramme de séquence avant d'effectuer cette tâche.

##### <a name="to-create-a-lifeline-from-an-existing-type"></a>Pour créer une ligne de vie à partir d'un type existant

- Faites glisser une classe, un composant ou une interface de l'Explorateur de modèles UML vers un diagramme de séquence.

   \- ou -

  1. Cliquez avec le bouton droit sur la classe, le composant ou l’interface dans son diagramme respectif, puis cliquez sur **créer la vie**.

  2. Dans la boîte de dialogue créer une zone de **vie** , sélectionnez un diagramme de séquence, puis cliquez sur **OK**.

     Une nouvelle ligne de vie d'instance nommée apparaît, dont le type est celui que vous avez fait glisser.

  > [!NOTE]
  > Vous pouvez répéter cette opération autant de fois que vous le souhaitez. Dans ce cas, vous créerez des lignes de vie avec différents noms d'instances.

##### <a name="to-change-the-type-of-a-lifeline"></a>Pour modifier le type d'une ligne de vie

1. Cliquez avec le bouton droit sur une vie, puis cliquez sur **Propriétés**.

2. Dans la fenêtre **Propriétés** , définissez la propriété **type** . Vous pouvez sélectionner un type dans le menu déroulant ou taper un nouveau nom.

### <a name="creating-classes-from-lifelines"></a>Création de classes à partir de lignes de vie
 Une fois que vous avez créé un ou plusieurs diagrammes de séquence, vous pouvez résumer les lignes de vie en créant des classes ou des interfaces à partir d'elles.

##### <a name="to-create-a-class-or-interface-from-a-lifeline"></a>Pour créer une classe ou une interface à partir d'une ligne de vie

1. Cliquez avec le bouton droit sur la vie, puis cliquez sur **créer une classe** ou **créer une interface**.

     Une nouvelle classe ou interface apparaît dans l'Explorateur de modèles UML.

2. Créez des opérations dans la classe ou l'interface pour chaque message reçu par la ligne de vie :

    1. Sélectionnez tous les messages que vous souhaitez inclure.

    2. Cliquez avec le bouton droit sur l’un des messages, puis cliquez sur **créer une méthode**.

         La nouvelle classe ou interface a des opérations pour chaque message sélectionné.

         Le nom de l’opération apparaît sous chaque flèche de message et dans la propriété **opération** du message.

         Si votre message comportait des paramètres au format « (paramètre : type) », ils apparaîtront dans la liste des paramètres de la nouvelle opération.

        > [!NOTE]
        > Vous devez répéter cette étape si vous ajoutez de nouveaux messages sur le diagramme de séquence.

3. Pour afficher la nouvelle classe ou interface en détail, vous devez l'ajouter à un diagramme de classes ou de composant.

    1. Ouvrez ou créez un diagramme de classes ou de composant.

    2. Faites glisser la nouvelle classe ou interface de l **'Explorateur de modèles UML** vers un diagramme de classes.

         La classe ou l'interface apparaît sur le diagramme de classes.

         \- ou -

    3. Faites glisser la nouvelle interface depuis l' **Explorateur de modèles UML** vers un composant ou un port dans un diagramme de composant.

         L'interface apparaît sur le composant sous forme d'interface Lollipop.

### <a name="creating-classes-for-parameters"></a>Création de classes pour des paramètres
 Vous pouvez inclure des paramètres dans les messages sur un diagramme de séquence. Vous pouvez utiliser un diagramme de classes UML pour décrire les types de paramètres.

## <a name="creating-reusable-interaction-sequences"></a><a name="Multiple"></a> Création de séquences d’interaction réutilisables
 Vous pouvez utiliser un diagramme distinct pour décrire une séquence qui contient des détails que vous souhaitez séparer ou qui est commune à plusieurs diagrammes.

 Vous pouvez créer un rectangle Utilisation d'interaction (12) sur un diagramme qui pointe vers les détails sur un autre diagramme.

 Double-cliquez sur une Utilisation d'interaction pour ouvrir le diagramme de séquence associé.

#### <a name="to-create-a-reusable-interaction-sequence-from-existing-lifelines"></a>Pour créer une séquence d'interaction réutilisable à partir de lignes de vie existantes

1. Dans la **boîte à outils**, cliquez sur **utilisation d’interaction**.

2. Sur le diagramme de séquence, maintenez le bouton de la souris enfoncé tout en faisant glisser les lignes de vie que vous souhaitez inclure dans la séquence réutilisable. Démarrez à la position verticale où vous souhaitez insérer l'utilisation d'interaction.

     Une utilisation d'interaction apparaît sur les lignes de vie sélectionnées sur le diagramme de séquence.

3. Double-cliquez sur le nom de l'utilisation d'interaction et modifiez-le pour décrire l'effet de la séquence réutilisable sur ce diagramme.

     \- ou -

     Écrivez le nom comme un appel de fonction, avec des paramètres.

4. Liez l'utilisation d'interaction à un autre diagramme de séquence. Cliquez avec le bouton droit sur l'utilisation d'interaction, puis :

     Cliquez sur **créer une nouvelle séquence** pour créer un diagramme de séquence

     \- ou -

     Cliquez sur **lier à la séquence** pour créer un lien vers un diagramme existant.

     Visual Studio crée un lien entre l'utilisation d'interaction et la nouvelle séquence d'interaction.

     Un nouveau diagramme de séquence apparaît dans votre solution. Il contient les lignes de vie que vous avez utilisées pour créer l'utilisation d'interaction.

    > [!NOTE]
    > Seules les lignes de vie que vous avez utilisées pour créer l'utilisation d'interaction seront incluses. Le nouveau diagramme n'inclura pas les lignes de vie que vous avez créées après l'utilisation d'interaction, même celle-ci les couvre maintenant.

#### <a name="to-create-a-reusable-sequence-from-existing-messages"></a>Pour créer une séquence réutilisable à partir de messages existants

- Cliquez avec le bouton droit sur le message que vous souhaitez déplacer, puis cliquez sur **déplacer vers le diagramme**.

  Visual Studio :

  - remplace par une utilisation d'interaction le message sélectionné et tous les messages auxiliaires ;

  - déplace les messages remplacés vers un nouveau diagramme de séquence ;

  - crée un lien entre l'utilisation d'interaction et le nouveau diagramme de séquence.

#### <a name="to-navigate-to-the-sequence-referenced-by-an-interaction-use"></a>Pour accéder à la séquence référencée par une utilisation d'interaction

- Double-cliquez sur l'utilisation d'interaction.

     \- ou -

     Cliquez avec le bouton droit sur l’utilisation d’interaction, puis cliquez sur **atteindre la séquence**.

### <a name="creating-a-placeholder-with-an-interaction-use"></a>Création d'un espace réservé avec une utilisation d'interaction
 Vous pouvez créer une utilisation d'interaction sans la lier à un autre diagramme. Vous pouvez l’utiliser comme espace réservé pour une partie de la séquence dont les détails ne sont pas encore utilisés. Utilisez le nom de l’utilisation de l’interaction pour indiquer le résultat souhaité.

## <a name="collapsing-groups-of-lifelines"></a><a name="Collapse"></a> Réduction des groupes de la vie
 Vous pouvez réduire un ensemble de lignes de vie pour que le groupe apparaisse comme une ligne de vie unique. Cela vous aide à visualiser un groupe d'objets en tant que composant unique. Les messages et les utilisations d'interaction entre les lignes de vie d'un groupe réduit sont masqués. Les messages et les séquences d'interaction qui comprennent d'autres lignes de vie sont affichés.

#### <a name="to-collapse-a-group-of-lifelines-together"></a>Pour réduire un groupe de lignes de vie ensemble

1. Sélectionnez plusieurs lignes de vie.

2. Cliquez avec le bouton droit sur l’un d’eux, puis cliquez sur **réduire**.

     Les lignes de vie distinctes sont remplacées par une seule ligne de vie.

     Les messages et les utilisations d'interactions qui impliquent uniquement des membres du groupe sont masqués.

3. Pour renommer le groupe, cliquez sur le nom.

    > [!NOTE]
    > Le nom du groupe est perdu quand vous développez le groupe.

#### <a name="to-expand-a-collapsed-group"></a>Pour développer un groupe réduit

- Cliquez avec le bouton droit sur la vie réduite, puis cliquez sur **développer**.

    > [!NOTE]
    > Le nom du groupe est perdu, ainsi que tous les liens qui vont du groupe à des commentaires ou des éléments de travail.

## <a name="describing-control-structures-with-fragments"></a><a name="Fragments"></a> Description de structures de contrôle avec des fragments
 Vous pouvez utiliser des fragments combinés (13) pour définir des boucles, des branches et un traitement simultané dans un diagramme de séquence. Vous pouvez également, à la place, utiliser un diagramme d'activités. Le diagramme d'activités n'est pas aussi utile pour l'affichage des messages entre les acteurs, mais dans certains cas il est plus performant pour l'affichage des boucles, des branches et de l'accès concurrentiel.

 Pour obtenir la liste complète des types de fragments, consultez [décrire le contrôle du workflow avec des fragments dans les diagrammes de séquence UML](../modeling/describe-control-flow-with-fragments-on-uml-sequence-diagrams.md).

#### <a name="to-create-a-combined-fragment"></a>Pour créer un fragment combiné

1. Sélectionnez un message ou une séquence de messages commençant tous sur la même ligne de vie ou occurrence d'exécution.

    > [!NOTE]
    > Sélectionnez les flèches de messages, et non les occurrences d'exécution vers lesquelles pointent les messages.

2. Cliquez avec le bouton droit sur l’un des messages, pointez sur **entourer**de, puis cliquez sur le type de fragment dont vous avez besoin.

     Un nouveau fragment apparaît. Il contient les messages que vous avez sélectionnés.

     Si le type de fragment combiné autorise plusieurs fragments, un fragment vide apparaît également.

3. Pour définir la protection d’un fragment, cliquez avec le bouton droit sur la bordure du fragment, puis cliquez sur **Propriétés**. Définissez la propriété **Guard** .

     La garde sert à définir la condition pour une branche ou une boucle.

4. Pour ajouter un nouveau fragment à un type qui autorise plusieurs fragments, cliquez avec le bouton droit sur la limite d’un fragment, puis pointez sur **Ajouter**. Cliquez sur opérande d' **interaction avant** ou **opérande d’interaction après**.

5. Pour ajouter de nouveaux messages à un fragment, utilisez les outils de message ou copiez et collez.

## <a name="see-also"></a>Voir aussi
 [Diagrammes de séquence UML : référence](../modeling/uml-sequence-diagrams-reference.md) [modifier les modèles UML et les diagrammes](../modeling/edit-uml-models-and-diagrams.md) [diagrammes de cas d’usage UML : référence](../modeling/uml-use-case-diagrams-reference.md) diagrammes de [classes UML : référence](../modeling/uml-class-diagrams-reference.md) [diagrammes de composants UML : référence](../modeling/uml-component-diagrams-reference.md) [diagrammes de composants UML](../modeling/uml-component-diagrams-reference.md) : référence [vidéo : esquisser des interactions à l’aide de diagrammes de séquence](https://channel9.msdn.com/posts/clinted/UML-with-VS-2010-Part-2-Organizing-Features-Into-Use-Cases)
