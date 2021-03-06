---
title: Développement d’un service de langage hérité | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- vs.vsip.LangServWiz.langtoks
- vs.vsip.LangServWiz.welcome
- vs.vsip.LangServWiz.langSpec
- vs.vsip.LangServWiz.langInfo
- vs.vsip.LangServWiz.langServOpts
helpviewer_keywords:
- language services, developing
ms.assetid: 6151ba88-c1c3-41de-a1cc-668f494d48d1
caps.latest.revision: 29
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 36ff8335bfaf99b5826d217a48910bfd581321e9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "90839694"
---
# <a name="developing-a-legacy-language-service"></a>Développement d’un service de langage hérité
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Cette section contient des liens vers des rubriques qui vous aident à créer un service de langage hérité.  
  
 Les services de langage hérités sont implémentés dans le cadre d’un VSPackage, mais la meilleure façon d’implémenter les fonctionnalités du service de langage consiste à utiliser les extensions MEF. Pour en savoir plus sur la nouvelle façon d’implémenter un service de langage, consultez [éditeur et extensions du service de langage](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
> Nous vous recommandons de commencer à utiliser la nouvelle API Editor dès que possible. Cela améliore les performances de votre service de langage et vous permet de tirer parti des nouvelles fonctionnalités de l’éditeur.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Modèle d’un service de langage hérité](../../extensibility/internals/model-of-a-legacy-language-service.md)  
 Fournit un modèle d’un service de langage minimal pour l' [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] éditeur de base. Vous pouvez utiliser ce modèle comme guide pour la création de votre propre service de langage.  
  
 [Interfaces du service de langage hérité](../../extensibility/internals/legacy-language-service-interfaces.md)  
 Décrit les objets requis pour implémenter un service de langage et fournit une liste d’objets supplémentaires que vous pouvez utiliser pour fournir une mise en surbrillance de la syntaxe, des données de méthode et d’autres fonctionnalités.  
  
 [Interception des commandes du service de langage hérité](../../extensibility/internals/intercepting-legacy-language-service-commands.md)  
 Décrit comment insérer un filtre de commande dans votre service de langage pour intercepter les commandes que l’affichage de texte gérerait autrement.  
  
 [Inscription d’un service de langage hérité](../../extensibility/internals/registering-a-legacy-language-service2.md)  
 Fournit des informations sur l’inscription de votre service de langage à l’aide de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .  
  
 [Prise en charge du service de langage pour le débogage](../../extensibility/internals/language-service-support-for-debugging.md)  
 Décrit comment un service de langage peut fournir des fonctionnalités pour prendre en charge un débogueur.  
  
 [Checklist : création d’un service de langage hérité](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)  
 Fournit des instructions pas à pas pour la création et l’intégration d’un service de langage pour l’éditeur principal.  
  
## <a name="related-sections"></a>Sections connexes  
 [Couleurs de syntaxe dans un service de langage hérité](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Explique comment implémenter la mise en surbrillance de la syntaxe dans votre service de langage.  
  
 [Saisie semi-automatique des instructions dans un service de langage hérité](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)  
 Décrit la saisie semi-automatique des instructions, le processus par lequel un service de langage aide les utilisateurs à terminer un mot clé ou un élément de langage qu’ils ont commencé à taper.  
  
 [Informations sur les paramètres dans un service de langage hérité](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)  
 Décrit comment fournir des conseils de méthode pour les fonctions et les méthodes surchargées.  
  
 [Guide pratique pour fournir la prise en charge de texte masqué dans un service de langage hérité](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)  
 Explique l’objectif d’une zone de texte masquée et fournit des instructions sur la façon d’implémenter une zone de texte masquée.  
  
 [Guide pratique pour fournir la prise en charge étendue du Mode Plan dans un service de langage hérité](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)  
 Explique les deux options qui étendent la prise en charge du mode plan à votre langage au-delà de la prise en charge de la commande *réduire aux définitions* .
