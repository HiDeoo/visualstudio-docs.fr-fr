---
title: Héritage de classes de données (Concepteur O-R) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: af32653c-f4e6-4217-8c5a-e32b322b4918
caps.latest.revision: 7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 9e7dfc2b1137b30a03425f663d70e12c528dad39
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72657414"
---
# <a name="data-class-inheritance-or-designer"></a>Héritage de classes de données (Concepteur O/R)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Comme d'autres objets, les classes [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] peuvent utiliser l'héritage et être dérivées d'autres classes. Dans le code, vous pouvez spécifier des relations d'héritage entre des objets en déclarant qu'une classe hérite d'une autre. Dans une base de données, les relations d'héritage sont créées de plusieurs façons. L'[!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)] ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]) prend en charge le concept d'héritage à table unique qui est souvent implémenté dans les systèmes relationnels.

 Dans l'héritage à table unique, une table de base de données contient des colonnes pour les classes de base et dérivées. Avec les données relationnelles, une colonne de discriminateur contient la valeur qui détermine à quelle classe appartient un enregistrement donné. Prenons par exemple une table Persons qui contient tous les employées d'une société. Certaines personnes sont des employés et d'autres des responsables. La table Persons contient une colonne nommée Type qui a une valeur de 1 pour les responsables et une valeur de 2 pour les employés. Il s'agit de la colonne de discriminateur. Dans ce scénario, vous pouvez créer une sous-classe d'employés et remplir la classe avec uniquement des enregistrements ayant une valeur Type de 2.

 Quand vous configurez l’héritage dans les classes d’entité à l’aide du [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], faites glisser la table unique qui contient les données d’héritage sur le concepteur à deux reprises : une pour chaque classe dans la hiérarchie d’héritage. Après avoir ajouté les tables au concepteur, associez-les à un élément Héritage de la boîte à outils **Concepteur Objet Relationnel**, puis définissez les quatre propriétés d’héritage dans la fenêtre **Propriétés**.

## <a name="inheritance-properties"></a>Propriétés d'héritage
 Le tableau suivant répertorie les propriétés d'héritage et leurs descriptions :

|Propriété|Description|
|--------------|-----------------|
|Propriété de discriminateur|Propriété (mappée à la colonne) qui détermine à quelle classe appartient l'enregistrement actif.|
|Valeur Discriminator de la classe de base|Valeur (dans la colonne désignée comme Propriété de discriminateur) déterminant qu'un enregistrement fait partie de la classe de base.|
|Valeur Discriminator de la classe dérivée|Valeur (dans la propriété désignée comme Propriété de discriminateur) déterminant qu'un enregistrement fait partie de la classe dérivée.|
|Valeur par défaut d'héritage|Classe qui doit être remplie lorsque la valeur de la propriété désignée comme propriété de **discriminateur** ne correspond pas à la valeur de **discriminateur de classe de base** ou à la valeur de **discriminateur de classe dérivée**.|

 La création d'un modèle objet qui utilise l'héritage et correspond aux données relationnelles peut prêter à confusion. Cette rubrique fournit des informations à propos des concepts de base et des propriétés individuelles requises pour configurer l'héritage. Les rubriques suivantes fournissent une explication plus claire de la configuration de l'héritage avec l'[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].

|Rubrique|Description|
|-----------|-----------------|
|[Guide pratique pour configurer l’héritage à l’aide du Concepteur O/R](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)|Décrit comment configurer des classes d'entité qui utilisent l'héritage à table unique à l'aide de l'[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].|
|[Procédure pas à pas : création de classes LINQ to SQL à l’aide d’un héritage de table individuelle (Concepteur O/R)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)|Fournit des instructions pas à pas sur la configuration des classes d'entité qui utilisent l'héritage à table unique à l'aide de l'[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].|

## <a name="see-also"></a>Voir aussi
 [Outils de LINQ to SQL dans Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md) [procédure pas à pas : création de classes de LINQ to SQL (concepteur o-r)](https://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233) [procédure pas à pas : création de classes LINQ to SQL à l’aide de l’héritage de table unique (concepteur o/r)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md) [prise en main](https://msdn.microsoft.com/library/db8a557a-fef8-4f4f-bb91-8cff7250ee25)
