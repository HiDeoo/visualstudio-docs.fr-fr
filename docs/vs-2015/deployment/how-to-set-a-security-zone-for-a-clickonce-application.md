---
title: 'Procédure : Définir une Zone de sécurité pour une Application ClickOnce | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, security settings
- code access security, ClickOnce applications
- security zones, ClickOnce applications
ms.assetid: d3dac454-518a-44d7-a76e-ccb7b9c3a150
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9af4507d7ccd604f82aae675bf87d36c0b039b26
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60110464"
---
# <a name="how-to-set-a-security-zone-for-a-clickonce-application"></a>Procédure : Définir une zone de sécurité pour une application ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Quand vous définissez des autorisations de sécurité d’accès du code pour une application ClickOnce, vous devez d’abord définir un ensemble d’autorisations de base dans la page **Sécurité** du **Concepteur de projet**.  
  
 Dans la plupart des cas, vous pouvez aussi sélectionner la zone **Internet** qui contient un ensemble limité d’autorisations, ou la zone **Intranet local** qui fournit un ensemble plus complet d’autorisations. Si votre application nécessite des autorisations personnalisées, sélectionnez la zone de sécurité **Personnalisée** pour les définir. Pour plus d’informations sur la définition d’autorisations personnalisées, consultez [Comment : Définir des autorisations personnalisées pour une Application ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md).  
  
### <a name="to-set-a-security-zone"></a>Pour définir une zone de sécurité  
  
1. Après avoir sélectionné un projet dans l’ **Explorateur de solutions**, dans le menu **Projet** , cliquez sur **Propriétés**.  
  
2. Cliquez sur l'onglet **Sécurité** .  
  
3. Cochez la case **Activer les paramètres de sécurité ClickOnce** .  
  
4. Sélectionnez la case d’option **Il s’agit d’une application de confiance partielle** .  
  
     Les contrôles de la section **Autorisations de sécurité ClickOnce** sont activés.  
  
5. Dans la liste déroulante **Zone à partir de laquelle votre application sera installée** , sélectionnez une zone de sécurité.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide pratique pour Définir des autorisations personnalisées pour une Application ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Sécurisation des applications ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Sécurité d’accès du code pour les applications ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [Sécurisation des applications ClickOnce](../deployment/securing-clickonce-applications.md)
