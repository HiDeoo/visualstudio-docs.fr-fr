---
title: Numéros de version de l’assembly principal et des assemblys satellites localisés | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- satellite assemblies, version numbers
- SatelliteContractVersionAttribute
- version numbers, assemblies
- assemblies [Visual Studio], version numbers
- versioning, assemblies
ms.assetid: 5489aea1-57b4-4561-9bb4-24d490269602
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a5c6d5e16a77a8c04964beb38e21ebf82ede7f0b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49223039"
---
# <a name="version-numbers-for-main-and-localized-satellite-assemblies"></a>Numéros de version de l'assembly principal et des assemblys satellites localisés
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La classe <xref:System.Resources.SatelliteContractVersionAttribute> fournit la prise en charge de la gestion de version pour un assembly principal qui utilise des ressources localisées via le Gestionnaire des ressources. L’application d’un <xref:System.Resources.SatelliteContractVersionAttribute> à l’assembly principal d’une application permet de mettre à jour et de redéployer cet assembly, sans mettre à jour ses assemblys satellites. Par exemple, vous pouvez utiliser la classe <xref:System.Resources.SatelliteContractVersionAttribute> avec un Service Pack qui n’introduit pas de nouvelles ressources sans régénérer et redéployer vos assemblys satellites. Pour que vos ressources localisées soient disponibles, la version de contrat satellite de votre assembly principal doit correspondre à la classe <xref:System.Reflection.AssemblyVersionAttribute> de vos assemblys satellites. Vous devez spécifier un numéro de version exact dans la classe <xref:System.Resources.SatelliteContractVersionAttribute> ; les caractères génériques tels que « * » ne sont pas autorisés. Pour plus d’informations, consultez [Récupération de ressources](http://msdn.microsoft.com/library/eca16922-1c46-4f68-aefe-e7a12283641f).  
  
## <a name="updating-assemblies"></a>Mise à jour des assemblys  
 La classe <xref:System.Resources.SatelliteContractVersionAttribute> permet de mettre à jour un assembly principal sans avoir à mettre à jour les assemblys satellites, et vice versa. Lorsque l’assembly principal est mis à jour, son numéro de version est modifié. Si vous souhaitez continuer à utiliser les assemblys satellites existants, modifiez le numéro de version de l’assembly principal, mais conservez le numéro de version de contrat satellite. Par exemple, dans votre première version, la version de l’assembly principal peut être 1.0.0.0. Dans ce cas, la version de contrat satellite et la version d’assembly de l’assembly satellite seront également 1.0.0.0. Si vous devez mettre à jour votre assembly principal pour un Service Pack, vous pouvez remplacer la version d’assembly par 1.0.0.1, tout en conservant la valeur 1.0.0.0 pour la version de contrat satellite et la version d’assembly du satellite.  
  
 Si vous devez mettre à jour un assembly satellite, mais pas votre assembly principal, modifiez le <xref:System.Reflection.AssemblyVersionAttribute> de l’assembly satellite. En même temps que votre assembly satellite, vous devez livrer un assembly de stratégie indiquant que votre nouvel assembly satellite est compatible avec votre ancien assembly satellite. Pour plus d’informations, consultez [Méthode de localisation des assemblys par le runtime](http://msdn.microsoft.com/library/772ac6f4-64d2-4cfb-92fd-58096dcd6c34).  
  
 Le code suivant montre la définition d’une version de contrat satellite. Le code peut être placé dans un script de build, ou dans le fichier AssemblyInfo.vb ou AssemblyInfo.cs.  
  
```vb  
<Assembly: SatelliteContractVersionAttribute("4.3.2.1")>  
  
```  
  
```csharp  
[assembly: SatelliteContractVersionAttribute("4.3.2.1")]  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Méthode de localisation des assemblys par le runtime](http://msdn.microsoft.com/library/772ac6f4-64d2-4cfb-92fd-58096dcd6c34)   
 [Définition des attributs d’assembly](http://msdn.microsoft.com/library/36a98a81-b5b5-4c19-912a-11f91eff7f4e)   
 [Sécurité et assemblys satellites localisés](../ide/security-and-localized-satellite-assemblies.md)   
 [Localisation d’applications](../ide/localizing-applications.md)   
 [Globalisation et localisation d’applications](../ide/globalizing-and-localizing-applications.md)

