---
title: Avertissements de la facilité de maintenance | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f709a7bb2d433ab86b5088349f1977a66c9a4c42
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49238496"
---
# <a name="maintainability-warnings"></a>avertissements liés à la facilité de maintenance
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Avertissements de la facilité de gestion prennent en charge la gestion des bibliothèques et des applications.  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Règle|Description|  
|----------|-----------------|  
|[CA1500 : Les noms de variable ne doivent pas être identiques à des noms de champs](../code-quality/ca1500-variable-names-should-not-match-field-names.md)|Une méthode d’instance déclare un paramètre ou une variable locale dont le nom correspond à un champ d’instance du type déclarant, ce qui entraîne des erreurs.|  
|[CA1501 : Évitez l’excès d’héritage](../code-quality/ca1501-avoid-excessive-inheritance.md)|Un type est imbriqué de plus de quatre niveaux dans sa hiérarchie d'héritage. Les hiérarchies de type profondément imbriquées peuvent être difficiles à suivre, comprendre et gérer.|  
|[CA1502 : Éviter une complexité excessive](../code-quality/ca1502-avoid-excessive-complexity.md)|Cette règle évalue le nombre de chemins linéairement indépendants dans la méthode, déterminé par le nombre et la complexité des branches conditionnelles.|  
|[CA1504 : Vérifiez les noms de champs peu clairs](../code-quality/ca1504-review-misleading-field-names.md)|Le nom d’un champ d’instance commence par « s_ » ou le nom de statique (partagé dans [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) champ commence par « m_ ».|  
|[CA1505 : Évitez le code impossible à maintenir](../code-quality/ca1505-avoid-unmaintainable-code.md)|Un type ou une méthode a une faible valeur d'indice de maintenabilité. Un faible indice de maintenabilité indique qu'un type ou qu'une méthode est probablement difficile à maintenir et qu'il/elle se prête bien à une nouvelle conception.|  
|[CA1506 : Évitez les couplages de classe excessifs](../code-quality/ca1506-avoid-excessive-class-coupling.md)|Cette règle mesure l'accouplement de classes en comptant le nombre de références de type uniques contenues dans un type ou une méthode.|  
  
## <a name="see-also"></a>Voir aussi  
 [Mesures de la complexité et de la facilité de maintenance du code managé](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)



