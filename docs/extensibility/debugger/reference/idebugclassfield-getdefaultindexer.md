---
title: 'IDebugClassField :: GetDefaultIndexer | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::GetDefaultIndexer
helpviewer_keywords:
- IDebugClassField::GetDefaultIndexer method
ms.assetid: 47ce4f45-3816-4b40-909c-5032d0692d75
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 57e00107374485043af370967794bdade1c213d1
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80734419"
---
# <a name="idebugclassfieldgetdefaultindexer"></a>IDebugClassField::GetDefaultIndexer
Obtient le nom de l’indexeur par défaut.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetDefaultIndexer( 
   BSTR* pbstrIndexer
);
```

```csharp
int GetDefaultIndexer(
   out string pbstrIndexer
);
```

## <a name="parameters"></a>Paramètres
`pbstrIndexer` à Retourne une chaîne contenant le nom de l’indexeur par défaut.

## <a name="return-value"></a>Valeur renvoyée
 En cas de réussite, retourne S_OK ou retourne S_FALSE s’il n’y a pas d’indexeur par défaut. Sinon, retourne un code d'erreur.

## <a name="remarks"></a>Notes
 L’indexeur par défaut d’une classe est la propriété qui est marquée en tant que `Default` propriété pour les accès au tableau. Cela est spécifique à [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] . Voici un exemple d’indexeur par défaut déclaré dans [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] et comment il est utilisé.

```vb
Imports System.Collections;

Public Class Class1
    Private myList as Hashtable

    Default Public Property Item(ByVal Index As Integer) As Integer
        Get
            Return CType(List(Index), Integer)
        End Get
        Set(ByVal Value As Integer)
            List(Index) = Value
        End Set
    End Property
End Class

Function GetItem(Index as Integer) as Integer
    Dim classList as Class1 = new Class1
    Dim value as Integer

    ' Access array through default indexer
    value = classList(2)

    ' Access array through explicit property
    value = classList.Item(2)

    Return value
End Function
```

## <a name="see-also"></a>Voir aussi
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
