---
title: Element (propriété dynamique XElement)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 520df74dae14fe672eb7d3db1bdc23a0a6437b16
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54976756"
---
# <a name="element-xelement-dynamic-property"></a>Element (propriété dynamique XElement)

Obtient un indexeur utilisé pour récupérer l’instance d’élément enfant qui correspond au nom développé spécifié.

## <a name="syntax"></a>Syntaxe

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Valeur de propriété/valeur de retour

Indexeur de type `XElement Item(String expandedName)`. Cet indexeur prend un paramètre de nom développé et retourne l’objet <xref:System.Xml.Linq.XElement> correspondant ou `null` s’il n’existe aucun élément avec le nom spécifié.

## <a name="remarks"></a>Notes

Cette propriété est équivalente à la méthode <xref:System.Xml.Linq.XContainer.Element%2A> de la classe <xref:System.Xml.Linq.XContainer?displayProperty=fullName>.

## <a name="see-also"></a>Voir aussi

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [Propriétés dynamiques de la classe XElement](../designers/xelement-class-dynamic-properties.md)
- [Élements](../designers/elements-xelement-dynamic-property.md)