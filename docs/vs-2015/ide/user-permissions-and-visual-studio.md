---
title: Autorisations utilisateur | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, user permissions
- user permissions
- administrative privileges
- permissions
ms.assetid: 70485ed7-6342-41bf-8250-7a6826e21b98
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: aa01cb77e8a003438721984da13f46de350104ea
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75918992"
---
# <a name="user-permissions-and-visual-studio"></a>Autorisations utilisateur et Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour des raisons de sécurité, vous devez exécuter Visual Studio en tant qu'utilisateur normal chaque fois que c'est possible.

> [!WARNING]
> Vous devez également veiller à ne pas compiler, lancer ou déboguer une solution Visual Studio qui ne provient pas d'une personne de confiance ou d'un emplacement de confiance.

 Vous pouvez faire quasiment tout dans l'IDE de Visual Studio comme un utilisateur normal, mais, vous devez avoir des autorisations d'administrateur pour effectuer les tâches suivantes :

|Domaine|Tâche|Informations supplémentaires|
|----------|----------|--------------------------|
|Installation|Installation de Visual Studio.|[Installation de Visual Studio 2015](../install/install-visual-studio-2015.md)|
||Mise à niveau d'une édition d'évaluation de Visual Studio.|[Comment : effectuer une mise à niveau à partir d'une version d'évaluation de Visual Studio](../install/how-to-upgrade-from-a-trial-edition-of-visual-studio.md)|
||Installation, mise à jour ou suppression du contenu d'Aide locale.|[Installer et gérer un contenu local](../ide/install-and-manage-local-content.md)|
|Types d’applications|Développement de solutions SharePoint 2010.|[Configuration requise pour le développement de solutions SharePoint](https://msdn.microsoft.com/library/ae8ff69d-4540-4380-ab0b-845f7108e89c)|
||Acquisition d'une licence de développeur pour [!INCLUDE[win8_appstore_long](../includes/win8-appstore-long-md.md)].|[Obtention d’une licence de développeur (applications Windows Store)](https://msdn.microsoft.com/library/windows/apps/hh974578.aspx)|
|Boîte à outils|Ajout de contrôles COM classiques à la **Boîte à outils**.|[Utilisation de la boîte à outils](../ide/using-the-toolbox.md)|
|Compléments|Installation et utilisation des compléments qui ont été écrits à l'aide de COM classique dans l'IDE.|[Création de compléments et d’Assistants](https://msdn.microsoft.com/library/c5a47c21-6668-4de3-898d-afa969317e73)|
|Génération|Utilisation des événements post-build qui inscrivent un composant.|[Présentation des étapes de génération personnalisée et des événements de build](https://msdn.microsoft.com/library/beb2f017-3e9f-4b2c-9b57-2572fd2628e4)|
||Inclusion d'une étape d'inscription lors de la gestion de projets C++.|[Présentation des étapes de génération personnalisée et des événements de build](https://msdn.microsoft.com/library/beb2f017-3e9f-4b2c-9b57-2572fd2628e4)|
|Débogage|Débogage d'applications exécutées avec des autorisations élevées.|[Paramètres et préparation du débogueur](../debugger/debugger-settings-and-preparation.md)|
||Débogage d’applications exécutées sous un compte utilisateur différent, comme les sites web ASP.NET.|[Débogage d’applications ASP.NET et AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)|
||Débogage dans la zone pour les applications du navigateur XAML (XBAP).|[Hôte WPF (PresentationHost.exe)](https://msdn.microsoft.com/library/3215bfa1-722c-4ac8-a7c5-bdd02d30afbd)|
||Utilisation de l'émulateur pour déboguer des projets de service cloud pour Microsoft Azure.|[Débogage d’un service cloud dans Visual Studio](../azure/vs-azure-tools-debug-cloud-services-virtual-machines.md)|
||Configuration d'un pare-feu pour un débogage distant.|[Configurer les outils de contrôle à distance sur le périphérique](https://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)|
|Outils d'analyse des performances|Profilage d'une application.|[Guide du débutant en profilage des performances](../profiling/beginners-guide-to-performance-profiling.md)|
|Déploiement|Déploiement d'une application web vers les Services IIS (Internet Information Services) sur un ordinateur local.|[Déploiement d’une application Web ASP.NET vers un fournisseur d’hébergement à l’aide de Visual Studio ou Visual Web Developer : déploiement vers IIS comme environnement de test](https://www.asp.net/web-forms/tutorials/deployment/deployment-to-a-hosting-provider/Deployment-to-a-Hosting-Provider-Deploying-to-IIS-as-a-Test-Environment-5-of-12)|
|Envoi de commentaires à Microsoft|Modification de votre mode de participation au Programme d'amélioration du produit Visual Studio.|[Guide pratique : envoyer des commentaires](../misc/how-to-send-feedback-about-visual-studio.md)|

## <a name="running-visual-studio-as-an-administrator"></a>Exécution de Visual Studio comme administrateur
 Lancez Visual Studio avec des autorisations d'administration chaque fois que vous démarrez l'IDE, ou modifiez le raccourci d'application afin qu'il soit toujours exécuté avec des autorisations d'administration. Pour plus d'informations, consultez l'aide de Windows.

#### <a name="to-run-visual-studio-with-administrative-permissions-on-win8-win81-winserver8-or-winblue_server_2"></a>Pour exécuter Visual Studio avec des autorisations d'administration sur [!INCLUDE[win8](../includes/win8-md.md)], [!INCLUDE[win81](../includes/win81-md.md)] ou [!INCLUDE[winserver8](../includes/winserver8-md.md)] ou [!INCLUDE[winblue_server_2](../includes/winblue-server-2-md.md)]

1. Dans l’écran **Démarrer**, tapez **Visual Studio**. Vous devez voir la version ou les versions de Visual Studio que vous avez installées.

2. Sélectionnez la version de Visual Studio que vous souhaitez démarrer, puis affichez le menu contextuel (il s'affiche en bas de l'écran). Sélectionnez **Exécuter en tant qu’administrateur**.

     Au démarrage de Visual Studio, **(Administrateur)** apparaît après le nom de produit dans la barre de titre.

#### <a name="to-run-visual-studio-with-administrative-permissions-on-win7-or-winsvr08_r2"></a>Pour exécuter Visual Studio avec des autorisations d'administration sur [!INCLUDE[win7](../includes/win7-md.md)] ou [!INCLUDE[winsvr08_r2](../includes/winsvr08-r2-md.md)]

1. Dans le menu **Démarrer**, sélectionnez **Tous les programmes**.

2. Dans le dossier **Microsoft Visual Studio** *Version*, sélectionnez **Visual Studio** *Version*, ouvrez le menu contextuel, puis choisissez **Exécuter en tant qu’administrateur**.

     Au démarrage de Visual Studio, **(Administrateur)** apparaît après le nom de produit dans la barre de titre.

## <a name="see-also"></a>Voir aussi
 [Portage, migration et mise à niveau des projets Visual Studio](../porting/porting-migrating-and-upgrading-visual-studio-projects.md) [Installation de Visual Studio 2015](../install/install-visual-studio-2015.md)
