---
title: '&lt; &gt; Impossible de supprimer le nom de la propriété de propriété, car il participe au nom de l’Association d’association &lt; &gt; | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 53bf12a84a705ddca0cacffc36028698cb08443a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72667267"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>Impossible de supprimer la propriété &lt;nom de la propriété&gt;, car elle participe à l’association &lt;nom de l’association&gt;
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La propriété sélectionnée est définie comme **Propriété d’association** pour l’association de classes indiquée dans le message d’erreur. Les propriétés ne peuvent pas être supprimées si elles participent à une association entre des classes de données.

 Affectez à **Propriété d’association** une propriété différente de la classe de données pour permettre la suppression de la propriété voulue.

### <a name="to-correct-this-error"></a>Pour corriger cette erreur

1. Dans le Concepteur O/R, sélectionnez la ligne d'association qui connecte les classes de données indiquées dans le message d'erreur.

2. Double-cliquez sur la ligne pour ouvrir la boîte de dialogue **Éditeur d’associations**.

3. Supprimez la propriété des **Propriétés d’association**.

4. Essayez une nouvelle fois de supprimer la propriété.

## <a name="see-also"></a>Voir aussi
 [Outils de LINQ to SQL dans Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md) [Comment : créer une association (relation) entre des classes LINQ to SQL (concepteur o/R)](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md) [procédure pas à pas : création de classes LINQ to SQL (concepteur o-r)](https://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233) [LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)
