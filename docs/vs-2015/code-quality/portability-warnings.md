---
title: Avertissements de portabilité | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.PortabilityRules
helpviewer_keywords:
- portability warnings
- managed code analysis warnings, portability warnings
- warnings, portability
ms.assetid: 902e859a-2153-4970-baaa-8a5b4a11806f
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 932474143b4770e81d8bfca14ab05a6538ae84a8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671171"
---
# <a name="portability-warnings"></a>avertissements liés à la portabilité
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Les avertissements de portabilité prennent en charge la portabilité sur différents systèmes d’exploitation.

## <a name="in-this-section"></a>Dans cette section

|Règle|Description|
|----------|-----------------|
|[CA1900 : Les champs de type valeur doivent être portables](../code-quality/ca1900-value-type-fields-should-be-portable.md)|Cette règle vérifie que les structures déclarées à l’aide d’un attribut de disposition explicite s’aligneront correctement lorsqu’elles sont marshalées vers du code non managé sur les systèmes d’exploitation 64 bits.|
|[CA1901 : Les déclarations P/Invoke doivent être portables](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|Cette règle évalue la taille de chaque paramètre et la valeur de retour d’un P/Invoke, puis vérifie que leur taille est correcte lorsqu’elle est marshalée en code non managé sur les systèmes d’exploitation 32 bits et 64 bits.|
|[CA1903 : Utiliser l’API seulement à partir de l’infrastructure cible](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|Un membre ou un type utilise un membre ou un type qui a été introduit dans un Service Pack qui ne figurait pas dans le Framework ciblé du projet.|
