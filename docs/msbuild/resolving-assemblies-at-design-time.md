---
title: Résolution d’assemblys au moment du design | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- msbuild
ms.assetid: 20dae076-733e-49c1-a2e9-b336757ae21d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d599cd7acc4402408c1c5852e7aafe73e93b41ac
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54991825"
---
# <a name="resolve-assemblies-at-design-time"></a>Résoudre des assemblys au moment du design
Quand vous ajoutez une référence à un assembly par l’intermédiaire de l’onglet **.NET** de la boîte de dialogue **Ajouter une référence**, la référence pointe vers un assembly de référence intermédiaire, autrement dit un assembly qui contient toutes les informations de type et de signature, mais pas nécessairement du code. L’onglet **.NET** liste les assemblys de référence qui correspondent aux assemblys runtime de .NET Framework. Il présente aussi ceux qui correspondent aux assemblys runtime des dossiers AssemblyFoldersEx inscrits et utilisés par des tiers.  
  
## <a name="multi-targeting"></a>Multi-ciblage  
 [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)] vous permet de cibler des versions du .NET Framework qui s’exécutent sur le Common Language Runtime (CLR) version 2.0 ou version 4. Il s’agit des versions .NET Framework 2.0, 3.0, 3.5, 4, 4.5 et 4.5.1, et des versions Silverlight 1.0, 2.0 et 3.0. Si une nouvelle version du .NET Framework basée sur le CLR version 2.0 ou version 4 est publiée, le Framework peut être installé à l’aide d’un pack de ciblage, et il apparaîtra automatiquement en tant que cible dans Visual Studio.  
  
## <a name="how-type-resolution-works"></a>Fonctionnement de la résolution de type  
 À l’exécution, le CLR résout les types dans l’assembly en recherchant dans le GAC, le répertoire *bin* et les chemins de détection. Ceci est géré par le chargeur de fusion. Mais comment le chargeur de fusion sait-il ce qu’il doit rechercher ? Cela dépend d’une résolution effectuée au moment du design, lors de la génération de l’application.  
  
 Pendant la génération, le compilateur résout les types d’applications à l’aide d’assemblys de référence. Dans les versions 2.0, 3.0, 3.5, 4, 4.5 et 4.5.1 de .NET Framework, les assemblys de référence sont installés lors de l’installation de .NET Framework.  
  
 Les assemblys de référence sont fournis par le pack de ciblage fourni avec la version correspondante du SDK .NET Framework. Le Framework lui-même fournit uniquement les assemblys runtime. Pour générer des applications, vous devez installer le .NET Framework et le SDK .NET Framework correspondant.  
  
 Quand vous ciblez un .NET Framework spécifique, le système de génération résout tous les types en utilisant les assemblys de référence dans le pack de ciblage. Au moment de l’exécution, le chargeur de fusion résout ces mêmes types aux assemblys runtime, qui se trouvent généralement dans le GAC.  
  
 Si les assemblys de référence ne sont pas disponibles, le système de génération résout les types d’assemblys à l’aide des assemblys runtime. Les assemblys runtime du GAC n’étant pas différenciés par des numéros de version mineure, il peut arriver que la résolution soit effectuée avec le mauvais assembly. Cela peut se produire par exemple si une nouvelle méthode introduite dans le .NET Framework version 3.5 est référencée alors que vous ciblez la version 3.0. La génération réussira et l’application s’exécutera sur l’ordinateur de build, mais elle échouera lors du déploiement sur un ordinateur sur lequel la version 3.5 n’est pas installée.  
  
 Le pack de ciblage désormais fourni avec le kit SDK .NET Framework comporte la liste de tous les assemblys runtime de cette version du framework, appelée liste de redistribution (redist). Il est donc impossible que le système de génération résolve des types avec la mauvaise version de l’assembly.  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts avancés](../msbuild/msbuild-advanced-concepts.md)