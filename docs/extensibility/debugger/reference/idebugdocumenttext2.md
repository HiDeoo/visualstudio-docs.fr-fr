---
title: IDebugDocumentText2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentText2
helpviewer_keywords:
- IDebugDocumentText2 interface
ms.assetid: e85f50a3-211c-4220-a9f4-789950ba2782
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5b5def7f6cc4ac5ced91ca0a273ce750003dca20
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80731560"
---
# <a name="idebugdocumenttext2"></a>IDebugDocumentText2
Cette interface représente un document texte.

## <a name="syntax"></a>Syntaxe

```
IDebugDocumentText2 : IDebugDocument2
```

## <a name="notes-for-implementers"></a>Notes pour les implémenteurs
 Un moteur DE débogage (DE) implémente cette interface lorsque le code source qu’il doit fournir est au format texte. Étant donné qu’il s’agit du cas le plus courant, si un DE implémente l’interface [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) , il doit également implémenter l' `IDebugDocumentText2` interface.

## <a name="notes-for-callers"></a>Notes pour les appelants
 Utilisez la `QueryInterface` méthode pour obtenir cette interface à partir d’une `IDebugDocument2` interface.

## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable
 Outre les méthodes sur l' `IDebugDocument2` interface, cette interface implémente les méthodes suivantes :

|Méthode|Description|
|------------|-----------------|
|[GetSize](../../../extensibility/debugger/reference/idebugdocumenttext2-getsize.md)|Récupère la taille du texte à cette position dans le document.|
|[GetText](../../../extensibility/debugger/reference/idebugdocumenttext2-gettext.md)|Récupère le texte à partir de la position spécifiée dans le document.|

## <a name="remarks"></a>Notes
 Un objet qui implémente cette interface doit également implémenter l' <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> interface, qui fournit l' <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> interface pour un objet [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md) .

## <a name="requirements"></a>Configuration requise
 En-tête : msdbg. h

 Espace de noms : Microsoft. VisualStudio. Debugger. Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)
- [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)
