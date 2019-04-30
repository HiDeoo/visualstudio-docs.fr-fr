---
title: Interfaces de fournisseur de symboles | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, symbol handler
- symbol handler, interfaces
- symbol handler, evaluating variables
ms.assetid: 4201f10e-c9f7-4b38-bb45-40fe0082d5bf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9e98d792da99cafb670f64f572a1d6e3e4597f8e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62913512"
---
# <a name="symbol-provider-interfaces"></a>Interfaces des fournisseurs de symboles
Les éléments suivants sont les Interfaces de gestion des symboles pour le [!INCLUDE[vsipsdk](../../../extensibility/includes/vsipsdk_md.md)].

## <a name="discussion"></a>Discussion
 Ces interfaces sont utilisées pour évaluer les variables dans une pile des appels en mode arrêt. Elles sont implémentées uniquement pour le common language runtime symbole les fournisseurs (SP).

|Interface|Implémenté par|Description|
|---------------|--------------------|-----------------|
|[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)|SP|Représente l’adresse d’un élément.|
|[IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)|SP|Représente l’adresse d’un élément, en fournissant un accès à l’ID de processus.|
|[IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)|SP|Représente un symbole de tableau ou un type de tableau.|
|[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)|SP|Représente un symbole de classe ou un type de classe.|
|[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)|SP|Représente un fournisseur de symboles COM + avec des méthodes qui sont spécifiques au code managé.|
|[IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)|SP|Représente un fournisseur de symboles COM + avec des méthodes qui sont spécifiques au code managé et étend le **IDebugComPlusSymbolProvider**.|
|[IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)|SP|Représente un symbole ou un type qui est un conteneur pour d’autres symboles ou les types.|
|[IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)|SP|Représente un attribut personnalisé qui peut être associé à un symbole.|
|[IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md)|SP|Représente une requête pour les attributs personnalisés sur une méthode ou un type.|
|[IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)|SP|Fournit l’accès aux attributs personnalisés sur un symbole.|
|[IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md)|SP|L’interface de base pour tout type qui peut être déterminée au moment de l’exécution.|
|[IDebugDynamicFieldCOMPlus](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus.md)|SP|Représente un champ dynamique pour un [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) objet.|
|[IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)|SP|Représente un type d’énumération.|
|[IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)|SP|Étend les types de champs disponibles pour prendre en charge les génériques du code managé.|
|[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)|SP|La classe de base pour tous les champs ; représente une description d’un symbole ou un type.|
|[IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)|SP|Représente la définition d’un champ pour un type générique du code managé.|
|[IDebugGenericFieldInstance](../../../extensibility/debugger/reference/idebuggenericfieldinstance.md)|SP|Représente une instance d’un champ pour un type générique du code managé.|
|[IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)|SP|Représente un paramètre pour un type générique du code managé.|
|[IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)|SP|Représente une méthode.|
|[IDebugModOpt](../../../extensibility/debugger/reference/idebugmodopt.md)|SP|Représente un modificateur facultatif de débogage.|
|[IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)|SP|Représente un pointeur.|
|[IDebugPrimitiveTypeField](../../../extensibility/debugger/reference/idebugprimitivetypefield.md)|SP|Représente une valeur d’énumération de type primitif à partir d’un [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) interface.|
|[IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md)|SP|Représente une propriété d’une classe de code managé que vous pouvez obtenir ou définir.|
|[IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)|SP|Représente un fournisseur de symboles qui fournit des types et des symboles.|
|[IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)|SP|Représente un fournisseur de symboles avec un accès direct aux interfaces de symbole de métadonnées et core.|
|[IDebugTypeFieldBuilder](../../../extensibility/debugger/reference/idebugtypefieldbuilder.md)|SP|Représente la capacité de créer un champ qui représente un type.|
|[IDebugTypeFieldBuilder2](../../../extensibility/debugger/reference/idebugtypefieldbuilder2.md)|SP|Étend la **IDebugTypeFieldBuilder** pour être en mesure de créer des types de tableau.|
|[IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)|SP|Représente une collection de [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objets.|
|[IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)|SP|Représente une collection de [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md) objets.|
|[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)|SP|Représente une collection de [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objets.|

## <a name="see-also"></a>Voir aussi
- [Informations de référence sur les API](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)