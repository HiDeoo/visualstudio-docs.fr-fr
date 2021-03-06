---
title: Enregistrer des données à partir d’un objet dans une base de données | Microsoft Docs
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
- data [Visual Studio], saving
- data access [Visual Studio], objects
- saving data
ms.assetid: efd6135a-40cf-4b0d-8f8b-41a5aaea7057
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6c1470c831177e74e7670d696b44fc2b0119a9a9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72607453"
---
# <a name="save-data-from-an-object-to-a-database"></a>Enregistrer les données d’un objet dans une base de données
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez enregistrer des données dans des objets dans une base de données en passant les valeurs de votre objet à l’une des méthodes DBDirect du TableAdapter (par exemple, `TableAdapter.Insert` ).

 Pour enregistrer des données à partir d’une collection d’objets, parcourez la collection d’objets (par exemple, une boucle for-Next) et envoyez les valeurs de chaque objet à la base de données à l’aide de l’une des méthodes DBDirect du TableAdapter.

 Par défaut, les méthodes DBDirect sont créées sur un TableAdapter qui peut être exécuté directement sur la base de données. Ces méthodes peuvent être appelées directement et ne nécessitent pas <xref:System.Data.DataSet> <xref:System.Data.DataTable> d’objets ou pour harmoniser les modifications afin d’envoyer des mises à jour à une base de données.

> [!NOTE]
> Quand vous configurez un TableAdapter, la requête principale doit fournir suffisamment d’informations pour que les méthodes DBDirect soient créées. Par exemple, si un TableAdapter est configuré pour interroger des données d’une table qui n’a pas de colonne de clé primaire définie, il ne génère pas de méthodes DBDirect.

|Méthode DBDirect du TableAdapter|Description|
|----------------------------------|-----------------|
|`TableAdapter.Insert`|Ajoute de nouveaux enregistrements à une base de données et vous permet de transmettre des valeurs de colonne individuelles en tant que paramètres de méthode.|
|`TableAdapter.Update`|Met à jour les enregistrements existants dans une base de données. La `Update` méthode accepte les valeurs de colonne d’origine et nouvelles en tant que paramètres de méthode. Les valeurs d’origine sont utilisées pour localiser l’enregistrement d’origine, et les nouvelles valeurs sont utilisées pour mettre à jour cet enregistrement.<br /><br /> La `TableAdapter.Update` méthode est également utilisée pour réconcilier les modifications apportées à un DataSet dans la base de données en acceptant un <xref:System.Data.DataSet> ,, <xref:System.Data.DataTable> <xref:System.Data.DataRow> ou un tableau de <xref:System.Data.DataRow> s comme paramètres de méthode.|
|`TableAdapter.Delete`|Supprime les enregistrements existants de la base de données en fonction des valeurs de colonne d’origine passées en tant que paramètres de méthode.|

### <a name="to-save-new-records-from-an-object-to-a-database"></a>Pour enregistrer de nouveaux enregistrements d’un objet dans une base de données

- Créez les enregistrements en passant les valeurs à la `TableAdapter.Insert` méthode.

     L’exemple suivant crée un nouvel enregistrement Customer dans la `Customers` table en passant les valeurs de l' `currentCustomer` objet à la `TableAdapter.Insert` méthode.

     [!code-csharp[VbRaddataSaving#23](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#23)]
     [!code-vb[VbRaddataSaving#23](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#23)]

### <a name="to-update-existing-records-from-an-object-to-a-database"></a>Pour mettre à jour des enregistrements existants d’un objet vers une base de données

- Modifiez les enregistrements en appelant la `TableAdapter.Update` méthode, en passant les nouvelles valeurs pour mettre à jour l’enregistrement et en passant les valeurs d’origine pour localiser l’enregistrement.

    > [!NOTE]
    > Votre objet doit conserver les valeurs d’origine afin de les passer à la `Update` méthode. Cet exemple utilise des propriétés avec un `orig` préfixe pour stocker les valeurs d’origine.

     L’exemple suivant met à jour un enregistrement existant dans la `Customers` table en passant les valeurs nouvelles et d’origine de l' `Customer` objet à la `TableAdapter.Update` méthode.

     [!code-csharp[VbRaddataSaving#24](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#24)]
     [!code-vb[VbRaddataSaving#24](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#24)]

### <a name="to-delete-existing-records-from-a-database"></a>Pour supprimer des enregistrements existants d’une base de données

- Supprimez les enregistrements en appelant la `TableAdapter.Delete` méthode et en passant les valeurs d’origine pour localiser l’enregistrement.

    > [!NOTE]
    > Votre objet doit conserver les valeurs d’origine afin de les passer à la `Delete` méthode. Cet exemple utilise des propriétés avec un `orig` préfixe pour stocker les valeurs d’origine.

     L’exemple suivant supprime un enregistrement de la `Customers` table en passant les valeurs d’origine de l' `Customer` objet à la `TableAdapter.Delete` méthode.

     [!code-csharp[VbRaddataSaving#25](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#25)]
     [!code-vb[VbRaddataSaving#25](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#25)]

## <a name="net-framework-security"></a>Sécurité du .NET Framework
 Vous devez être autorisé à effectuer l’insertion, la mise à jour ou la suppression sélectionnée sur la table dans la base de données.

## <a name="see-also"></a>Voir aussi
 [Enregistrer les données dans la base de données](../data-tools/save-data-back-to-the-database.md)
