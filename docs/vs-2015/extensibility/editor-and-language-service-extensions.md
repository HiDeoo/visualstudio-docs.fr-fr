---
title: Extensions du service de langage et de l’éditeur | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK]
ms.assetid: 5653bac9-724f-4948-a820-68ce6aa96365
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7fa3e4be6ee44011eb1286e3ebf22ee69f8e3397
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "65683117"
---
# <a name="editor-and-language-service-extensions"></a>Extensions de l’éditeur et du service de langage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez étendre la plupart des fonctionnalités de l’éditeur de code Visual Studio. L’éditeur est basé sur le Windows Presentation Foundation (WPF) et écrit en code managé. Bien que cette conception diffère des conceptions dans les versions antérieures de Visual Studio, elle fournit la plupart des fonctionnalités. Pour étendre l’éditeur, utilisez le Managed Extensibility Framework (MEF).  
  
 Le kit de développement logiciel (SDK) Visual Studio fournit des adaptateurs appelés *shims* pour prendre en charge les VSPackages qui ont été écrits pour des versions antérieures. Néanmoins, si vous disposez déjà d’un VSPackage, nous vous recommandons de le mettre à jour vers la nouvelle technologie pour obtenir de meilleures performances et une meilleure fiabilité.  
  
## <a name="related-topics"></a>Rubriques connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Création d’une extension avec un modèle d’élément d’éditeur](../extensibility/creating-an-extension-with-an-editor-item-template.md)|Introduction à l’utilisation des modèles d’élément de l’éditeur.|  
|[Extension de l’éditeur et des services de langage](../extensibility/extending-the-editor-and-language-services.md)|Liens vers des documents qui présentent la conception et les fonctionnalités de l’éditeur principal et montrent comment l’étendre.|  
|[Interfaces héritées dans l’éditeur](../extensibility/legacy-interfaces-in-the-editor.md)|Liens vers des documents qui expliquent comment accéder à l’éditeur principal à partir du code existant.|  
|[Création d’éditeurs et de concepteurs personnalisés](../extensibility/creating-custom-editors-and-designers.md)|Liens vers des documents qui expliquent comment créer des éditeurs personnalisés.|  
|[Extensibilité du service de langage hérité](../extensibility/internals/legacy-language-service-extensibility.md)|Liens vers des documents qui décrivent comment intégrer des langages de programmation dans Visual Studio.|  
|[Managed Extensibility Framework (MEF)](https://msdn.microsoft.com/library/6c61b4ec-c6df-4651-80f1-4854f8b14dde)|Présente le Managed Extensibility Framework (MEF).|  
|[Windows Presentation Foundation](https://msdn.microsoft.com/library/f667bd15-2134-41e9-b4af-5ced6fafab5d)|Présente le Windows Presentation Foundation (WPF).|
