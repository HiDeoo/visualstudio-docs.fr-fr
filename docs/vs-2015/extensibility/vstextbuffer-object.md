---
title: Objet VSTextBuffer | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VSTextBuffer
helpviewer_keywords:
- VSTextBuffer object, reference
- views [Visual Studio SDK], VSTextBuffer object
ms.assetid: c5f94b45-7249-4e1f-a53d-1d2a1c61e0ef
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a3466e52a980c9a8013491002fd3e005c9b98546
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49267687"
---
# <a name="vstextbuffer-object"></a>Objet VSTextBuffer
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

L’objet de mémoire tampon de texte représente un flux de texte Unicode, ce qui est généralement associé à un fichier. Un <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objet peut être utilisé en dehors du contexte de l’éditeur principal, comme dans le cas d’un Assistant.  
  
 Le tableau suivant présente les interfaces de `VSTextBuffer`.  
  
|Méthode|Description|  
|------------|-----------------|  
|[IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797)|Interface OLE standard. Principalement utilisé pour la gestion de la mémoire tampon Annuler/Rétablir.|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Interface OLE standard.|  
|[IPersistStream](http://msdn.microsoft.com/library/windows/desktop/ms690091)|Interface OLE standard.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Permet la création d’actions composés (autrement dit, les actions qui sont regroupées dans une unité d’annulation/de rétablissement unique).|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Active la persistance des données de document gérées par la mémoire tampon de texte.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|Fournit des services de base ; utilisé par de nombreux clients.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextFind>|Utilisé pour rechercher une mémoire tampon.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|Fournit lire et écrire des fonctionnalités à l’aide de coordonnées à deux dimensions. Hérite de `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|Fournit lire et écrire des fonctionnalités à l’aide des coordonnées unidimensionnelles. Hérite de `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|Offre un accès séquentiel, orienté flux et à du texte dans la mémoire tampon rapide.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|Fournit l’accès à une collection générique de propriétés. La propriété la plus importante est le nom ou le moniker, de la mémoire tampon. Vous pouvez stocker vos propres données aléatoires dans la mémoire tampon avec cette interface par la création d’un GUID et l’utiliser en tant que clé.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|Prend en charge les points de connexion pour les événements.|  
  
## <a name="remarks"></a>Notes  
 Le `VSTextBuffer` se trouve généralement par un `QueryInterface` appeler sur `IVsTextBuffer`. Pour plus d’informations, consultez [mémoire tampon de texte](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md).  
  
## <a name="see-also"></a>Voir aussi  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [Édition de figures](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)

