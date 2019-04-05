---
title: Exposition des Types aux concepteurs visuels | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- types [Visual Studio SDK], exposing to visual designers
- designers [Visual Studio SDK], exposing types
- custom tools, exposing types to visual designers
ms.assetid: a7a32ad4-3a0a-4eb8-a6ac-491c42885639
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c87f44dd12724c694fc27bae985f5f7fb617e45c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58948738"
---
# <a name="exposing-types-to-visual-designers"></a>Exposition des types aux concepteurs visuels
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] doit avoir accès aux définitions de classe et le type au moment du design pour afficher un concepteur visuel. Les classes sont chargés à partir d’un ensemble prédéfini d’assemblys qui incluent le jeu complète des dépendances du projet actuel (références plus leurs dépendances). Il peut également être nécessaire pour les concepteurs visuels pour accéder aux classes et des types qui sont définis dans les fichiers générés par les outils personnalisés.  
  
 Le [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] et [!INCLUDE[csprcs](../../includes/csprcs-md.md)] projet fournissent une assistance pour accéder à des types et des classes générées via temporaire portable fichiers exécutables (PE temporaires). N’importe quel fichier généré par un outil personnalisé peut être compilé dans un assembly temporaire afin que les types peuvent être chargées à partir de ces assemblys et exposés aux concepteurs. La sortie de chaque outil personnalisé est compilée dans un PE temporaire distinct, et la réussite ou l’échec de cette compilation temporaire dépend uniquement ou non le fichier généré peut être compilé. Même si un projet peuvent ne pas générer dans sa globalité, PE temporaires individuel peut rester disponible pour les concepteurs.  
  
 Le système de projet prend en charge pour le suivi des modifications au fichier de sortie d’un outil personnalisé, à condition que ces modifications sont le résultat de l’exécution de l’outil personnalisé. Chaque fois que l’outil personnalisé est exécuté, une nouvelle PE temporaire est généré et les notifications appropriées sont envoyées aux concepteurs.  
  
> [!NOTE]
>  Étant donné que le fichier exécutable de génération de programme temporaire se produit en arrière-plan, sans erreurs sont signalées à l’utilisateur si la compilation échoue.  
  
 Les outils personnalisés qui tirent parti de la prise en charge de PE temporaire doivent respecter les règles suivantes :  
  
-   `GeneratesDesignTimeSource` doit être définie sur 1 dans le Registre.  
  
     Aucune compilation de fichier exécutable du programme n’a lieu sans ce paramètre.  
  
-   Le code généré doit être dans la même langue que le paramètre de projet global.  
  
     Le PE temporaire est compilé, quel que soit ce que l’outil personnalisé signale que l’extension demandée dans <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A> autant que `GeneratesDesignTimeSource` est défini sur 1 dans le Registre. L’extension n’a pas besoin être .vb, .cs ou .jsl ; Il peut être n’importe quelle extension.  
  
-   Le code généré par l’outil personnalisé doit être valide, et il doit se compiler sur son propre à l’aide d’uniquement le jeu de références présents dans le projet au moment <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> termine son exécution.  
  
     Lorsqu’un PE temporaire est compilé, le seul fichier source spécifié pour le compilateur est la sortie de l’outil personnalisé. Par conséquent, un outil personnalisé qui utilise un PE temporaire doit générer des fichiers de sortie qui peuvent être compilés indépendamment des autres fichiers dans le projet.  
  
## <a name="see-also"></a>Voir aussi  
 [Introduction à l’objet BuildManager](http://msdn.microsoft.com/50080ec2-c1c9-412c-98ef-18d7f895e7fa)   
 [Implémentation de générateurs de fichier unique](../../extensibility/internals/implementing-single-file-generators.md)   
 [Déterminer le Namespace par défaut d’un projet](../../misc/determining-the-default-namespace-of-a-project.md)   
 [Inscription de générateurs de fichier unique](../../extensibility/internals/registering-single-file-generators.md)
