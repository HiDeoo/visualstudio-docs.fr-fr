---
title: La modification du type de retour d’une méthode DataContext ne peut pas être annulée | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 76b161fc-5075-4192-8d94-f15b02e199e9
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: f020aed4c1213d3db008862386704c0f63b86bde
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72662469"
---
# <a name="changing-the-return-type-of-a-datacontext-method-cannot-be-undone"></a>Impossible d'annuler la modification du type de retour d'une méthode DataContext
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Impossible d'annuler la modification du type de retour d'une méthode DataContext. Pour revenir au type généré automatiquement, vous devez déplacer à nouveau l'élément de l'Explorateur de serveurs/Explorateur de bases de données vers le Concepteur O/R. Êtes-vous sûr de vouloir modifier le type de retour ?

 Le type de retour d’une méthode <xref:System.Data.Linq.DataContext> diffère selon l’endroit où vous déposez l’élément dans le [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]. Si vous déposez directement un élément dans une classe d’entité existante, une méthode <xref:System.Data.Linq.DataContext> qui a le type de retour de la classe d’entité est créée. Si vous déposez un élément dans une zone vide du [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], une méthode <xref:System.Data.Linq.DataContext> qui retourne un type généré automatiquement est créée. Vous pouvez modifier le type de retour d’une méthode <xref:System.Data.Linq.DataContext> après l’avoir ajoutée au volet de méthodes. Pour inspecter ou modifier le type de retour d’une méthode <xref:System.Data.Linq.DataContext>, sélectionnez-la et cliquez sur la propriété **Type de retour** dans la fenêtre **Propriétés**.

### <a name="to-change-the-return-type-of-a-datacontext"></a>Pour modifier le type de retour d'un DataContext

- Cliquez sur **Oui**.

### <a name="to-exit-the-message-box-and-leave-the-return-type-unchanged"></a>Pour sortir de la boîte de message et laisser le type de retour inchangé

- Cliquez sur **Non**.

### <a name="to-revert-to-the-original-return-type-after-changing-the-return-type"></a>Pour rétablir le type de retour d'origine après l'avoir modifié

1. Sélectionnez la méthode <xref:System.Data.Linq.DataContext> dans le [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] et supprimez-la.

2. Localisez l’élément dans l’**Explorateur de serveurs/Explorateur de bases de données** et faites-le glisser vers le [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].

     Une méthode <xref:System.Data.Linq.DataContext> est créée avec le type de retour par défaut d’origine.

## <a name="see-also"></a>Voir aussi
 [Outils de LINQ to SQL dans Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md) , [méthodes (concepteur o/r)](../data-tools/datacontext-methods-o-r-designer.md) [Comment : créer des méthodes DataContext mappées à des procédures stockées et des fonctions (concepteur o/r)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md) [LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)
