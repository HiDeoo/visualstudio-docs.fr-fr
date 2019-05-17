---
title: IPropertyProxyProvider::GetPropertyProxy | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyProvider::GetPropertyProxy
helpviewer_keywords:
- IPropertyProxyProvider::GetPropertyProxy
ms.assetid: 3ebb7515-5bfe-48f4-9b8d-721b8f664eb6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2a05a903578e49b1b8ffefe0b0bb13fb693c993c
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458085"
---
# <a name="ipropertyproxyprovidergetpropertyproxy"></a>IPropertyProxyProvider::GetPropertyProxy
Récupère l’interface de proxy de propriété pour l’ID de proxy spécifié.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetPropertyProxy(
   DWORD                  dwID,
   IPropertyProxyEESide** proxy
);
```

```csharp
int GetPropertyProxy(
   uint                     dwID,
   out IPropertyProxyEESide proxy
);
```

## <a name="parameters"></a>Paramètres
 `dwID`\

 [in] ID du proxy de propriété souhaitée.

 `proxy`\

 [out] Retourne un [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) objet.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 Pour prendre en charge les visualiseurs de type externe, cette méthode transfère généralement l’appel à la [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md) (méthode). Consultez [visualisation et affichage des données](../../../extensibility/debugger/visualizing-and-viewing-data.md) pour plus d’informations sur la façon dont le IEEVisualizerService est obtenu.

## <a name="see-also"></a>Voir aussi
- [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md)
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)
- [Visualisation et affichage des données](../../../extensibility/debugger/visualizing-and-viewing-data.md)