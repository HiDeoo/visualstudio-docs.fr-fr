---
title: Évaluation d’une expression de fenêtre Espion | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Watch window expressions
- Watch window, expressions
- expression evaluation, Watch window expressions
ms.assetid: b07e72c7-60d3-4b30-8e3f-6db83454c348
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f13573cfecbd81f36e3b77e9b23beeaa558c08dc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "90839974"
---
# <a name="evaluating-a-watch-window-expression"></a>Évaluation d’une expression de fenêtre Espion
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

> [!IMPORTANT]
> Dans Visual Studio 2015, cette façon d’implémenter les évaluateurs d’expression est déconseillée. Pour plus d’informations sur l’implémentation des évaluateurs d’expression CLR, consultez [évaluateur d’expression CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) et [exemple évaluateur d’expression managée](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Lorsque l’exécution est suspendue, Visual Studio appelle le moteur de débogage (DE) pour déterminer la valeur actuelle de chaque expression dans sa liste de suivi. Le DE évalue chaque expression à l’aide d’un évaluateur d’expression (EE), et Visual Studio affiche sa valeur dans la fenêtre **Espion** .  
  
 Voici une vue d’ensemble de l’évaluation d’une expression de liste de suivi :  
  
1. Visual Studio appelle le [GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) du de pour récupérer un contexte d’expression qui peut être utilisé pour évaluer des expressions.  
  
2. Pour chaque expression de la liste de suivi, Visual Studio appelle [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) pour convertir le texte de l’expression en une expression analysée.  
  
3. `IDebugExpressionContext2::ParseText` appelle [Parse](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) pour effectuer le travail d’analyse du texte et produire un objet [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) .  
  
4. `IDebugExpressionContext2::ParseText` crée un objet [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) et y place l' `IDebugParsedExpression` objet. Cet `DebugExpression2` objet I est ensuite renvoyé à Visual Studio.  
  
5. Visual Studio appelle [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) pour évaluer l’expression analysée.  
  
6. `IDebugExpression2::EvaluateSync` passe l’appel à [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) pour effectuer l’évaluation réelle et produire un objet [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) retourné à Visual Studio.  
  
7. Visual Studio appelle [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) pour obtenir la valeur de l’expression qui est ensuite affichée dans la liste Watch.  
  
## <a name="parse-then-evaluate"></a>Analyser puis évaluer  
 Étant donné que l’analyse d’une expression complexe peut prendre plus de temps que son évaluation, le processus d’évaluation d’une expression est divisé en deux étapes : 1) analyser l’expression et 2) évaluer l’expression analysée. De cette façon, l’évaluation peut se produire plusieurs fois, mais l’expression doit être analysée une seule fois. L’expression analysée intermédiaire est retournée à partir du EE dans un objet [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) qui est à son tour encapsulé et retourné à partir de la sous la forme d’un objet [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) . L' `IDebugExpression` objet diffère l’évaluation de l' `IDebugParsedExpression` objet.  
  
> [!NOTE]
> Il n’est pas nécessaire qu’un EE adhère à ce processus en deux étapes, même si Visual Studio l’utilise. le EE peut analyser et évaluer à la même étape lors de l’appel de [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) (c’est comme cela que l’exemple MyCEE fonctionne, par exemple). Si votre langage peut former des expressions complexes, vous souhaiterez peut-être séparer l’étape d’analyse de l’étape d’évaluation. Cela peut augmenter les performances dans le débogueur Visual Studio lorsque de nombreuses expressions Watch sont affichées.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Exemple d’implémentation de l’évaluation d’expression](../../extensibility/debugger/sample-implementation-of-expression-evaluation.md)  
 Utilise l’exemple MyCEE pour parcourir le processus d’évaluation d’expression.  
  
 [Évaluation d’une expression espionne](../../extensibility/debugger/evaluating-a-watch-expression.md)  
 Explique ce qui se produit après l’analyse d’une expression réussie.  
  
## <a name="related-sections"></a>Sections connexes  
 [Contexte d’évaluation](../../extensibility/debugger/evaluation-context.md)  
 Fournit les arguments passés lorsque le moteur DE débogage (DE) appelle l’évaluateur d’expression (EE).  
  
## <a name="see-also"></a>Voir aussi  
 [Écriture d’un évaluateur d’expression de CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)
