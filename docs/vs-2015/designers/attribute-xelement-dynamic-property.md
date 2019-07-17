---
title: Attribute (propriété dynamique XElement) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ced05b8da63f9a7a242b166fe64e9e44f78b8065
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68162675"
---
# <a name="attribute-xelement-dynamic-property"></a>Attribute (propriété dynamique XElement)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Obtient un indexeur utilisé pour récupérer l'instance d'attribut qui correspond au nom développé spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
elem.Attribute[{namespaceName}attribName]  
```  
  
## <a name="property-valuereturn-value"></a>Valeur de propriété/valeur de retour  
 Indexeur de type `XAttribute Item(String expandedName)`. Cet indexeur prend le nom développé de l'attribut spécifié et retourne l'objet <xref:System.Xml.Linq.XAttribute> correspondant ou `null` s'il n'existe aucun attribut avec le nom spécifié.  
  
## <a name="remarks"></a>Notes  
 Cette propriété est équivalente à la méthode <xref:System.Xml.Linq.XElement.Attribute%2A> de la classe <xref:System.Xml.Linq.XElement?displayProperty=fullName>.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>   
 [Propriétés dynamiques de la classe XElement](../designers/xelement-class-dynamic-properties.md)   
 [Valeur](../designers/value-xattribute-dynamic-property.md)
