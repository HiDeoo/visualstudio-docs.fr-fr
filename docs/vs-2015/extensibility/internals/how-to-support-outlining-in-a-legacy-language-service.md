---
title: 'Comment : prendre en charge le mode plan dans un service de langage hérité | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], collapse to definitions command
- language services, supporting Collapse to Definitions command
- hidden text, Collapse to Definitions command
ms.assetid: bb6e74c3-93e4-4ef7-afc7-1c9b342f083b
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d92baa824dbb70dd591cadef99775f943c651aef
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "90840202"
---
# <a name="how-to-support-outlining-in-a-legacy-language-service"></a>Guide pratique pour prendre en charge le Mode Plan dans un service de langage hérité
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Le mode plan est utilisé pour développer ou réduire différentes zones de texte. La façon dont le mode plan est utilisé peut être définie différemment selon les différentes langues. Pour plus d’informations, voir [Mode Plan](../../ide/outlining.md).  
  
 Les services de langage hérités sont implémentés dans le cadre d’un VSPackage, mais la meilleure façon d’implémenter les fonctionnalités du service de langage consiste à utiliser les extensions MEF. Pour en savoir plus sur la nouvelle façon d’implémenter le mode plan, consultez [procédure pas à pas : mode plan](../../extensibility/walkthrough-outlining.md).  
  
> [!NOTE]
> Nous vous recommandons de commencer à utiliser la nouvelle API Editor dès que possible. Cela améliore les performances de votre service de langage et vous permet de tirer parti des nouvelles fonctionnalités de l’éditeur.  
  
 L’exemple suivant illustre la prise en charge de cette commande pour votre service de langage.  
  
### <a name="to-support-outlining"></a>Pour prendre en charge le mode plan  
  
1. Implémentez <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage> sur votre objet de service de langage.  
  
2. Appelez <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> sur l’objet de session en mode plan actuel pour ajouter de nouvelles régions en mode plan.  
  
## <a name="robust-programming"></a>Programmation fiable  
 Quand un utilisateur sélectionne **réduire aux définitions** dans le menu **mode plan** , l’IDE appelle <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage.CollapseToDefinitions%2A> sur votre service de langage.  
  
 Lorsque cette méthode est appelée, l’IDE passe dans un <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> pointeur (pointeur vers une mémoire tampon de texte) et un <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession> (pointeur vers la session en mode plan active).  
  
 Vous pouvez appeler la <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> méthode pour plusieurs régions en mode plan en spécifiant ces régions dans le `rgOutlnReg` paramètre. Le `rgOutlnReg` paramètre est une <xref:Microsoft.VisualStudio.TextManager.Interop.NewOutlineRegion> structure. Ce processus vous permet de spécifier différentes caractéristiques de la zone masquée, par exemple si une région particulière est développée ou réduite.  
  
> [!NOTE]
> N’oubliez pas de masquer les caractères de nouvelle ligne. Le texte masqué doit s’étendre à partir du début de la première ligne jusqu’au dernier caractère de la dernière ligne d’une section, ce qui laisse le caractère de nouvelle ligne final visible.  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : fournir une prise en charge du texte masqué dans un service de langage hérité](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)   
 [Guide pratique pour fournir la prise en charge étendue du Mode Plan dans un service de langage hérité](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)
