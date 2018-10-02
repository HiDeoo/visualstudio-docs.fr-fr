---
title: '&lt;assemblyIdentity&gt; , élément (déploiement ClickOnce) | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assemblyIdentity> element [ClickOnce deployment manifest]
ms.assetid: f4a3bb83-c800-47d0-9905-9a5ae2486838
caps.latest.revision: 25
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 4b1f5a0dbf056925b4f2a25356759dccacc3b363
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47493180"
---
# <a name="ltassemblyidentitygt-element-clickonce-deployment"></a>&lt;assemblyIdentity&gt; , élément (déploiement ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [ &lt;assemblyIdentity&gt; , élément (déploiement ClickOnce)](https://docs.microsoft.com/visualstudio/deployment/assemblyidentity-element-clickonce-deployment).  
  
Identifie l’assembly principal de le [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <assemblyIdentity    
   name   
   version  
   publicKeyToken  
   processorArchitecture  
    type  
/>  
```  
  
## <a name="elements-and-attributes"></a>Éléments et attributs  
 Le `assemblyIdentity` élément est requis. Il ne contient aucun élément enfant et a les attributs suivants.  
  
|Attribut|Description|  
|---------------|-----------------|  
|`name`|Obligatoire. Identifie le nom explicite du déploiement à titre d’information.<br /><br /> Si `name` contient des caractères spéciaux, tels que des guillemets simples ou doubles, l’application peut échouer à activer.|  
|`version`|Obligatoire. Spécifie le numéro de version de l’assembly, au format suivant : `major.minor.build.revision`.<br /><br /> Cette valeur doit être incrémentée dans un manifeste mis à jour pour déclencher une mise à jour de l’application.|  
|`publicKeyToken`|Obligatoire. Spécifie une chaîne hexadécimale de 16 caractères qui représente les 8 derniers octets de la valeur de hachage SHA-1 de la clé publique sous laquelle le manifeste de déploiement est signé. La clé publique qui est utilisée pour signer doit être de 2 048 bits ou supérieur.<br /><br /> Bien que la signature d’un assembly est recommandé mais facultatif, cet attribut est requis. Si un assembly n’est pas signé, vous devez copier une valeur à partir d’un assembly auto-signé ou utiliser une valeur « factice » de tous les zéros non significatifs.|  
|`processorArchitecture`|Obligatoire. Spécifie le processeur. Les valeurs valides sont `msil` pour tous les processeurs, `x86` pour Windows 32 bits, `IA64` pour Windows 64 bits, et `Itanium` pour les processeurs Itanium d’Intel 64 bits.|  
|`type`|Obligatoire. Pour assurer la compatibilité avec la technologie d’installation de côte à côte de Windows. La seule valeur autorisée est `win32`.|  
  
## <a name="remarks"></a>Notes  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant illustre un `assemblyIdentity` élément dans un [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] manifeste de déploiement. Cet exemple de code fait partie d’un exemple plus complet fourni pour le [du manifeste de déploiement ClickOnce](../deployment/clickonce-deployment-manifest.md) rubrique.  
  
```  
<!-- Identify the deployment. -->  
<assemblyIdentity   
  name="My Application Deployment.app"  
  version="1.0.0.0"  
  publicKeyToken="43cb1e8e7a352766"  
  language="neutral"  
  processorArchitecture="x86"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Manifeste de déploiement ClickOnce](../deployment/clickonce-deployment-manifest.md)   
 [\<assemblyIdentity > élément](../deployment/assemblyidentity-element-clickonce-application.md)



