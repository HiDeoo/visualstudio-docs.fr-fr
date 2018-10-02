---
title: Attribute (propriété dynamique XElement) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 750e84a386360880cf30e76fc0157145820c654c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47501074"
---
# <a name="attribute-xelement-dynamic-property"></a>Attribute (propriété dynamique XElement)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [attribut (propriété dynamique XElement)](https://docs.microsoft.com/visualstudio/designers/attribute-xelement-dynamic-property).  
  
Obtient un indexeur utilisé pour récupérer l’instance d’attribut qui correspond au nom développé spécifié.  
  
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



