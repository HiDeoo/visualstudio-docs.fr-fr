---
title: Datasets typés et non typés | Microsoft Docs
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.date: 11/15/2016
ms.topic: conceptual
ms.assetid: c83ba0bb-5425-4d47-8891-6b4dbf937701
caps.latest.revision: 8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 39a16a200bbc057288ae2741e7d504566b0368e1
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72667154"
---
# <a name="typed-vs-untyped-datasets"></a>Datasets typés et non typés
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Un DataSet typé est un DataSet qui est dérivé d’abord de la classe de base, <xref:System.Data.DataSet> puis qui utilise les informations de la **Concepteur de DataSet**, qui est stockée dans un fichier. xsd, pour générer une nouvelle classe DataSet fortement typée. Les informations du schéma (tables, colonnes, etc.) sont générées et compilées dans cette nouvelle classe DataSet sous la forme d’un ensemble d’objets et de propriétés de première classe. Étant donné qu’un DataSet typé hérite de la classe de base <xref:System.Data.DataSet> , la classe typée utilise toutes les fonctionnalités de la <xref:System.Data.DataSet> classe et peut être utilisée avec les méthodes qui prennent une instance d’une <xref:System.Data.DataSet> classe comme paramètre.

 En revanche, un DataSet non typé n’a pas de schéma intégré correspondant. Comme dans un DataSet typé, un DataSet non typé contient des tables, des colonnes, etc., mais celles-ci sont exposées uniquement sous forme de collections. (Toutefois, une fois que vous avez créé manuellement les tables et d’autres éléments de données dans un DataSet non typé, vous pouvez exporter la structure du jeu de données en tant que schéma à l’aide de la méthode du DataSet <xref:System.Data.DataSet.WriteXmlSchema%2A> .)

## <a name="contrasting-data-access-in-typed-and-untyped-datasets"></a>Différences entre l’accès aux données dans les datasets typés et non typés
 La classe d’un DataSet typé possède un modèle d’objet dans lequel ses propriétés prennent les noms réels des tables et des colonnes. Par exemple, si vous utilisez un DataSet typé, vous pouvez référencer une colonne à l’aide d’un code tel que le suivant :

 [!code-csharp[VbRaddataDatasets#4](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDatasets/CS/Form1.cs#4)]
 [!code-vb[VbRaddataDatasets#4](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDatasets/VB/Form1.vb#4)]

 En revanche, si vous utilisez un DataSet non typé, le code équivalent est le suivant :

 [!code-csharp[VbRaddataDatasets#5](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDatasets/CS/Form1.cs#5)]
 [!code-vb[VbRaddataDatasets#5](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDatasets/VB/Form1.vb#5)]

 L’accès typé n’est pas seulement plus facile à lire, mais également entièrement pris en charge par IntelliSense dans l' [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] **éditeur de code**. En plus de faciliter l’utilisation de, la syntaxe du DataSet typé fournit la vérification de type au moment de la compilation, ce qui réduit considérablement les risques d’erreurs lors de l’affectation de valeurs aux membres d’un jeu de données. Si vous modifiez le nom d’une colonne dans votre <xref:System.Data.DataSet> classe et que vous compilez ensuite votre application, vous recevez une erreur de Build. En double-cliquant sur l’erreur de build dans le **liste des tâches**, vous pouvez accéder directement à la ligne ou aux lignes de code qui font référence à l’ancien nom de colonne. L’accès aux tables et aux colonnes d’un DataSet typé est également légèrement plus rapide lors de l’exécution, car l’accès est déterminé au moment de la compilation, et non pas dans les collections au moment de l’exécution.

 Bien que les datasets typés présentent de nombreux avantages, un DataSet non typé est utile dans de nombreuses circonstances. Le scénario le plus évident est lorsqu’aucun schéma n’est disponible pour le jeu de données. Cela peut se produire, par exemple, si votre application interagit avec un composant qui retourne un jeu de données, mais que vous ne connaissez pas à l’avance sa structure. De même, il peut arriver que vous utilisiez des données qui n’ont pas une structure statique et prévisible. Dans ce cas, il n’est pas pratique d’utiliser un DataSet typé, car vous devez régénérer la classe DataSet typée à chaque modification de la structure de données.

 Plus généralement, il existe de nombreux cas où vous pouvez créer un jeu de données de manière dynamique sans disposer d’un schéma. Dans ce cas, le jeu de données est simplement une structure pratique dans laquelle vous pouvez conserver des informations, à condition que les données puissent être représentées de manière relationnelle. En même temps, vous pouvez tirer parti des fonctionnalités du jeu de données, telles que la capacité à sérialiser les informations à passer à un autre processus ou à écrire un fichier XML.
