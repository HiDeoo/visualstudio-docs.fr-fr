---
title: Déploiement des prérequis pour les Applications 64 bits | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [Visual Studio], 64-bit
- 64-bit [Visual Studio]
- 64-bit programming [Visual Studio]
- 64-bit applications [Visual Studio]
ms.assetid: 87399e20-5510-41e4-b5b7-4a87c5773f21
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 10a5883e655fc5ee8a37bbe61f531b6b266ebb55
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44281887"
---
# <a name="deploy-prerequisites-for-64-bit-applications"></a>Déploiement des prérequis pour les applications 64 bits
Le déploiement ClickOnce prend en charge l'installation des applications sur les plateformes 64 bits. Les plateformes cibles sont **x86** pour les plateformes 32 bits, **x64** pour machines prenant en charge les jeux d’instructions AMD64 et EM64T, et **Itanium** pour le processeur Itanium 64 bits.  
  
## <a name="prerequisites"></a>Prérequis  
 Le tableau suivant répertorie les composants redistribuables que vous pouvez utiliser comme composants requis pour l'installation de votre application 64 bits.  
  
 Si vous sélectionnez un composant requis qui n'a pas de composants 64 bits, vous risquez de voir s'afficher un avertissement indiquant que les packages sélectionnés ne sont pas disponibles pour la plateforme 64 bits.  
  
|Composant redistribuable|Prise en charge x64|Prise en charge IA64|  
|---------------------|-----------------|------------------|  
|[!INCLUDE[vsto_runtime](../deployment/includes/vsto_runtime_md.md)]|Oui|Non|  
|Bibliothèques Runtime Visual C++ 2010 (IA64)|Non|Oui|  
|Bibliothèques Runtime Visual C++ 2010 (x64)|Oui|Non|  
|Microsoft .NET Framework 4 (x86 et x64)|Oui||  
|Microsoft .NET Framework 4 Client Profile (x86 et x64)|Oui||  
  
## <a name="see-also"></a>Voir aussi  
 [Déployer des applications, services et composants](../deployment/deploying-applications-services-and-components.md)   
 [Comment : installer les composants requis avec une application ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [Applications 64 bits](/dotnet/framework/64-bit-apps)