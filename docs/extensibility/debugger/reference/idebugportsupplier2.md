---
title: IDebugPortSupplier2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier2
helpviewer_keywords:
- IDebugPortSupplier2 interface
ms.assetid: 37067324-2ea6-4a01-8829-a6e9c7a70068
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 947a311cb1e83eaa131730725aeb7938e5615f0f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66340050"
---
# <a name="idebugportsupplier2"></a>IDebugPortSupplier2
Cette interface fournit des ports pour le Gestionnaire de session de débogage (SDM).

## <a name="syntax"></a>Syntaxe

```
IDebugPortSupplier2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs
Un fournisseur de port personnalisé implémente cette interface pour représenter un fournisseur de port.

## <a name="notes-for-callers"></a>Notes de publication pour les appelants
Un appel à `CoCreateInstance` avec un fournisseur de port `GUID` retourne cette interface (il s’agit de la méthode standard pour obtenir cette interface). Exemple :

```cpp
IDebugPortSupplier2 *GetPortSupplier(GUID *pPortSupplierGuid)
{
    IDebugPortSupplier2 *pPS = NULL;
    if (pPortSupplierGuid != NULL) {
        CComPtr<IDebugPortSupplier2> spPortSupplier;
        spPortSupplier.CoCreateInstance(*pPortSupplierGuid);
        if (spPortSupplier != NULL) {
            pPS = spPortSupplier.Detach();
        }
    }
    return (pPS);
}
```

Un appel à [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md) renvoie cette interface, qui représente le fournisseur de port actuel utilisé par [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)].

- [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md) retourne cette interface, qui représente le fournisseur de port qui a créé le port.

- [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md) représente une liste de `IDebugPortSupplier` interfaces (le `IEnumDebugPortSuppliers` interface est obtenue à partir de [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md), qui représente tous les fournisseurs de port inscrit avec [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]).

En règle générale, un moteur de débogage n’interagit pas avec un fournisseur de port.

## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable
Le tableau suivant présente les méthodes de `IDebugPortSupplier2`.

|Méthode|Description|
|------------|-----------------|
|[GetPortSupplierName](../../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md)|Obtient le nom de fournisseur de port.|
|[GetPortSupplierId](../../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)|Obtient l’identificateur de fournisseur de port.|
|[GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md)|Obtient un port à partir d’un fournisseur de port.|
|[EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)|Énumère les ports qui existent déjà.|
|[CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)|Vérifie qu’un fournisseur de port prend en charge l’ajout de nouveaux ports.|
|[AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)|Ajoute un port.|
|[RemovePort](../../../extensibility/debugger/reference/idebugportsupplier2-removeport.md)|Supprime un port.|

## <a name="remarks"></a>Notes
Un fournisseur de port peut s’identifier par nom et ID, ajouter et supprimer les ports et énumérer tous les ports qui fournit le fournisseur de port.

## <a name="requirements"></a>Configuration requise
En-tête : msdbg.h

Espace de noms : Microsoft.VisualStudio.Debugger.Interop

Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Interfaces de base](../../../extensibility/debugger/reference/core-interfaces.md)
- [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)
- [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)
- [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)
