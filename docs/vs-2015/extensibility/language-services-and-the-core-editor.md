---
title: Services de langage et de l’éditeur principal | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - language services
ms.assetid: e03199a6-ad5f-4075-bfba-8d36865112b7
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 503924f435dda2d4432c915f9566846f0f4dd964
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51727301"
---
# <a name="language-services-and-the-core-editor"></a>Services de langage et de l’éditeur principal
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Éditeurs de Visual Studio sont souvent associés à un service de langage. Entre autres choses, un service de langage fournit la coloration syntaxique, la saisie semi-automatique des instructions, IntelliSense et la mise en forme du texte.  
  
## <a name="core-editors-and-document-data-objects"></a>Éditeurs de Core et des objets de données de Document  
 Lorsque vous accédez à l’éditeur principal, vous ne créez pas de données de document et les objets de vue de document. L’IDE crée et contrôle de ces deux objets, et vous procurer les handles en effectuant les appels appropriés dans l’éditeur de votre implémentation de la fabrique.  
  
 Pour plus d’informations, consultez [déterminer quel éditeur ouvre un fichier dans un projet](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md).  
  
## <a name="language-services-and-the-core-editor"></a>Services de langage et de l’éditeur principal  
 En implémentant un service de langage, vous pouvez contrôler la façon dont les données sont affichées dans la vue de document. Un service de langage fournit des informations et comportement est spécifique à une langue donnée, tels que Visual C++. Lorsque vous créez une mémoire tampon de texte et déterminez l’extension de nom de fichier pour le document que vous ouvrez, la mémoire tampon de texte détermine le service de langage associé à cette extension de nom de fichier à partir d’une clé de Registre HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Editors \\{GUID YourLanguageService} \Extensions. Le VSPackage standard chargement procédure puis charge votre VSPackage et une instance de votre service de langage est créée.  
  
 Un service de langage de base est indiqué dans l’illustration suivante.  
  
 ![Graphique de modèle de Service de langage](../extensibility/media/vslanguageservicemodel.gif "vsLanguageServiceModel")  
Objets de service principaux éditeur et la langue  
  
 L’objet de données de document pour l’éditeur principal est appelé une mémoire tampon de texte et est représenté par le <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objet. L’objet de vue de document est appelée un affichage de texte et est représenté par le <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> objet. Ces deux objets fonctionnent ensemble via le service de langage pour fournir une vue unifiée de l’éditeur principal. Informations à partir de la mémoire tampon de texte et l’affichage de texte présente dans une fenêtre de document appelée une fenêtre de code. Le document de la fenêtre code est géré par un gestionnaire de fenêtre de code.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 [Fournissant un contexte de Service de langage à l’aide de l’API héritée](../extensibility/providing-a-language-service-context-by-using-the-legacy-api.md)   
 [Hébergement d’IntelliSense](../extensibility/intellisense-hosting.md)   
 [Langues de relation contenant-contenus](../extensibility/contained-languages.md)   
 [Développement d’un service de langage hérité](../extensibility/internals/developing-a-legacy-language-service.md)

