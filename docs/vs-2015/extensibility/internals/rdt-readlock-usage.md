---
title: Utilisation de RDT_ReadLock | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- RDT_ReadLock
- visible
- RDT_EditLock
- invisible
ms.assetid: b935fc82-9d6b-4a8d-9b70-e9a5c5ad4a55
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a9a6b5f86f0cfbb71f6264bdc74df72ad9209c9d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68154133"
---
# <a name="rdt_readlock-usage"></a>Utilisation de RDT_ReadLock
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> est un indicateur qui fournit la logique de verrouillage d’un document dans la table de document en cours d’exécution (RDT), qui est la liste de tous les documents actuellement ouverts dans l’IDE de Visual Studio. Cet indicateur détermine à quel moment les documents sont ouverts et si un document est visible dans l’interface utilisateur ou s’il est maintenu invisiblement en mémoire.  
  
 En règle générale, vous devez utiliser <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> lorsque l’une des conditions suivantes est vraie :  
  
- Lorsque vous souhaitez ouvrir un document de façon invisible et en lecture seule, mais il n’est pas encore établi, qui <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> doit lui être propriétaire.  
  
- Lorsque vous souhaitez que l’utilisateur soit invité à enregistrer un document qui a été ouvert de façon invisible avant de l’afficher dans l’interface utilisateur, puis a tenté de le fermer.  
  
## <a name="how-to-manage-visible-and-invisible-documents"></a>Comment gérer des documents visibles et invisibles  
 Lorsqu’un utilisateur ouvre un document dans l’interface utilisateur, un <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> propriétaire du document doit être établi et un <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> indicateur doit être défini. Si aucun <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> propriétaire ne peut être établi, le document n’est pas enregistré lorsque l’utilisateur clique sur **enregistrer tout** ou ferme l’IDE. Cela signifie que si un document est ouvert de façon invisible lorsqu’il est modifié en mémoire, et que l’utilisateur est invité à enregistrer le document à l’arrêt ou enregistré si **enregistrer tout** est choisi, un `RDT_ReadLock` ne peut pas être utilisé. Au lieu de cela, vous devez utiliser un `RDT_EditLock` et inscrire un <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> lorsqu’un <xref:Microsoft.VisualStudio.Shell.Interop.__VSREGDOCLOCKHOLDER> indicateur.  
  
## <a name="rdt_editlock-and-document-modification"></a>RDT_EditLock et modification de document  
 L’indicateur précédent mentionné indique que l’ouverture invisible du document produira son lors de l' `RDT_EditLock` ouverture du document par l’utilisateur dans une **DocumentWindow**visible. Dans ce cas, l’utilisateur reçoit une invite d' **enregistrement** lorsque la fonction **DocumentWindow** visible est fermée. Les implémentations de Microsoft. VisualStudio. Package. Automation. OAProject. CodeModel qui utilisent le <xref:Microsoft.VisualStudio.Shell.Interop.IVsInvisibleEditorManager> service fonctionnent initialement lorsque seul `RDT_ReadLock` est pris (c’est-à-dire lorsque le document est ouvert de façon invisible pour analyser les informations). Plus tard, si le document doit être modifié, le verrou est mis à niveau vers un **RDT_EditLock**faible. Si l’utilisateur ouvre ensuite le document dans un fichier **DocumentWindow**visible, le `CodeModel` faible `RDT_EditLock` est libéré.  
  
 Si l’utilisateur ferme ensuite la **DocumentWindow** et choisit **non** lorsqu’il est invité à enregistrer le document ouvert, l' `CodeModel` implémentation supprime toutes les informations du document et ouvre de nouveau le document à partir du disque, la prochaine fois que des informations supplémentaires sont requises pour le document. La subtilité de ce comportement est une instance où l’utilisateur ouvre la **DocumentWindow** du document ouvert invisible, le modifie, le ferme, puis choisit **non** lorsque vous êtes invité à enregistrer le document. Dans ce cas, si le document a un `RDT_ReadLock` , le document n’est pas réellement fermé et le document modifié reste ouvert de manière invisible, même si l’utilisateur a choisi de ne pas enregistrer le document.  
  
 Si l’ouverture invisible du document utilise un faible `RDT_EditLock` , il génère alors le verrou lorsque l’utilisateur ouvre le document de façon visible et qu’aucun autre verrou n’est maintenu. Lorsque l’utilisateur ferme la **DocumentWindow** et choisit **non** lorsqu’il est invité à enregistrer le document, le document doit être fermé à partir de la mémoire. Cela signifie que le client invisible doit écouter les événements RDT pour suivre cette occurrence. La prochaine fois que le document sera requis, le document doit être rouvert.
