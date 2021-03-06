---
title: Ajouter de nouvelles sources de données | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
f1_keywords:
- vs.datasource.datasourcefieldspicker
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], data sources
- data sources
ms.assetid: ed28c625-bb89-4037-bfde-cfa435d182a2
caps.latest.revision: 60
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 85c07ad7995bc614df4b988bb17fa8977452b5d8
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72673067"
---
# <a name="add-new-data-sources"></a>Ajouter de nouvelles sources de données
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans le contexte de .NET Data Tools dans Visual Studio, le terme « *source de données* » fait référence aux objets .net qui se connectent à un magasin de données et exposent les données à une application .net. Les concepteurs Visual Studio peuvent utiliser la sortie de la source de données pour générer le code réutilisable qui lie les données aux formulaires quand vous faites glisser et déposez des objets de base de données à partir de la fenêtre **sources de données** . Ce type de source de données peut être :

- Classe dans un modèle de Entity Framework qui est associé à un type de base de données.

- Jeu de données associé à un type de base de données.

- Classe qui représente un service réseau tel qu’un service de données Windows Communication Foundation (WCF) ou un service REST.

- Classe qui représente un service SharePoint.

- Une classe ou une collection dans votre solution.

> [!NOTE]
> Si vous n’utilisez pas les fonctionnalités de liaison de données, DataSets, Entity Framework, LINQ to SQL, WCF ou SharePoint, le concept de « source de données » ne s’applique pas. Il vous suffit de vous connecter directement à la base de données à l’aide des objets SQLCommand et de communiquer directement avec la base de données.

 Vous créez et modifiez des sources de données à l’aide de l' **Assistant Configuration de source de données** dans une application Windows Forms ou Windows Presentation Foundation. Pour Entity Framework, commencez par créer vos classes d’entité, puis démarrez l’Assistant en sélectionnant **projet**  >  **Ajouter une nouvelle source de données** (décrit plus en détail plus loin dans cet article).

 ![Assistant Configuration de source de données](../data-tools/media/data-source-configuration-wizard.png "Assistant Configuration de source de données")

 Une fois que vous avez créé une source de données, celle-ci apparaît dans la fenêtre outil **sources de données** (Maj + Alt + D ou **Afficher**d'  >  **autres**  >  **sources de données**Windows). Vous pouvez faire glisser une source de données depuis la fenêtre **sources de données** vers une aire de conception de formulaire ou un contrôle. Cela entraîne la génération de code réutilisable, c’est-à-dire le code qui affiche les données provenant du magasin de données pour l’utilisateur. L’illustration suivante montre un jeu de données qui a été supprimé dans un Windows Form. Si vous avez sélectionné la touche F5 sur l’application, les données de la base de données sous-jacente s’affichent dans les contrôles du formulaire.

 ![Opération glisser de source de données](../data-tools/media/raddata-data-source-drag-operation.png "opération glisser de la source de données raddata")

## <a name="data-source-for-a-database-or-a-database-file"></a>Source de données d’une base de données ou d’un fichier de base de données

### <a name="dataset"></a>Dataset
 Pour créer un DataSet en tant que source de données, exécutez l' **Assistant Configuration de source de données** (**projet**  >  **Ajouter une nouvelle** source de données) et choisissez le type **de source de données de la base de** données. Suivez les invites pour spécifier une connexion de base de données nouvelle ou existante ou un fichier de base de données.

### <a name="entity-classes"></a>Classes Entity
 Pour créer un modèle de Entity Framework comme source de données, exécutez d’abord l' **Assistant Entity Data Model** pour créer les classes d’entité (**projet**  >  **Ajouter un nouvel élément**  >  **ADO.NET Entity Data Model**).

 ![Nouvel élément de projet de modèle de Entity Framework](../data-tools/media/raddata-new-entity-framework-model-project-item.png "raddata nouvel élément de projet de modèle de Entity Framework")

 Choisissez la méthode par laquelle vous souhaitez générer le modèle.

 ![Entity Data Model (assistant)](../data-tools/media/raddata-entity-data-model-wizard.png "Assistant Entity Data Model raddata")

 Ajoutez le modèle en tant que source de données. Les classes qui ont été générées s’affichent dans l **'Assistant Configuration de source de données** lorsque vous choisissez la catégorie **objets** .

 ![Assistant Configuration de source de données avec des classes d’entité](../data-tools/media/raddata-data-source-configuration-wizard-with-entity-classes.png "Assistant Configuration de source de données raddata avec des classes d’entité")

## <a name="data-source-for-a-service"></a>Source de données d’un service
 Pour créer une source de données à partir d’un service, exécutez l' **Assistant Configuration de source de données** et choisissez le type de source de données du **service** . Il s’agit simplement d’un raccourci vers la boîte de dialogue **Ajouter une référence de service** , à laquelle vous pouvez également accéder en cliquant avec le bouton droit sur le projet dans **Explorateur de solutions** et en sélectionnant **Ajouter une référence de service**.

 Quand vous créez une source de données à partir d’un service, Visual Studio ajoute une référence de service à votre projet. Visual Studio crée également des objets proxy qui correspondent aux objets retournées par le service. Par exemple, un service qui retourne un jeu de données est représenté dans votre projet sous la forme d’un jeu de données ; un service qui retourne un type spécifique est représenté dans votre projet sous la forme du type retourné.

 Vous pouvez créer une source de données à partir des types de services suivants :

- Services de données WCF. Pour plus d’informations, consultez [What is Content Moderator?](https://msdn.microsoft.com/library/7924cf94-c9a6-4015-afc9-f5d22b1743bb) (Présentation de Content Moderator).

- Services de données WCF. Pour plus d’informations, consultez [Windows Communication Foundation services et WCF Data Services dans Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md).

- Services Web.

    > [!NOTE]
    > Les éléments qui s’affichent dans la fenêtre **sources de données** dépendent des données retournées par le service. Certains services peuvent ne pas fournir suffisamment d’informations pour que l’**Assistant Configuration de source de données** puisse créer des objets pouvant être liés. Par exemple, si le service retourne un DataSet non typé, aucun élément ne s’affiche dans la fenêtre **sources de données** lorsque vous terminez l’Assistant. Cela est dû au fait que les datasets non typés ne fournissent pas de schéma et, par conséquent, que l’Assistant ne dispose pas de suffisamment d’informations pour créer la source de données.

## <a name="data-source-for-an-object"></a>Source de données d’un objet
 Vous pouvez créer une source de données à partir de n’importe quel objet qui expose une ou plusieurs propriétés publiques en exécutant l' **Assistant Configuration de source de données** , puis en sélectionnant le type de source de données de l' **objet** . Toutes les propriétés publiques d’un objet sont affichées dans la fenêtre **sources de données** .   Si vous utilisez Entity Framework et que vous avez généré un modèle, c’est là que vous trouvez les classes d’entité qui seront les sources de données pour votre application.

 Dans la page **Sélectionner les objets de données** , développez les nœuds dans l’arborescence pour rechercher les objets que vous souhaitez lier. L’arborescence contient des nœuds pour votre projet et pour les assemblys et d’autres projets référencés par votre projet.

 Si vous souhaitez établir une liaison à un objet d’un assembly ou d’un projet qui n’apparaît pas dans l’arborescence, cliquez sur **Ajouter une référence** et utilisez la **boîte de dialogue Ajouter une référence** pour ajouter une référence à l’assembly ou au projet. Une fois la référence ajoutée, l’assembly ou le projet est ajouté à l’arborescence.

> [!NOTE]
> Vous devrez peut-être générer le projet qui contient vos objets pour que les objets s’affichent dans l’arborescence.

> [!NOTE]
> Pour prendre en charge la liaison de données par glisser-déplacer, les objets qui implémentent l' <xref:System.ComponentModel.ITypedList> <xref:System.ComponentModel.IListSource> interface ou doivent avoir un constructeur par défaut. Dans le cas contraire, Visual Studio ne peut pas instancier l’objet source de données, et il affiche une erreur quand vous faites glisser l’élément sur l’aire de conception.

## <a name="data-source-for-a-sharepoint-list"></a>Source de données d’une liste SharePoint
 Vous pouvez créer une source de données à partir d’une liste SharePoint en exécutant l **'Assistant Configuration de source de données** et en sélectionnant le type de source de données **SharePoint** . SharePoint expose des données via [!INCLUDE[ssAstoria](../includes/ssastoria-md.md)] , donc la création d’une source de données SharePoint est identique à la création d’une source de données à partir d’un service. La sélection de l’élément **SharePoint** dans l **'Assistant Configuration de source de données** ouvre la boîte de dialogue **Ajouter une référence de service** , où vous vous connectez au service de données SharePoint en pointant sur le serveur SharePoint.  Cela nécessite le kit de développement logiciel (SDK) SharePoint.

## <a name="see-also"></a>Voir aussi
 [Outils de données Visual Studio pour .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)
