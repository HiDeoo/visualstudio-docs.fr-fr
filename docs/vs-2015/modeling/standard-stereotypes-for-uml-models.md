---
title: Stéréotypes standard pour les modèles UML | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML, stereotypes
- UML diagrams, stereotypes
ms.assetid: 8a8c2321-1cae-4ba8-bb9e-23495c3404d8
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a16c68b3b14be57fb0a6a45c740e5420a82c2ddf
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72661049"
---
# <a name="standard-stereotypes-for-uml-models"></a>Stéréotypes standard pour les modèles UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez ajouter des stéréotypes à des éléments de modèle UML pour fournir des informations supplémentaires au lecteur ou pour un traitement informatique. Les stéréotypes sont définis dans les profils et chaque profil fournit un ensemble de stéréotypes. Plusieurs profils sont fournis avec Visual Studio. Vous pouvez également définir vos propres profils, qui peuvent contenir vos propres stéréotypes. Pour plus d’informations, consultez [définir un profil pour étendre UML](../modeling/define-a-profile-to-extend-uml.md).

 Pour connaître les versions de Visual Studio qui prennent en charge cette fonctionnalité, consultez [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="the-standard-profiles"></a>Profils standard
 Les profils suivants sont disponibles dans une édition prise en charge de Visual Studio dès que vous l'avez installée.

|Profil|Objectif|
|-------------|-------------|
|[Profil standard L2](#L2)|Ensemble standard de stéréotypes qui peuvent servir à ajouter des informations supplémentaires concernant un élément ou une relation.|
|[Profil standard L3](#L3)|Ensemble standard de stéréotypes qui peuvent servir à ajouter des informations supplémentaires concernant un élément ou une relation.|
|[Profil C#](#NetProfile)|Si vous prévoyez qu'une classe ou un autre élément dans un modèle UML représente du code de programme, vous pouvez l'indiquer en appliquant l'un des stéréotypes du profil C#.<br /><br /> Ces stéréotypes ajoutent également des propriétés aux éléments de modèle.|

 Lorsque vous créez un modèle UML, les profils standard UML L2 et L3 sont liés au modèle, sauf si vous supprimez les liens.

 Pour utiliser les stéréotypes de chacun de ces profils, vous devez d'abord lier le profil à un package ou à un modèle qui contient les éléments auxquels vous souhaitez les appliquer.

#### <a name="to-link-a-profile-to-a-model-or-a-package"></a>Pour lier un profil à un modèle ou à un package

1. Ouvrez l' **Explorateur de modèles UML**. Dans le menu **architecture** , pointez sur **fenêtres**, puis cliquez sur **Explorateur de modèles UML**.

2. Recherchez un package ou un modèle qui contient tous les éléments auxquels vous souhaitez appliquer les stéréotypes dans le profil.

3. Cliquez avec le bouton droit sur le package ou le modèle, puis cliquez sur **Propriétés**.

4. Dans la fenêtre **Propriétés** , définissez la propriété **profils** sur les profils de votre choix.

#### <a name="to-remove-the-link-between-a-profile-and-a-model-or-package"></a>Pour supprimer le lien entre un profil et un modèle ou un package

1. Dans l’Explorateur de modèles UML, cliquez avec le bouton droit sur le modèle ou le package, puis cliquez sur **Propriétés**.

2. Dans la Fenêtre Propriétés, définissez la propriété **profils** sur vide.

    > [!NOTE]
    > Vous pouvez dissocier un profil uniquement si aucun des éléments du modèle ou du package n'utilise les stéréotypes de ce profil.

#### <a name="to-apply-a-stereotype-to-a-model-element"></a>Pour appliquer un stéréotype à un élément de modèle

1. Cliquez avec le bouton droit sur l’élément de modèle dans un diagramme ou dans l' **Explorateur de modèles UML**, puis cliquez sur **Propriétés**.

2. Cliquez sur la propriété **stéréotypes** et sélectionnez les stéréotypes que vous souhaitez appliquer.

     Les stéréotypes sélectionnés sont affichés entre « chevrons » dans l'élément de modèle pour la plupart des types d'éléments.

    > [!NOTE]
    > Si vous ne voyez pas la propriété **stéréotypes** , ou si le stéréotype souhaité n’apparaît pas, vérifiez que l’élément de modèle est à l’intérieur d’un package ou d’un modèle auquel le profil approprié a été lié.

3. Certains stéréotypes vous permettent de définir les valeurs de propriétés supplémentaires pour l'élément de modèle. Pour afficher ces propriétés, développez la propriété **stéréotypes** .

### <a name="uml-standard-profile-l2"></a><a name="L2"></a> Profil standard L2 UML
 Vous pouvez utiliser les stéréotypes suivants pour préciser la signification des éléments de modèle UML, à moins que le lien vers le profil n'ait été supprimé du modèle.

 La signification exacte de ces stéréotypes est déterminée par vos propres conventions locales et par les outils que vous pouvez utiliser pour traiter le modèle.

|Stereotype|S’applique à|Signification|
|----------------|----------------|-------------|
|auxiliary|Classe|Classe qui prend en charge une autre classe, en général en implémentant une logique supplémentaire. L'autre classe peut avoir le stéréotype « focus ».|
|appel|Dépendance|La classe cliente appelle les opérations du fournisseur.|
|create|Dépendance|La classe cliente crée des instances du fournisseur.|
|create|Message|L'expéditeur crée le destinataire.|
|create|Opération|Cette opération est un constructeur.|
|derive|Dépendance|L'élément client est calculé intégralement ou partiellement à partir du fournisseur.|
|destroy|Opération|L'opération détruit son instance.|
|document|Artefact|« file » qui est pas une source ou un fichier exécutable.|
|entité|Composant|Le composant représente un concept métier.|
|executable|Artefact|« file » exécutable.|
|fichier|Artefact|Fichier physique.|
|focus|Classe|Classe définissant la logique d'entreprise, qui est prise en charge par plusieurs classes « auxiliary ».|
|framework|Package|Ce package définit un modèle de design réutilisable.|
|implement|Composant|Implémentation d'une « specification ».|
|implementationClass|Classe|La classe décrit une implémentation et chaque instance d'exécution a une classe d'implémentation fixe. Contraste avec « type ».|
|instantiate|Dépendance|Le client crée des instances du fournisseur.|
|bibliothèque|Artefact|« file » de bibliothèque.|
|metaclass|Classe|Les instances de cette classe sont également des classes.|
|modelLibrary|Package|Contient des éléments de modèle censés être réutilisés en important des packages. Défini en général dans le cadre d'un profil et importé automatiquement par l'application du profil.|
|processus|Composant|Composant basé sur une transaction, ou qui transporte un thread.|
|realization|Classe, Interface, Composant|Décrit une implémentation.|
|refine|Dépendance|La classe, le composant ou le package client fournit plus d'informations sur la spécification ou la conception que le fournisseur.|
|responsibility|Dépendance|Le commentaire à l'extrémité fournisseur de la dépendance définit les responsabilités du composant ou de la classe cliente.|
|script|Artefact|« file » interprétable.|
|Envoyer|Dépendance|L'opération source envoie le signal cible.|
|service|Composant|Composant sans état.|
|source|Artefact|« file » compilable.|
|specification|Classe, Interface, Composant|Définit le comportement d'un composant ou d'un objet sans définir son fonctionnement en interne.|
|subsystem|Composant|Partie d'un grand système. Un sous-système sur un diagramme de cas d'usage est un composant avec le stéréotype subsystem.|
|trace|Dépendance|L'élément client fait partie de la conception qui réalise le fournisseur. Les deux extrémités de cette dépendance sont généralement dans des modèles différents. L'un de ces modèles est une réalisation de l'autre.|
|type|Classe|Spécifie le comportement d'un objet sans déclarer comment il est implémenté. Un objet est un membre d'un type s'il est conforme à la spécification.|
|service|Classe|Collection de fonctions statiques. La classe n'a pas d'instances.|

### <a name="uml-standard-profile-l3"></a><a name="L3"></a> Profil standard L3 UML
 Vous pouvez utiliser les stéréotypes suivants pour préciser la signification des éléments de modèle UML, à moins que le profil n'ait été dissocié du modèle.

 La signification exacte de ces stéréotypes est déterminée par vos propres conventions locales et par les outils que vous pouvez utiliser pour traiter le modèle.

|Stereotype|S’applique à|Description|
|----------------|----------------|-----------------|
|buildComponent|Composant|Collection d'éléments utilisés pour définir une build.|
|metaModel|Modèle|Définit un langage de modélisation tel qu'une variante d'UML ou un langage spécifique à un domaine.|
|systemModel|Modèle|Modèle qui est une collection de modèles qui s'appliquent au même système, par exemple une spécification, une réalisation et des relations de suivi entre elles.|

## <a name="c-profile"></a><a name="NetProfile"></a> Profil C#
 Les stéréotypes définis dans ce profil vous permettent d'indiquer qu'un élément de modèle est destiné à une traduction en code de programme. Chaque stéréotype définit des propriétés supplémentaires que vous pouvez définir sur l'élément de modèle.

 Pour rendre ces stéréotypes disponibles, liez un modèle ou un package au profil C#. Vous pouvez ensuite appliquer les stéréotypes à des éléments de modèle dans ce modèle ou ce package.

 Les stéréotypes disponibles, les éléments auxquels ils s'appliquent et les propriétés supplémentaires qu'ils rendent disponibles sont résumées dans le tableau suivant.

|Stereotype|S’applique à|Propriétés|
|----------------|----------------|----------------|
|**Classe C#**|Classe UML<br /><br /> Composant|**Attributs CLR**<br /><br /> **Is Partial**<br /><br /> **Est sealed**<br /><br /> **Est statique**<br /><br /> **Is Unsafe**<br /><br /> **Visibilité du package**|
|**C# struct**|Classe UML<br /><br /> Composant|**Attributs CLR**<br /><br /> **Is Partial**<br /><br /> **Is Unsafe**<br /><br /> **Visibilité du package**|
|**C# global members**|Classe UML<br /><br /> Composant|**Attributs CLR**|
|**Interface C#**|Interface UML|**Attributs CLR**<br /><br /> **Is Partial**<br /><br /> **Visibilité du package**|
|**C# enum**|Énumération UML|**ClrAttributes**<br /><br /> **Base Type**|
|**C# namespace**|Package UML|**Attributs CLR**<br /><br /> **Base Name**<br /><br /> **Using Namespaces**|

## <a name="see-also"></a>Voir aussi
 [Ajouter des stéréotypes à des éléments de modèle UML](../modeling/add-stereotypes-to-uml-model-elements.md) [personnaliser votre modèle avec des profils et des stéréotypes](../modeling/customize-your-model-with-profiles-and-stereotypes.md) [définir un profil pour étendre UML](../modeling/define-a-profile-to-extend-uml.md)
