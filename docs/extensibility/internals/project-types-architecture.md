---
title: Architecture des types de projets | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], architecture
ms.assetid: 9c1d940f-8a54-41f7-a8aa-c870e324371c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e53929b1ec2ed9c73191bf16f1cedc84a53b58f2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80706318"
---
# <a name="project-types-architecture"></a>Architecture des types de projets
Cette section contient des informations détaillées sur l’architecture des types de projet dans [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] .

## <a name="in-this-section"></a>Dans cette section
- [Éléments d’un modèle de projet](../../extensibility/internals/elements-of-a-project-model.md)

 Répertorie les services qu’un type de projet peut consommer et les interfaces qu’il doit implémenter.

- [Principaux composants d’un modèle de projet](../../extensibility/internals/project-model-core-components.md)

 Décrit les types de projets d’interfaces que doit implémenter et peut éventuellement implémenter pour fournir des fonctionnalités supplémentaires.

- [Quand créer des types de projets](../../extensibility/internals/when-to-create-project-types.md)

 Vous aide à déterminer quand vous devez créer un type de projet et quand vous pouvez utiliser une autre [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] fonctionnalité d’extensibilité telle que les VSPackages et les éditeurs pour atteindre le même objectif.

- [Hiérarchies et sélection](../../extensibility/internals/hierarchies-and-selection.md)

 Décrit comment [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] utilise les hiérarchies et le contexte de sélection pour offrir une expérience utilisateur cohérente et simplifiée.

## <a name="related-sections"></a>Sections connexes
- [Sous-types de projets](../../extensibility/internals/project-subtypes.md)

 Explique comment les sous-types de projet vous permettent de personnaliser le comportement des systèmes de projet de [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] et [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] .

- [Types de projets](../../extensibility/internals/project-types.md)

 Fournit une vue d’ensemble des projets en tant que blocs de construction de base de l' [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] environnement de développement intégré (IDE). Des liens sont fournis vers des rubriques supplémentaires qui expliquent comment les projets contrôlent la génération et la compilation du code.
