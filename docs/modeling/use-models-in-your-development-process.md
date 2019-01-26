---
title: Utiliser des modèles dans votre processus de développement
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- UML, using models
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 123d34383f1dace7d7c6d12d41bfc1122ae521c7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55071083"
---
# <a name="use-models-in-your-development-process"></a>Utiliser des modèles dans votre processus de développement

Dans Visual Studio, vous pouvez utiliser un modèle pour vous aider à comprendre et à modifier un système, une application ou un composant. Un modèle peut vous aider à visualiser le monde dans lequel votre système fonctionne, à clarifier les besoins des utilisateurs, à définir l'architecture de votre système, à analyser le code et à vous assurer qu'il répond aux impératifs. Consultez [vidéo Channel 9 : Améliorer l’architecture via la modélisation](http://go.microsoft.com/fwlink/?LinkID=252078).

Pour connaître les versions de Visual Studio qui prennent en charge chaque type de modèle, consultez [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

Les modèles peuvent vous aider de plusieurs façons :

- Dessiner des diagrammes de modélisation vous aide à clarifier les concepts liés aux spécifications, à l'architecture et à la conception de haut niveau. Pour plus d’informations, consultez [modéliser les besoins de l’utilisateur](../modeling/model-user-requirements.md).

- L'utilisation de modèles peut vous aider à exposer des incohérences dans les spécifications.

- Communiquer avec des modèles vous permet de communiquer des concepts importants avec moins d'ambiguïté qu'avec un langage naturel. Pour plus d’informations, consultez [modèle d’architecture de votre application](../modeling/model-your-app-s-architecture.md).

- Vous pouvez parfois utiliser des modèles pour générer du code ou d'autres artefacts tels que des schémas de bases de données ou des documents. Par exemple, les composants de modélisation de Visual Studio sont générées à partir d’un modèle. Pour plus d’informations, consultez [générer et configurer votre application à partir de modèles](../modeling/generate-and-configure-your-app-from-models.md).

Vous pouvez utiliser des modèles dans une large gamme de processus, de l'extrême agilité à la haute cérémonie.

## <a name="use-models-to-reduce-ambiguity"></a>Utiliser des modèles pour réduire l’ambiguïté

Le langage de modélisation est moins ambigu que le langage naturel et il est conçu pour exprimer les idées généralement requises lors du développement de logiciels.

Si votre projet comporte une petite équipe qui adhère à des pratiques agiles, vous pouvez utiliser des modèles pour vous aider à clarifier les récits utilisateur. Lors des discussions avec les clients concernant leurs besoins, la création d'un modèle peut générer des questions utiles beaucoup plus rapidement, et sur une étendue plus large du produit, que l'écriture de code de prototype.

Si votre projet est volumineux et comprend des équipes à différents endroits du globe, vous pouvez utiliser des modèles pour aider à communiquer les impératifs et l'architecture beaucoup plus efficacement qu'avec du texte brut.

Dans les deux cas, la création d'un modèle entraîne presque toujours une réduction significative des incohérences et des ambiguïtés. Les différentes parties prenantes ont fréquemment une vue différente du monde dans lequel fonctionne le système, et les différents développeurs ont fréquemment une vue différente du fonctionnement du système. Le recours à un modèle comme focus d'une discussion expose généralement ces différences. Pour plus d’informations sur la façon d’utiliser un modèle pour réduire les incohérences, consultez [modéliser les besoins de l’utilisateur](../modeling/model-user-requirements.md).

## <a name="use-models-with-other-artifacts"></a>Utiliser des modèles avec d’autres artefacts

Un modèle n'est pas en soi une architecture ou une spécification de configuration. C'est un outil qui permet d'exprimer plus clairement certains aspects de ces choses, mais les concepts impliqués dans la conception de logiciel ne peuvent pas tous être exprimés. Les modèles doivent donc être utilisés avec d’autres moyens de communication, tels que des éléments de travail des pages ou des paragraphes, les documents Microsoft Office OneNote dans Team Foundation ou des pense-bêtes sur le mur de salle de projet. Mis à part ce dernier élément, tous ces types d'objets peuvent être liés aux parties des éléments du modèle.

Voici d'autres aspects de spécification qui sont couramment utilisés avec les modèles. Selon l'échelle et le style de votre projet, vous pourriez utiliser plusieurs de ces aspects ou aucun d'entre eux :

- Récits utilisateur. Un récit utilisateur est une courte description, discutée avec les utilisateurs et les autres parties prenantes, d'un aspect du comportement du système qui sera livré lors de l'une des itérations du projet. Un récit utilisateur typique commence « le client sera en mesure de... » Un récit utilisateur peut présenter un groupe de cas d'usage ou définir des extensions de cas d'usage qui ont été développées précédemment. La définition ou l'extension des cas d'usage aide à clarifier le récit utilisateur.

- Demandes de modification. Une demande de modification dans un projet plus formel est très similaire à un récit utilisateur dans un projet agile. L'approche agile traite toutes les spécifications comme des modifications de ce qui a été développé lors des itérations précédentes.

- Description de cas d'usage. Un cas d'usage représente une façon par laquelle un utilisateur interagit avec le système pour atteindre un objectif particulier. Une description complète comprend l'objectif, les séquences d'événements principales et alternatives, ainsi que les résultats exceptionnels. Un diagramme de cas d'usage aide à résumer et à fournir une vue d'ensemble des cas d'usage.

- Scénarios. Un scénario est une description assez détaillée d'une séquence d'événements indiquant comment le système, les utilisateurs et les autres systèmes coopèrent pour fournir une valeur aux parties prenantes. Il peut prendre la forme d'un diaporama de l'interface utilisateur ou d'un prototype de l'interface utilisateur. Il peut décrire un cas d'usage ou d'une séquence de cas d'usage.

- Glossaire. Le glossaire de spécifications du projet décrit les mots avec lesquels les clients discutent de leur environnement. Les modèles d'impératifs et d'interface utilisateur doivent également utiliser ces termes. Un diagramme de classes peut aider à clarifier les relations entre la plupart de ces termes. La création des diagrammes et du glossaire réduit non seulement les malentendus entre les utilisateurs et les développeurs, mais expose également presque toujours les malentendus entre les différentes parties prenantes.

- Règles métier. Vous pouvez exprimer de nombreuses règles métier en tant que contraintes invariantes sur les associations et les attributs dans le modèle de classes de spécifications et en tant que contraintes sur les diagrammes de séquence.

- Conception de haut niveau. Décrit les principales parties et comment elles s'emboîtent les unes aux autres. Les diagrammes de composant, de séquence et d'interface constituent une partie importante d'une conception de haut niveau.

- Modèles de conception. Décrivent les règles de conception qui sont partagées entre les différentes parties du système.

- Spécifications de tests. Les scripts de tests et les conceptions du code de test peuvent faire bon usage des diagrammes d'activités et de séquence pour décrire des séquences d'étapes de tests. Les tests système doivent être exprimés selon les termes du modèle d'impératifs, pour que vous puissiez facilement les modifier en cas de modification des impératifs.

- Plan de projet. Le plan de projet ou backlog définit quand chaque fonctionnalité sera délivrée. Vous pouvez définir chaque fonctionnalité en déclarant quels cas d'usage et règles métier elle implémente ou étend. Vous pouvez soit faire référence aux cas d'usage et aux règles métier directement dans le plan, soit définir un ensemble de fonctionnalités dans un document séparé et utiliser les titres des fonctionnalités dans le plan.

## <a name="use-models-in-iteration-planning"></a>Utiliser des modèles dans la planification de l’itération

Bien que tous les projets soient différents en termes d'échelle et d'organisation, un projet typique est planifié comme une série d'itérations qui dure entre deux et six semaines. Il est important de planifier suffisamment d'itérations pour que les commentaires issus des premières itérations puissent être utilisés pour ajuster l'étendue et les plans des itérations ultérieures.

Les suggestions suivantes peuvent vous aider à tirer parti des avantages offerts par la modélisation dans un projet itératif.

### <a name="sharpen-focus-as-each-iteration-approaches"></a>Affinez le focus à l’approche de chaque itération.

À l'approche de chaque itération, utilisez des modèles pour vous aider à définir ce qui doit être livré à la fin de l'itération.

- Ne modélisez pas tout en détail lors des premières itérations. Lors de la première itération, créez un diagramme de classes pour les principaux éléments du glossaire utilisateur, dessinez un diagramme des principaux cas d'usage et dessinez un diagramme des principaux composants. Ne décrivez pas ces éléments de manière très détaillée, car les détails changeront lors des phases ultérieures du projet. Utilisez les termes définis dans ce modèle pour créer une liste de fonctionnalités ou de récits utilisateur importants. Assignez les fonctionnalités aux itérations pour équilibrer approximativement la charge de travail estimée tout au long du projet. Ces assignations changeront durant les phases ultérieures du projet.

- Essayez d'implémenter des versions simplifiées de tous les scénarios d'usage les plus importants lors de l'une des premières itérations. Étendez ces cas d'usage lors des itérations ultérieures. Cette approche permet de réduire le risque de découverte d'un défaut dans les spécifications ou l'architecture trop tard dans le projet.

- À l'approche de la fin de chaque itération, organisez un atelier de spécifications pour définir en détail les spécifications ou les récits utilisateur qui seront développés dans l'itération suivante. Invitez les utilisateurs et les parties prenantes qui peuvent décider des priorités, ainsi que les développeurs et les testeurs système. Trois heures seront généralement nécessaires pour définir les spécifications pour une itération de deux semaines.

- L'objectif de cet atelier est que tout le monde s'entende sur ce qui doit être accompli à la fin de l'itération suivante. Utilisez des modèles comme outil pour aider à clarifier les spécifications. La sortie de l’atelier est un backlog d’itération : autrement dit, une liste de tâches de développement dans les suites de test et de Team Foundation dans [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)].

- Lors de l'atelier de spécifications, discutez de la conception  uniquement dans le cadre de la détermination des estimations pour les tâches de développement. Autrement, ne discutez que du comportement du système avec lequel les utilisateurs auront une interaction directe. Séparez le modèle d'impératifs du modèle d'architecture.

- Les parties prenantes non-techniques n'auront généralement aucun problème pour comprendre les diagrammes UML, avec quelques conseils de votre part.

### <a name="link-model-to-work-items"></a>Lier le modèle aux éléments de travail

Après l'atelier de spécifications, élaborez les détails du modèle d'impératifs et liez le modèle à des tâches de développement. Pour cela, en liant des éléments de travail dans Team Foundation pour les éléments dans le modèle.

Vous pouvez lier n'importe quel élément à des éléments de travail, mais les éléments les plus utiles sont les suivants :

- Commentaires décrivant les règles métier ou les impératifs de qualité de service. Pour plus d’informations, consultez [modéliser les besoins de l’utilisateur](../modeling/model-user-requirements.md).

### <a name="link-model-to-tests"></a>Lier le modèle aux tests

Utilisez le modèle d'impératifs pour guider la conception des tests d'acceptation. Créez ces tests en même temps que le travail de développement.

Pour en savoir plus sur cette technique, consultez [développer des tests à partir d’un modèle de](../modeling/develop-tests-from-a-model.md).

### <a name="estimate-remaining-work"></a>Estimer le travail restant

Un modèle d'impératifs peut aider à estimer la taille totale du projet par rapport à la taille de chaque itération. L'évaluation du nombre et de la complexité des cas d'usage et des classes peut vous aider à estimer le travail de développement nécessaire. Une fois les premières itérations terminées, une comparaison des spécifications couvertes et de celles restant à couvrir peut donner une mesure approximative du coût et de la portée du reste du projet.

À l'approche de la fin de chaque itération, passez en revue l'assignation des spécifications aux itérations ultérieures. Il peut être utile de représenter l'état de votre logiciel à la fin de chaque itération comme sous-système dans un diagramme de cas d'usage. Lors de vos discussions, vous pouvez déplacer des cas d'usage et des extensions de cas d'usage de l'un de ces sous-systèmes vers un autre.

## <a name="levels-of-abstraction"></a>Niveaux d'abstraction

Les modèles ont une plage d'abstraction par rapport au logiciel. Les modèles les plus concrets représentent directement le code de programme et les modèles les plus abstraits représentent des concepts métier qui peuvent être représentés ou non dans le code.

Vous pouvez visualiser un modèle via plusieurs genres de diagrammes. Pour plus d’informations sur les modèles et les diagrammes, voir [création de modèles pour votre application](../modeling/create-models-for-your-app.md).

Différents genres de diagrammes sont utiles pour décrire la conception à différents niveaux d'abstraction. La plupart des types de diagrammes sont utiles à plusieurs niveaux. Le tableau ci-dessous montre comment chaque type de diagramme peut être utilisé.

|Niveau de conception|Types de diagrammes|
|-|-|
|Processus d'entreprise<br /><br /> Comprendre le contexte dans lequel votre système sera utilisé vous aide à comprendre les besoins des utilisateurs.|-Diagrammes de classes conceptuels décrivent les concepts d’entreprise utilisés dans le processus de l’entreprise.|
|Besoins des utilisateurs<br /><br /> Définition de ce que votre système doit apporter aux utilisateurs.|-Les règles d’entreprise et qualité de service peuvent être décrits dans des documents séparés.|
|Conception de haut niveau<br /><br /> Structure globale du système : composants principaux et comment ils s'imbriquent les uns aux autres.|-Les diagrammes de dépendance décrivent la façon dont le système est structuré en parties interdépendantes. Vous pouvez valider le code de programme par rapport aux diagrammes de dépendance à vérifier qu’il adhère à l’architecture.|
|Analyse du code<br /><br /> Diagrammes peuvent être générés à partir du code.|-Diagrammes de dépendance affichent les dépendances entre les classes. Code de mise à jour peut être validé par rapport à un diagramme de la dépendance.<br />-Les diagrammes de classes affichent les classes dans le code.|

## <a name="external-resources"></a>Ressources externes

|**Catégorie**|**Liens**|
|-|-|
|**Vidéos**|![lien vers la vidéo](../data-tools/media/playvideo.gif) [MSDN vidéos de procédure : Comment créer et utiliser des modèles UML et diagrammes (Visual Studio 2010 Ultimate)](http://go.microsoft.com/fwlink/?LinkId=214460)<br /><br /> ![lien vers la vidéo](../data-tools/media/playvideo.gif) [Channel 9 : UML avec Visual Studio 2010](http://go.microsoft.com/fwlink/?LinkID=201106)<br /><br /> ![lien vers la vidéo](../data-tools/media/playvideo.gif) [série MSDN Comment faire : Outils UML et extensibilité (Visual Studio 2010 Ultimate)](http://go.microsoft.com/fwlink/?LinkID=214467)|
|**Forums**|- [Outils de visualisation et de modélisation Visual Studio](http://go.microsoft.com/fwlink/?LinkId=184720)<br />- [Kit de développement logiciel (SDK) Visual Studio Visualization and Modeling (outils DSL)](http://go.microsoft.com/fwlink/?LinkId=184721)|
|**Blogs**|[Microsoft DevOps](https://blogs.msdn.microsoft.com/devops/)|
|**Articles et journaux techniques**|[Centre d’architecture MSDN](http://go.microsoft.com/fwlink/?LinkId=201343)<br /><br /> [Guide des outils d’architecture Visual Studio](../modeling/visual-studio-architecture-tooling-guidance.md)|

## <a name="see-also"></a>Voir aussi

- [Utiliser des modèles dans le développement Agile](https://msdn.microsoft.com/592ac27c-3d3e-454a-9c38-b76658ed137f)
- [Créer des modèles pour votre application](../modeling/create-models-for-your-app.md)
- [Modéliser les besoins des utilisateurs](../modeling/model-user-requirements.md)
- [Modéliser l’architecture de votre application](../modeling/model-your-app-s-architecture.md)
- [Développer des tests à partir d’un modèle](../modeling/develop-tests-from-a-model.md)
- [Structurer votre solution de modélisation](../modeling/structure-your-modeling-solution.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
