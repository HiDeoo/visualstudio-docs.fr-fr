---
title: Les objets que vous ajoutez au concepteur utilisent une connexion de données différente de celle utilisée actuellement par le concepteur
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 23abfbdc1b0bf922e3d15f0181afd7d01aa7ee2f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53935656"
---
# <a name="the-objects-you-are-adding-to-the-designer-use-a-different-data-connection-than-the-designer"></a>Les objets que vous ajoutez au concepteur utilisent une connexion de données autre que le Concepteur

Les objets que vous ajoutez au concepteur utilisent une connexion de données différente du concepteur en cours d'utilisation. Voulez-vous remplacer la connexion utilisée par le concepteur ?

Lorsque vous ajoutez des éléments à la **concepteur objet/relationnel** (**Concepteur O/R**), tous les éléments utilisent une seule connexion de données partagée. (L'aire de conception représente le <xref:System.Data.Linq.DataContext> qui utilise une connexion unique pour tous les objets sur l'aire.) Si vous ajoutez un objet au concepteur qui utilise une connexion de données différente de la connexion de données qui est actuellement utilisée par le concepteur, ce message apparaît. Pour résoudre cette erreur, vous pouvez maintenir la connexion existante. Dans ce cas, l'objet sélectionné n'est pas ajouté. Vous pouvez également choisir d’ajouter l’objet et de réinitialiser la connexion <xref:System.Data.Linq.DataContext> à la nouvelle connexion.

> [!NOTE]
> Si vous cliquez sur **Oui**, classes d’entité toutes sur le **Concepteur O/R** sont mappées à la nouvelle connexion.

## <a name="to-replace-the-existing-connection-with-the-connection-used-by-the-selected-object"></a>Pour remplacer la connexion existante par la connexion qu'utilise l'objet sélectionné

- Cliquez sur **Oui**.

    L’objet sélectionné est ajouté à la **Concepteur O/R**et le *DataContext.Connection* est définie sur la nouvelle connexion.

## <a name="to-continue-to-use-the-existing-connection-and-cancel-adding-the-selected-object"></a>Pour continuer d'utiliser la connexion existante et annuler l'ajout de l'objet sélectionné

- Cliquez sur **Non**.

    L'action est annulée. *DataContext.Connection* conserve la connexion existante.

## <a name="see-also"></a>Voir aussi

- [Messages du Concepteur O/R](../data-tools/o-r-designer-messages.md)
- [Outils LINQ to SQL dans Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
