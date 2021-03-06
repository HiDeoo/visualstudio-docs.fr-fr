---
title: Conditions préalables pour le débogage distant d’applications Web | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging ASP.NET Web applications, remote servers
- remote debugging, prerequisites
- remote servers, debugging Web applications
ms.assetid: 1cd777b5-6d20-4ca6-a0df-51653b118469
caps.latest.revision: 30
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c8cbf0ae920be00980d270aae16d5e7d1f7a5313
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72574629"
---
# <a name="prerequisites-for-remote-debugging-web-applications"></a>Prérequis pour le débogage à distance d'applications web
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Avec le débogueur de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], vous pouvez déboguer une application Web de façon transparente, sur l'ordinateur local ou sur un serveur distant. Cela signifie que le débogueur fonctionne de la même façon et vous permet d’utiliser les mêmes fonctionnalités sur l’un ou sur l’autre. Cependant, afin que le débogage distant fonctionne correctement, vous devez respecter certaines conditions.  
  
- Les composants de débogage distant [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] doivent être installés sur le serveur que vous souhaitez déboguer. Pour plus d’informations, consultez [configuration du débogage distant](https://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c).  
  
- Par défaut, le processus de traitement [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] s'exécute comme un processus utilisateur ASPNET. En conséquence, vous devez avoir des privilèges d'administrateur sur l'ordinateur où [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] s'exécute pour le déboguer. Le nom du processus de traitement [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] varie en fonction du scénario de débogage et de la version d'IIS. Pour plus d'informations, consultez [How to: Find the Name of the ASP.NET Process](../debugger/how-to-find-the-name-of-the-aspnet-process.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Débogage d’applications ASP.NET et AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [Configuration requise](../debugger/aspnet-debugging-system-requirements.md)
