---
title: Convertir une chaîne normale en littéraux de chaîne verbatim
ms.date: 06/08/2020
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 7e8e239f53f92727072a2fcd6573d6957b7cd3ec
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85290334"
---
# <a name="convert-between-regular-string-and-verbatim-string-literals-refactoring"></a>Conversion entre une chaîne normale et des littéraux de chaîne Verbatim refactorisation

Cette refactorisation s’applique à :

- C#

**Ce qui suit :** Permet d’effectuer une conversion entre une chaîne normale et des littéraux de chaîne Verbatim.

Dans les **cas suivants :** Vous voulez économiser de l’espace ou améliorer la clarté de votre code.

**Pourquoi :** La conversion d’un littéral de chaîne Verbatim en littéral de chaîne standard peut permettre d’économiser de l’espace. La conversion d’un littéral de chaîne ordinaire en littéral de chaîne Verbatim peut fournir une plus grande clarté.

## <a name="how-to"></a>Procédures

1. Placez le signe insertion sur la chaîne normale ou le littéral de chaîne Verbatim :

2. Appuyez sur **CTRL** + **.** pour afficher le menu **Actions rapides et refactorisations**.

3. Sélectionnez l’une des options suivantes : 

    Sélectionnez **Convertir en chaîne classique**.

    ![Convertir en chaîne régulière](media/convert-to-regular-string.png)

    Sélectionnez **Convertir en chaîne verbatim**.

    ![Convertir en chaîne textuelle](media/convert-to-verbatim-string.png)

## <a name="see-also"></a>Voir aussi

- [Refactorisation](../refactoring-in-visual-studio.md)