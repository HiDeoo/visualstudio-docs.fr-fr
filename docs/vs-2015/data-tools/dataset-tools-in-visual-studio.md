---
title: Outils de jeu de données
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
f1_keywords:
- vs.data.DataSet
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- untyped datasets
- datasets [Visual Basic], extended properties
- typed datasets
- current record in dataset
- XML [Visual Basic], datasets
- DataSet class, about datasets
- unique constraints (datasets)
- data relationships
- parent records in datasets
- extended properties, in typed datasets
- datasets [Visual Basic]
- schemas [Visual Basic], datasets
- datasets [Visual Basic], msprop
- master-detail tables, datasets
- databases [Visual Basic], updating
- msprop
- foreign keys, datasets
- DataSet class
- datasets [Visual Basic], filling
- case sensitivity, datasets
- constraints [Visual Basic], datasets
- child records
- related tables, datasets
- updating datasets, about dataset updates
- data caching, datasets
- DataRelation object, datasets
- untyped datasets, compared to typed datasets
- cache [Visual Studio], datasets
- datasets [Visual Basic], relationships
- related tables
- XML schemas, about XML schemas and datasets
- relationships, datasets
- typed datasets, compared to untyped datasets
- datasets [Visual Basic], populating
- datasets [Visual Basic], namespace
- data adapters, populating datasets
ms.assetid: ee57f4f6-9fe1-4e0a-be9a-955c486ff427
caps.latest.revision: 53
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 23e4deba53288383a569f6da6e14d27f723825ee
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72657384"
---
# <a name="dataset-tools-in-visual-studio"></a>Outils de dataset dans Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

REMARQUE]
> Les jeux de données et les classes associées sont des technologies .NET héritées des 2000 premières versions qui permettent aux applications d’utiliser des données en mémoire alors que les applications sont déconnectées de la base de données. Ils sont particulièrement utiles pour les applications qui permettent aux utilisateurs de modifier des données et de conserver les modifications dans la base de données. Bien que les jeux de données aient prouvé qu’il s’agit d’une technologie très performante, nous recommandons que les nouvelles applications .NET utilisent Entity Framework. Entity Framework offre un moyen plus naturel de travailler avec des données tabulaires en tant que modèles objet, et il dispose d’une interface de programmation plus simple.

 Un objet DataSet est un objet en mémoire qui est essentiellement une mini-base de données. Il contient des objets DataTable, DataColumn et DataRow dans lesquels vous pouvez stocker et modifier des données à partir d’une ou plusieurs bases de données sans avoir à maintenir une connexion ouverte. Le DataSet conserve des informations sur les modifications apportées à ses données, de sorte que les mises à jour peuvent être suivies et renvoyées à la base de données lorsque votre application est reconnectée.

 Les jeux de données et les classes associées sont définis dans l’espace de noms System. Data de la bibliothèque de classes .NET Framework. Vous pouvez créer et modifier dynamiquement des datasets dans le code. Pour plus d’informations sur la façon de procéder, consultez ADO.NET. La documentation de cette section montre comment utiliser des jeux de données à l’aide de concepteurs Visual Studio. Une chose à savoir : les jeux de données qui sont effectués par le biais de concepteurs utilisent des objets TableAdapter pour interagir avec la base de données, alors que les jeux de données qui sont créés par programmation utilisent des objets DataAdapter. Pour plus d’informations sur la création de jeux de données par programme, consultez [DataAdapters et DataReaders](https://msdn.microsoft.com/library/cc952ca2-ec19-46ab-9189-15174b52cb74).

 Si votre application doit uniquement lire les données d’une base de données et ne pas effectuer de mises à jour, d’ajouts ou de suppressions, vous pouvez généralement obtenir de meilleures performances en utilisant un objet DataReader pour récupérer des données dans un objet de liste générique ou un autre objet de collection. Si vous affichez les données, vous pouvez lier l’interface utilisateur à la collection.

## <a name="dataset-workflow"></a>Flux de travail du DataSet
 Visual Studio fournit de nombreux outils pour simplifier l’utilisation des jeux de données. Le flux de travail de bout en bout de base est le suivant :

- Utilisez la fenêtre **source de données** pour créer un nouveau jeu de données à partir d’une ou de plusieurs sources de données. Utilisez la **Concepteur de DataSet** pour configurer le jeu de données et définir ses propriétés. Par exemple, vous devez spécifier les tables de la source de données à inclure, ainsi que les colonnes de chaque table. Choisissez soigneusement pour conserver la quantité de mémoire requise par le jeu de données. Pour plus d’informations, consultez [Créer et configurer des datasets](../data-tools/create-and-configure-datasets-in-visual-studio.md).

- Spécifiez les relations entre les tables afin que les clés étrangères soient gérées correctement. Pour plus d’informations, consultez [remplir des jeux de données à l’aide de TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md).

- Utilisez l' **Assistant Configuration de TableAdapter** pour spécifier la requête ou la procédure stockée qui remplira le DataSet, ainsi que les opérations de base de données (mise à jour, suppression, etc.) à implémenter. Pour plus d’informations, consultez les rubriques suivantes :

  - [Remplir des datasets à l’aide de TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md)

  - [Modifier des données dans des datasets](../data-tools/edit-data-in-datasets.md)

  - [Valider les données dans des datasets](../data-tools/validate-data-in-datasets.md)

  - [Enregistrer les données dans la base de données](../data-tools/save-data-back-to-the-database.md)

- Interrogez et recherchez les données dans le DataSet. Pour plus d’informations, consultez [requêtes datasets](../data-tools/query-datasets.md). [!INCLUDE[linq_dataset](../includes/linq-dataset-md.md)] active [LINQ (Language-Integrated Query) sur les](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) données dans un <xref:System.Data.DataSet> objet. Pour plus d’informations, [consultez LINQ to DataSet](https://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17).

- Utilisez la fenêtre **sources de données** pour lier des contrôles d’interface utilisateur au DataSet ou à ses colonnes individuelles, et pour spécifier les colonnes qui peuvent être modifiées par l’utilisateur. Pour plus d’informations, consultez [lier des contrôles à des données dans Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md).

## <a name="datasets-and-n-tier-architecture"></a>Jeux de données et architecture multiniveau
 Pour plus d’informations sur les jeux de données dans les applications multicouches, consultez [utiliser des jeux de données dans des applications multicouches](../data-tools/work-with-datasets-in-n-tier-applications.md).

## <a name="datasets-and-xml"></a>Jeux de données et XML
 Pour plus d’informations sur la conversion de jeux de données vers et à partir de XML, consultez [lire des données XML dans un DataSet](../data-tools/read-xml-data-into-a-dataset.md) et [enregistrer un DataSet au format XML](../data-tools/save-a-dataset-as-xml.md).

## <a name="see-also"></a>Voir aussi
 [Outils de données Visual Studio pour .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)
