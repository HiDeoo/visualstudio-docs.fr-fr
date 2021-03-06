---
title: Prise en charge du service de langage pour le débogage | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c61f7fa7e698e2c01cadb1dbb36a321c6e656e35
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68195004"
---
# <a name="language-service-support-for-debugging"></a>Prise en charge du service de langage pour le débogage
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Un service de langage peut fournir des fonctionnalités qui prennent en charge un débogueur par le biais de l' <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo> interface. Ces fonctionnalités incluent la validation des points d’arrêt et la fourniture d’une liste d’expressions dans la fenêtre **automatique** .  
  
 Toutefois, vous devez disposer d’un évaluateur d’expression pour déboguer votre langage. L’évaluateur d’expression est responsable de l’évaluation des expressions afin de produire des valeurs pendant le débogage. Pour plus d’informations sur l’implémentation des évaluateurs d’expression CLR, consultez :  
  
- [Évaluateurs d’expression CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)  
  
- [Exemple d’évaluateur d’expression managée](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)  
  
## <a name="compiler-output"></a>Sortie du compilateur  
 Le type de compilateur détermine ce que vous devez faire pour implémenter le débogage pour votre langage. Si votre compilateur cible le système d’exploitation Windows et écrit un fichier. pdb, vous pouvez déboguer des programmes à l’aide du moteur de débogage de code natif intégré à Visual Studio. Si votre compilateur produit le langage MSIL (Microsoft Intermediate Language), vous pouvez déboguer des programmes avec le moteur de débogage de code managé, qui est également intégré à Visual Studio. Si votre compilateur cible un système d’exploitation propriétaire ou un environnement d’exécution différent, vous devez écrire votre propre moteur de débogage.  
  
 Pour plus d’informations sur l’implémentation du débogage pour votre langage, consultez [prise en main](../../extensibility/debugger/getting-started-with-debugger-extensibility.md) dans le kit de développement logiciel (SDK) de débogage Visual Studio.
