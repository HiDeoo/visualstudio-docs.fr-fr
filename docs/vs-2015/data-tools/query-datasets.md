---
title: Jeux de données de requête | Microsoft Docs
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.date: 11/15/2016
ms.topic: conceptual
ms.assetid: 7b1a91cf-8b5a-4fc0-ac36-0dc2d336fa1b
caps.latest.revision: 11
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7ccd5deffb0127769e2cd9dff3bf2accf75617eb
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72607448"
---
# <a name="query-datasets"></a>Interroger des datasets
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour rechercher des enregistrements spécifiques dans un DataSet, utilisez la méthode FindBy sur le DataTable, écrivez votre propre boucle foreach sur la collection Rows de la table ou utilisez [LINQ to DataSet](https://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17). LINQ to DataSet.

## <a name="dataset-case-sensitivity"></a>Respect de la casse du DataSet
 Dans un jeu de données, les noms de table et de colonne ne respectent pas la casse par défaut, c’est-à-dire qu’une table dans un DataSet appelé « clients » peut également être appelée « clients ». Cela correspond aux conventions d’affectation de noms dans de nombreuses bases de données, notamment SQL Server.In SQL Server, le comportement par défaut est que les noms des éléments de données ne peuvent pas être distingués uniquement par la casse.

> [!NOTE]
> Contrairement aux jeux de données, les documents XML respectent la casse, de sorte que les noms des éléments de données définis dans les schémas respectent la casse. Par exemple, le protocole de schéma permet au schéma de définir une table appelée « Customers » (clients) et une autre table appelée « Customers » (clients). Cela peut entraîner des collisions de noms lorsqu’un schéma qui contient des éléments qui diffèrent uniquement par la casse est utilisé pour générer une classe DataSet.

 Toutefois, le respect de la casse peut être un facteur déterminant la façon dont les données sont interprétées dans le jeu de données. Par exemple, si vous filtrez des données dans une table de DataSet, les critères de recherche peuvent retourner des résultats différents selon que la comparaison respecte la casse. Vous pouvez contrôler le respect de la casse pour le filtrage, la recherche et le tri en définissant la propriété du DataSet <xref:System.Data.DataSet.CaseSensitive%2A> . Toutes les tables du DataSet héritent par défaut de la valeur de cette propriété. (Vous pouvez remplacer cette propriété pour chaque table individuelle en définissant la propriété de la table <xref:System.Data.DataTable.CaseSensitive%2A> .)

## <a name="locate-a-specific-row-in-a-data-table"></a>Rechercher une ligne spécifique dans une table de données

#### <a name="to-find-a-row-in-a-typed-dataset-with-a-primary-key-value"></a>Pour rechercher une ligne dans un DataSet typé avec une valeur de clé primaire

- Pour localiser une ligne, appelez la méthode fortement typée `FindBy` qui utilise la clé primaire de la table.

     Dans l’exemple suivant, la `CustomerID` colonne est la clé primaire de la `Customers` table. Cela signifie que la `FindBy` méthode générée est `FindByCustomerID` . L’exemple montre comment assigner un spécifique <xref:System.Data.DataRow> à une variable à l’aide de la `FindBy` méthode générée.

     [!code-csharp[VbRaddataEditing#18](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#18)]
     [!code-vb[VbRaddataEditing#18](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#18)]

#### <a name="to-find-a-row-in-an-untyped-dataset-with-a-primary-key-value"></a>Pour rechercher une ligne dans un DataSet non typé avec une valeur de clé primaire

- Appelez la <xref:System.Data.DataRowCollection.Find%2A> méthode d’une <xref:System.Data.DataRowCollection> collection, en passant la clé primaire en tant que paramètre.

     L’exemple suivant montre comment déclarer une nouvelle ligne appelée `foundRow` et lui assigner la valeur de retour de la <xref:System.Data.DataRowCollection.Find%2A> méthode. Si la clé primaire est trouvée, le contenu de l’index de colonne 1 s’affiche dans une boîte de message.

     [!code-csharp[VbRaddataEditing#19](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#19)]
     [!code-vb[VbRaddataEditing#19](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#19)]

## <a name="findrows-by-column-values"></a>FindRows par valeurs de colonne

#### <a name="to-find-rows-based-on-the-values-in-any-column"></a>Pour rechercher des lignes en fonction des valeurs d’une colonne

- Les tables de données sont créées à l’aide de la <xref:System.Data.DataTable.Select%2A> méthode, qui retourne un tableau de <xref:System.Data.DataRow> s en fonction de l’expression transmise à la <xref:System.Data.DataTable.Select%2A> méthode. Pour plus d’informations sur la création d’expressions valides, consultez la section « syntaxe des expressions » de la page sur la <xref:System.Data.DataColumn.Expression%2A> propriété.

     L’exemple suivant montre comment utiliser la <xref:System.Data.DataTable.Select%2A> méthode de <xref:System.Data.DataTable> pour rechercher des lignes spécifiques.

     [!code-csharp[VbRaddataEditing#20](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#20)]
     [!code-vb[VbRaddataEditing#20](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#20)]

## <a name="access-related-records"></a>Accéder aux enregistrements associés
 Lorsque les tables d’un jeu de données sont liées, un <xref:System.Data.DataRelation> objet peut rendre les enregistrements associés disponibles dans une autre table. Par exemple, un jeu de données contenant `Customers` des `Orders` tables et peut être mis à disposition.

 Vous pouvez utiliser un <xref:System.Data.DataRelation> objet pour localiser des enregistrements connexes en appelant la <xref:System.Data.DataRow.GetChildRows%2A> méthode d’un <xref:System.Data.DataRow> dans la table parente. Cette méthode retourne un tableau d’enregistrements enfants connexes. Ou vous pouvez appeler la <xref:System.Data.DataRow.GetParentRow%2A> méthode d’un <xref:System.Data.DataRow> dans la table enfant. Cette méthode retourne un unique <xref:System.Data.DataRow> à partir de la table parente.

 Cette page fournit des exemples à l’aide de datasets typés. Pour plus d’informations sur la navigation dans les relations dans les datasets non typés, consultez [navigation](https://msdn.microsoft.com/library/e5e673f4-9b44-45ae-aaea-c504d1cc5d3e)dans les jeux de données.

> [!NOTE]
> Si vous travaillez dans une application Windows Forms et que vous utilisez les fonctionnalités de liaison de données pour afficher les données, le formulaire généré par le concepteur peut fournir suffisamment de fonctionnalités pour votre application. Pour plus d’informations, consultez [lier des contrôles à des données dans Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md).

 Les exemples de code suivants montrent comment parcourir les relations vers le haut et vers le haut dans des datasets typés. Les exemples de code utilisent les méthodes typées <xref:System.Data.DataRow> ( `NorthwindDataSet.OrdersRow` ) et les méthodes générées `FindBy` *PrimaryKey* ( `FindByCustomerID` ) pour rechercher une ligne souhaitée et retourner les enregistrements associés. Les exemples se compilent et s’exécutent correctement uniquement si vous disposez des éléments suivants :

- Instance d’un dataset nommé `NorthwindDataSet` avec une `Customers` table.

- Une `Orders` table.

- Une relation nommée `FK_Orders_Customers` qui associe les deux tables disponibles à l’étendue de votre code

En outre, les deux tables doivent être remplies de données pour tous les enregistrements à retourner.

#### <a name="to-return-the-child-records-of-a-selected-parent-record"></a>Pour retourner les enregistrements enfants d’un enregistrement parent sélectionné

- Appeler la <xref:System.Data.DataRow.GetChildRows%2A> méthode d’une `Customers` ligne de données spécifique et retourner un tableau de lignes de la `Orders` table :

     [!code-csharp[VbRaddataDatasets#6](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDatasets/CS/Form1.cs#6)]
     [!code-vb[VbRaddataDatasets#6](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDatasets/VB/Form1.vb#6)]

#### <a name="to-return-the-parent-record-of-a-selected-child-record"></a>Pour retourner l’enregistrement parent d’un enregistrement enfant sélectionné

- Appelez la <xref:System.Data.DataRow.GetParentRow%2A> méthode d’une `Orders` ligne de données spécifique et retournez une ligne unique à partir de la `Customers` table :

     [!code-csharp[VbRaddataDatasets#7](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDatasets/CS/Form1.cs#7)]
     [!code-vb[VbRaddataDatasets#7](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDatasets/VB/Form1.vb#7)]
