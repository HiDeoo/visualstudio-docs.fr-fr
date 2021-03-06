---
title: 'Exemple d’extension Excel : classe PropertyProvider | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: 075d9b8d-8658-4fca-8711-08304dbac1c5
caps.latest.revision: 11
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 8ae254f85b00c47ba00250641f7afe0a638ceabc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72660420"
---
# <a name="sample-excel-extension-propertyprovider-class"></a>Exemple d'extension Excel : classe PropertyProvider
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette classe interne étend la classe <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> et fournit des services de propriétés pour des éléments [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] afin d’enregistrer et de lire des tests d’interface utilisateur.

## <a name="getcontrolsupportlevel-method"></a>Méthode GetControlSupportLevel
 La méthode <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetControlSupportLevel%2A> retourne un nombre qui indique le niveau de prise en charge que le fournisseur de propriétés peut offrir pour le contrôle fourni. Plus la valeur retournée est élevée, plus le fournisseur de propriétés peut prendre en charge le contrôle. Dans ce cas, la méthode vérifie la valeur de la propriété <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.TechnologyName%2A> du contrôle fourni. Si la valeur est « Excel » et que <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.ControlTypeName%2A> indique qu’il s’agit d’un `CellElement`, la méthode retourne la valeur la plus élevée. Sinon, elle retourne zéro, ce qui indique l’absence de prise en charge.

## <a name="getpropertynames-method"></a>Méthode GetPropertyNames
 Retourne un dictionnaire de noms de propriétés et de descripteurs de propriétés pour les propriétés prises en charge d’un contrôle Cell Excel.

## <a name="getpropertydescriptor-method"></a>Méthode GetPropertyDescriptor
 Cette méthode est appelée par le framework de test pour obtenir le descripteur de propriété prédéfini du nom de propriété fourni.

## <a name="getpropertyvalue-and-setpropertyvalue-methods"></a>Méthodes GetPropertyValue et SetPropertyValue
 La méthode `GetPropertyValue` utilise la classe `Communicator` de cette extension pour retourner la valeur de propriété à partir d’Excel. La méthode `SetPropertyValue` utilise la classe <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard> et le composant `Communicator` pour définir la valeur de propriété. Ces méthodes sont appelées par le framework de test.

## <a name="code-generation-customization-methods"></a>Méthodes de personnalisation de la génération de code
 Ces méthodes ne sont pas implémentées pour cette extension. Par conséquent, elles retournent `null` ou lèvent <xref:System.NotImplementedException>.

## <a name="see-also"></a>Voir aussi
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard>
 [Extension des tests codés de l'interface utilisateur t enregistrements des actions pour prendre charge Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
