---
title: Interfaces du fournisseur de symboles | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, symbol handler
- symbol handler, interfaces
- symbol handler, evaluating variables
ms.assetid: 4201f10e-c9f7-4b38-bb45-40fe0082d5bf
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7929ba36c76f0db1cabab087afe3590de509efff
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80715848"
---
# <a name="symbol-provider-interfaces"></a>Interfaces des fournisseurs de symboles
Voici les interfaces de gestion de symboles pour le [!INCLUDE[vsipsdk](../../../extensibility/includes/vsipsdk_md.md)] .

## <a name="discussion"></a>Discussion
 Ces interfaces sont utilisées pour évaluer des variables dans une pile des appels en mode arrêt. Elles sont implémentées uniquement pour les common language runtime les fournisseurs de symboles (SP).

|Interface|Implémenté par|Description|
|---------------|--------------------|-----------------|
|[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)|SP|Représente l’adresse d’un élément.|
|[IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)|SP|Représente l’adresse d’un élément, fournissant un accès à l’ID de processus.|
|[IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)|SP|Représente un symbole de tableau ou un type de tableau.|
|[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)|SP|Représente un symbole de classe ou un type de classe.|
|[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)|SP|Représente un fournisseur de symboles COM+ avec des méthodes qui sont spécifiques au code managé.|
|[IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)|SP|Représente un fournisseur de symboles COM+ avec des méthodes qui sont spécifiques au code managé et étendent le **IDebugComPlusSymbolProvider**.|
|[IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)|SP|Représente un symbole ou un type qui est un conteneur pour d’autres symboles ou types.|
|[IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)|SP|Représente un attribut personnalisé qui peut être attaché à un symbole.|
|[IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md)|SP|Représente une requête d’attributs personnalisés sur une méthode ou un type.|
|[IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)|SP|Fournit l’accès aux attributs personnalisés sur un symbole.|
|[IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md)|SP|Interface de base pour tout type pouvant être déterminé au moment de l’exécution.|
|[IDebugDynamicFieldCOMPlus](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus.md)|SP|Représente un champ dynamique pour un objet [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) .|
|[IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)|SP|Représente un type d'énumération.|
|[IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)|SR|Étend les types de champs disponibles pour prendre en charge les génériques de code managé.|
|[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)|SP|Classe de base pour tous les champs ; représente une description d’un symbole ou d’un type.|
|[IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)|SP|Représente la définition d’un champ pour un type générique de code managé.|
|[IDebugGenericFieldInstance](../../../extensibility/debugger/reference/idebuggenericfieldinstance.md)|SP|Représente une instance d’un champ pour un type générique de code managé.|
|[IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)|SP|Représente un paramètre pour un type générique de code managé.|
|[IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)|SP|Représente une méthode.|
|[IDebugModOpt](../../../extensibility/debugger/reference/idebugmodopt.md)|SP|Représente un modificateur facultatif Debug.|
|[IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)|SP|Représente un pointeur.|
|[IDebugPrimitiveTypeField](../../../extensibility/debugger/reference/idebugprimitivetypefield.md)|SP|Représente une valeur d’énumération de type primitif à partir d’une interface [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) .|
|[IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md)|SP|Représente une propriété d’une classe de code managé qui peut être obtenue ou définie.|
|[IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)|SP|Représente un fournisseur de symboles qui fournit des symboles et des types.|
|[IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)|SP|Représente un fournisseur de symboles avec un accès direct aux métadonnées et aux interfaces de symboles principaux.|
|[IDebugTypeFieldBuilder](../../../extensibility/debugger/reference/idebugtypefieldbuilder.md)|SP|Représente la capacité de créer un champ qui représente un type.|
|[IDebugTypeFieldBuilder2](../../../extensibility/debugger/reference/idebugtypefieldbuilder2.md)|SP|Étend le **IDebugTypeFieldBuilder** pour pouvoir créer des types de tableau.|
|[IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)|SP|Représente une collection d’objets [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) .|
|[IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)|SP|Représente une collection d’objets [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md) .|
|[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)|SP|Représente une collection d’objets [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) .|

## <a name="see-also"></a>Voir aussi
- [Référence sur l’API](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)
