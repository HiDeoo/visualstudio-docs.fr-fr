---
title: Impossible de supprimer le nom de la propriété de propriété &lt; &gt; | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: aca36919cb4c82d6ca76e0f3eecbbacd48cde768
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72667241"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted"></a>Impossible de supprimer le nom de la propriété de propriété &lt; &gt;
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La propriété \<property name> ne peut pas être supprimée, car elle est définie en tant que propriété de discriminateur pour l’héritage entre \<class name> et \<class name>

 La propriété sélectionnée est définie comme **Propriété de discriminateur** pour l’héritage entre les classes indiquées dans le message d’erreur. Les propriétés ne peuvent pas être supprimées si elles participent à la configuration d'héritage entre des classes de données.

 Affectez à **Propriété de discriminateur** une propriété différente de la classe de données pour permettre la suppression de la propriété voulue.

### <a name="to-correct-this-error"></a>Pour corriger cette erreur

1. Dans le Concepteur O/R, sélectionnez la ligne d'héritage qui connecte les classes de données indiquées dans le message d'erreur.

2. Affectez à **Propriété de discriminateur** une propriété différente.

3. Essayez une nouvelle fois de supprimer la propriété.

## <a name="see-also"></a>Voir aussi
 [Comment : configurer l’héritage à l’aide du concepteur o/r](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md) [héritage de classes de données (concepteur o/r)](../data-tools/data-class-inheritance-o-r-designer.md) [procédure pas à pas : création de classes LINQ to SQL à l’aide de l’héritage de table unique (concepteur o/r)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)
