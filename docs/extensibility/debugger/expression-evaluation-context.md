---
title: Contexte d’évaluation de l’expression | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e939a4fa5f4673e2f701206c96599c54bc0c3b51
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80738734"
---
# <a name="expression-evaluation-context"></a>Contexte d’évaluation de l’expression
Dans le [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] cadre du débogage, un **contexte d’évaluation d’expression**:

- Représente un contexte pour l’évaluation de l’expression. En règle générale, un contexte d’évaluation correspond à la portée lexicale dans laquelle évaluer les variables, les paramètres, les fonctions et les méthodes. Par exemple, un contexte d’évaluation d’expression associé à un frame de pile fournit le contexte pour l’évaluation des variables locales, des paramètres de méthode et des membres de classe (le cas échéant).

- Existe lorsqu’un programme s’est arrêté à un point d’arrêt. L’expression elle-même est une structure de données qui représente une expression analysée qui est prête pour la liaison et l’évaluation dans le contexte donné.

     Plus en détail, les expressions sont créées à l’aide de la méthode [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) . Lorsqu’une expression est évaluée, elle génère une chaîne imprimable contenant le nom et le type de variable ou d’argument et sa valeur. Cette chaîne s’affiche dans la Fenêtre Espion ou dans la fenêtre variables locales de l’IDE.

     Étant donné une `BSTR` interface et une interface [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) , un moteur de débogage (de) peut créer une interface [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) en analysant une expression. Pour une `IDebugExpression2` interface donnée, le de peut obtenir une valeur via l’évaluation d’expression synchrone ou asynchrone. Cette valeur, ainsi que le nom et le type de la variable ou de l’argument, sont envoyés à l’environnement de développement intégré (IDE) pour l’affichage.

## <a name="see-also"></a>Voir aussi
- [Interfaces d’évaluation d’expression](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [Contextes du débogueur](../../extensibility/debugger/debugger-contexts.md)
