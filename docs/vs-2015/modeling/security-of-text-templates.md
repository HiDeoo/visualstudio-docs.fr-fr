---
title: Sécurité des modèles de texte | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, security
ms.assetid: 567a2383-7d43-4acc-af4a-cd70b7a0151e
caps.latest.revision: 25
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e24a90d4e7af351fc4ba5807d2af7830edede9cb
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72671214"
---
# <a name="security-of-text-templates"></a>Sécurité des modèles de texte
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Les modèles de texte présentent les problèmes de sécurité suivants :

- Les modèles de texte sont vulnérables aux insertions de code arbitraires.

- Si le mécanisme utilisé par l’hôte pour rechercher un processeur de directive n’est pas sécurisé, un processeur de directive malveillant peut être exécuté.

## <a name="arbitrary-code"></a>Code arbitraire
 Lorsque vous écrivez un modèle, vous pouvez placer n’importe quel code dans les \<# #> balises. Cela permet d’exécuter du code arbitraire à partir d’un modèle de texte.

 Veillez à obtenir des modèles à partir de sources approuvées. Veillez à prévenir les utilisateurs finaux de votre application de ne pas exécuter les modèles qui ne proviennent pas de sources approuvées.

## <a name="malicious-directive-processor"></a>Processeur de directive malveillant
 Le moteur de modèle de texte interagit avec un hôte de transformation et un ou plusieurs processeurs de directive pour transformer le texte du modèle en fichier de sortie. Pour plus d’informations, consultez [processus de transformation de modèle de texte](../modeling/the-text-template-transformation-process.md).

 Si le mécanisme utilisé par l’hôte pour rechercher un processeur de directive n’est pas sécurisé, il risque d’exécuter un processeur de directive malveillant. Le processeur de directive malveillant peut fournir du code qui est exécuté en `FullTrust` mode lors de l’exécution du modèle. Si vous créez un hôte de transformation de modèle de texte personnalisé, vous devez utiliser un mécanisme sécurisé, tel que le registre, pour que le moteur localise les processeurs de directive.
