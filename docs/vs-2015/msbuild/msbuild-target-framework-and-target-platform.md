---
title: Framework cible et plateforme cible (MSBuild) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
ms.assetid: df6517c5-edd6-4cc4-97ad-b3cdfc78e799
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1a550b4a6634604594da0893e3f420fd9c38ca3c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68181017"
---
# <a name="msbuild-target-framework-and-target-platform"></a>Framework cible et plateforme cible (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Un projet peut être généré pour s’exécuter sur un *framework cible*, qui est une version particulière du .NET Framework, et sur une *plateforme cible*, qui est une architecture logicielle particulière.  Par exemple, vous pouvez cibler une application pour qu'elle s'exécute sur le .NET Framework 2.0, sur une plateforme 32 bits qui est compatible avec la famille de processeurs 802x86 (« x86 »). La combinaison de framework cible et de plateforme cible porte le nom de *contexte cible*.  
  
## <a name="target-framework-and-profile"></a>Version cible du .NET Framework et profil cible  
 Une version cible du .NET Framework est la version particulière du [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] sur laquelle le projet généré doit s'exécuter. La spécification d'une version cible du .NET Framework est nécessaire, car elle active des fonctionnalités du compilateur et des références d'assemblys qui sont spécifiques à cette version du .NET Framework.  
  
 Les versions du .NET Framework actuellement disponibles sont les suivantes :  
  
- [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 2.0 (inclus dans Visual Studio 2005)  
  
- [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 3.0 (inclus dans [!INCLUDE[wiprlhext](../includes/wiprlhext-md.md)])  
  
- [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 3.5 (inclus dans [!INCLUDE[vs_orcas_long](../includes/vs-orcas-long-md.md)])  
  
- [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 4 (inclus dans Visual Studio 2010)  
  
- [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 4.5 (inclus dans [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)])  
  
- [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 4.5.1 (inclus dans [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)])  
  
- [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 4.5.2  
  
- [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 4.6 (inclus dans [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)])  
  
  Les versions du .NET Framework diffèrent l'une de l'autre quant à la liste d'assemblys que vous pouvez référencer. Par exemple, vous ne pouvez créer des applications Windows Presentation Foundation (WPF) que si votre projet cible le .NET Framework version 3.0 ou supérieure.  
  
  La version cible du .NET Framework est spécifiée dans la propriété `TargetFrameworkVersion` du fichier projet. Vous pouvez changer la version cible du .NET Framework pour un projet en utilisant les pages des propriétés du projet dans l'environnement de développement intégré (IDE) Visual Studio. Pour plus d’informations, consultez [Comment : cibler une version du .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md). Les valeurs disponibles pour `TargetFrameworkVersion` sont `v2.0`, `v3.0`, `v3.5`, `v4.0`, `v4.5`, `v4.5.1`, `v4.5.2` et `v4.6`.  
  
```  
<TargetFrameworkVersion>v4.0</TargetFrameworkVersion>  
```  
  
 Un *profil cible* est un sous-ensemble d’un framework cible. Par exemple, le profil Client .NET Framework 4 n'inclut pas de références aux assemblys MSBuild.  
  
 Le profil cible est spécifié dans la propriété `TargetFrameworkProfile` d'un fichier projet. Vous pouvez changer le profil cible en utilisant le contrôle de la version cible du .NET Framework dans les pages des propriétés du projet dans l'IDE. Pour plus d’informations, consultez [Comment : cibler une version du .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
```  
<TargetFrameworkVersion>v4.0</TargetFrameworkVersion>  
<TargetFrameworkProfile>Client</TargetFrameworkProfile>  
```  
  
## <a name="target-platform"></a>Plateforme cible  
 Une *plateforme* est une combinaison de matériel et de logiciel qui définit un environnement d’exécution spécifique. Par exemple,  
  
- `x86` désigne un système d'exploitation Windows 32 bits qui s'exécute sur un processeur Intel 80x86 ou son équivalent.  
  
- `Xbox` désigne la plateforme Microsoft Xbox 360.  
  
  Une *plateforme cible* est la plateforme particulière sur laquelle votre projet généré doit s’exécuter. La plateforme cible est spécifiée dans la propriété de build `Platform` d'un fichier projet. Vous pouvez changer la plateforme cible en utilisant les pages de propriétés du projet ou le **Gestionnaire de configurations** dans l’IDE.  
  
```  
<PropertyGroup>  
   <Platform>x86</Platform>  
</PropertyGroup>  
  
```  
  
 Une *configuration cible* est un sous-ensemble d’une plateforme cible. Par exemple, la configuration `x86``Debug` n’inclut pas la plupart des optimisations du code. La configuration cible est spécifiée dans la propriété de build `Configuration` d'un fichier projet. Vous pouvez changer la configuration cible en utilisant les pages de propriétés du projet ou le **Gestionnaire de configurations**.  
  
```  
<PropertyGroup>  
   <Platform>x86</Platform>  
   <Configuration>Debug</Configuration>  
<PropertyGroup>  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [MULTICIBLAGE](../msbuild/msbuild-multitargeting-overview.md)
