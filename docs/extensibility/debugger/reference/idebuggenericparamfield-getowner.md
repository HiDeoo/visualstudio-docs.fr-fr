---
title: IDebugGenericParamField::GetOwner - France Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugGenericParamField::GetOwner
ms.assetid: c7f6d166-a69e-40c4-bd0b-1a1fdf9aaacf
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 040b8cf21cda1a0634c1c423516109b1ef214f01
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80727873"
---
# <a name="idebuggenericparamfieldgetowner"></a>IDebugGenericParamField::GetOwner
Récupère le type ou le propriétaire de la méthode de ce paramètre générique.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetOwner(
    IDebugField** ppOwner
);
```

```csharp
int GetOwner(
    out IDebugField ppOwner
);
```

## <a name="parameters"></a>Paramètres
`ppOwner`\
[out] Retourne l’objet [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) qui possède ce paramètre générique.

## <a name="return-value"></a>Valeur de retour
En cas de réussite, retourne `S_OK` , sinon, retourne un code d'erreur.

## <a name="example"></a>Exemple
L’exemple suivant montre comment implémenter cette méthode pour un objet **CDebugGenericParamFieldType** qui expose [l’interface IDebugGenericParamField.](../../../extensibility/debugger/reference/idebuggenericparamfield.md)

```cpp
HRESULT CDebugGenericParamFieldType::GetOwner(IDebugField** ppOwner)
{
    HRESULT hr = S_OK;
    CComPtr<IMetaDataImport> pMetadata;

    METHOD_ENTRY( CDebugGenericParamFieldType::GetOwner );

    IfFalseGo(ppOwner, E_INVALIDARG );
    *ppOwner = NULL;

    IfFailGo( this->LoadProps() );
    IfFailGo( m_spSH->GetMetadata( m_idModule, &pMetadata ) );

    switch (TypeFromToken(m_tokOwner))
    {
        case mdtMethodDef:
            {
                mdTypeDef tokClass;
                CComPtr<IDebugField> pClass;
                CDEBUG_ADDRESS caddr;
                CComPtr<IDebugContainerField> pContainer;

                IfFailGo( pMetadata->GetMethodProps( m_tokOwner, &tokClass, NULL, 0, NULL, NULL, NULL, NULL, NULL, NULL ) );
                IfFailGo( m_spSH->CreateClassType(m_idModule, tokClass, &pClass) );
                IfFailGo( pClass->QueryInterface( &pContainer ) );
                IfFailGo( caddr.InitializeMethod( m_idModule, tokClass, m_tokOwner, 0, 0 ) );
                IfFailGo( m_spSH->CreateMethodSymbol( pContainer, caddr, FIELD_SYM_MEMBER, ppOwner ) );
                break;
            }
        case mdtTypeDef:
            {
                IfFailGo( m_spSH->CreateClassType(m_idModule, m_tokOwner, ppOwner) );
                break;
            }
        default:
            {
                ASSERT(!"Unexpected Owner type for Generic Param Field");
                hr = E_FAIL;
            }
    }
Error:

    METHOD_EXIT( CDebugGenericParamFieldType::GetOwner, hr );
    return hr;
}
```

## <a name="see-also"></a>Voir aussi
- [IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)
