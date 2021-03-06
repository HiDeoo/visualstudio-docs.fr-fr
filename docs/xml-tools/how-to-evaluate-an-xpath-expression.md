---
title: Évaluer une expression XPath pendant le débogage
ms.date: 03/05/2019
ms.topic: how-to
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 64113461cd081eb97e2eb927119f1cd67f8a8d6e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85816252"
---
# <a name="evaluate-xpath-expressions"></a>Évaluer les expressions XPath

Vous pouvez évaluer des expressions XPath à l’aide de la fenêtre **Espion express** pendant le débogage. L’expression XPath doit être valide par rapport à la recommandation du W3C sur XPath 1.0. Le contexte XSLT actuel (autrement dit, le `self::node()` nœud dans la fenêtre **variables locales** ) fournit le contexte d’évaluation de l’expression XPath.

Lors de l’évaluation d’une expression XPath :

- Les fonctions XPath intégrées sont prises en charge.

- Les fonctions XSLT intégrées et les fonctions définies par l’utilisateur ne sont pas prises en charge.

> [!NOTE]
> Le débogage XSLT est disponible uniquement dans l’édition Enterprise de Visual Studio.

## <a name="evaluate-an-xpath-expression"></a>Évaluer une expression XPath

La procédure suivante utilise les fichiers *Below-Average. xsl* et *books.xml* de la page [procédure pas à pas : déboguer une feuille de style XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md#sample-files) .

1. Insérez un point d’arrêt à l’étiquette de début `xsl:if`.

2. Pour démarrer le débogage, choisissez **XML**  >  **Démarrer le débogage XSLT** dans la barre de menus (ou appuyez sur **ALT** + **F5**).

   Le débogueur démarre et s'arrête à la balise `xsl:if`.

3. Cliquez avec le bouton droit et sélectionnez **Espion express**.

   La fenêtre **Espion express** s’ouvre.

4. Entrez `./price/text()` dans le champ **expression** de la boîte de dialogue **Espion express** , puis choisissez **réévaluer**.

   Le prix du nœud book actuel s’affiche dans la zone **valeur** .

   ![Évaluer une expression XPath dans la fenêtre Espion express](media/quickwatch-price.png)

5. Modifiez l’expression XPath en `./price/text() < $bookAverage` et cliquez sur **réévaluer**.

   La zone **valeur** indique que l’expression XPath prend la valeur `true` .

## <a name="see-also"></a>Voir aussi

- [Débogage XSLT](../xml-tools/debugging-xslt.md)
