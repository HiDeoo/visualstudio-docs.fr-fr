---
title: Modification de la valeur d’un local | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, changing values programmatically
ms.assetid: 8407d3df-d38a-4328-82d1-98084bef43ec
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 516725510c5f5bc7baa8bd96d3f7fb969b6589e5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "90839333"
---
# <a name="changing-the-value-of-a-local"></a>Modification de la valeur d’une variable locale
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

> [!IMPORTANT]
> Dans Visual Studio 2015, cette façon d’implémenter les évaluateurs d’expression est déconseillée. Pour plus d’informations sur l’implémentation des évaluateurs d’expression CLR, consultez [évaluateur d’expression CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) et [exemple évaluateur d’expression managée](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Quand une nouvelle valeur est tapée dans le champ valeur de la fenêtre **variables locales** , le package de débogage transmet la chaîne, telle qu’elle est tapée, à l’évaluateur d’expression (EE). L’EE évalue cette chaîne, qui peut contenir une valeur simple ou une expression, et stocke la valeur résultante dans le local associé.  
  
 Il s’agit d’une vue d’ensemble du processus de modification de la valeur d’une variable locale :  
  
1. Une fois que l’utilisateur a entré la nouvelle valeur, Visual Studio appelle [SetValueAsString](../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md) sur l’objet [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) associé au local.  
  
2. `IDebugProperty2::SetValueAsString` effectue les tâches suivantes :  
  
   1. Évalue la chaîne pour produire une valeur.  
  
   2. Lie l’objet [IDebugField](../../extensibility/debugger/reference/idebugfield.md) associé pour obtenir un objet [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) .  
  
   3. Convertit la valeur en une série d’octets.  
  
   4. Appelle [SetValue](../../extensibility/debugger/reference/idebugobject-setvalue.md) pour placer les octets de la valeur dans la mémoire afin que le programme en cours de débogage puisse y accéder.  
  
3. Visual Studio actualise l’affichage des **variables locales** (pour plus d’informations, consultez [affichage des variables locales](../../extensibility/debugger/displaying-locals.md) ).  
  
   Cette procédure est également utilisée pour modifier la valeur d’une variable dans la fenêtre **Espion** , sauf qu’il s’agit `IDebugProperty2` de l’objet associé à la valeur de l’objet local utilisé à la place de l' `IDebugProperty2` objet associé au local lui-même.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Exemple d’implémentation de la modification de valeurs](../../extensibility/debugger/sample-implementation-of-changing-values.md)  
 Utilise l’exemple MyCEE pour parcourir le processus de modification des valeurs.  
  
## <a name="see-also"></a>Voir aussi  
 [Écriture d’un évaluateur d’expression CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Affichage des variables locales](../../extensibility/debugger/displaying-locals.md)
