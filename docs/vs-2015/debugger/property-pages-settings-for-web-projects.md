---
title: Paramètres des pages de propriétés pour les projets Web | Microsoft Docs
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
- debugging [Visual Studio], Web applications
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- debugging Web applications, project settings
- debug configurations, Web projects
ms.assetid: 8ec5160a-6408-4f47-8d41-f0e20e79a3b9
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3cb7cd3f8c3678d37feb2267f68ab5d2b3d970e0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68150856"
---
# <a name="property-pages-settings-for-web-projects"></a>Paramètres des pages de propriétés pour les projets Web
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez modifier les paramètres de propriété de configuration Debug d’un site web dans la boîte de dialogue **Pages de propriétés**, comme indiqué dans [Configurations Debug et Release](../debugger/how-to-set-debug-and-release-configurations.md). Les tableaux suivants indiquent où se trouvent les paramètres du débogueur dans la boîte de dialogue **Pages de propriétés**.  
  
### <a name="configuration-properties-folder-start-options-category"></a>Dossier Propriétés de configuration (catégorie Options de démarrage)  
  
|**Paramètre**|**Description**|  
|-----------------|---------------------|  
|**Action de démarrage**|Titre qui regroupe les options liées au démarrage d'une application.|  
|**Utiliser la page active**|Spécifie la page active comme point de départ du débogage.|  
|**Page spécifique :**|Spécifie la page web à partir de laquelle vous voulez débuter le débogage.|  
|**Démarrer le programme externe :**|Spécifie la commande de lancement du programme que vous voulez déboguer.|  
|**Arguments de ligne de commande :**|Spécifie les arguments de la commande spécifiée ci-dessus.|  
|**Répertoire de travail :**|Spécifie le répertoire de travail du programme en cours de débogage. En [!INCLUDE[csprcs](../includes/csprcs-md.md)], le répertoire de travail est celui à partir duquel l'application est lancée : \bin\debug par défaut.|  
|**URL de démarrage**|Spécifie l'emplacement de l'application Web que vous voulez déboguer.|  
|**N’ouvrez pas une page. Attendre une demande émanant d’une application externe**|Indique d'attendre une demande émanant d'une application externe. Cette option ne lance pas Internet Explorer ou une autre application. Elle prépare simplement au débogage en cas d'appel par une application.|  
|**Serveur**|Titre qui regroupe des options liées au serveur à utiliser.|  
|**Utiliser le serveur Web par défaut**|Indique d'utiliser le serveur Web par défaut.|  
|**Utiliser le serveur personnalisé**|Vous permet d'entrer l'URL de base à utiliser comme serveur.|  
|**Débogueurs**|Titre qui regroupe des options liées au type de débogage à réaliser.|  
|**Débogage ASP.NET**|Active le débogage des pages ASP écrites pour la plateforme de développement [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]. Vous devez spécifier une URL dans **URL de démarrage**.|  
|**Débogage du code natif**|Vous permet de déboguer les appels au code Win32 natif (non managé) à partir de votre application managée.|  
|**Débogage SQL Server**|Autorise le débogage d'objets de base de données SQL Server.|  
|**Débogage Silverlight**|Autorise le débogage de composants Silverlight.|  
  
## <a name="see-also"></a>Voir aussi  
 [Paramètres et préparation du débogueur](../debugger/debugger-settings-and-preparation.md)
