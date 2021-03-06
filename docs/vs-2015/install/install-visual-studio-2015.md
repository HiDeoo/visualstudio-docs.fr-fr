---
title: Installer Visual Studio 2015 │ Microsoft Docs
titleSuffix: ''
ms.date: 04/15/2020
ms.prod: visual-studio-dev14
ms.technology: vs-ide-install
ms.topic: conceptual
f1_keywords:
- vs.about
helpviewer_keywords:
- Visual Studio, installing
- installing Visual Studio
- server installations [Visual Studio]
- Setup [Visual Studio]
- install Visual Studio
- visual studio installer
ms.assetid: da049020-cfda-40d7-8ff4-7492772b620f
caps.latest.revision: 183
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: d593625985924d8c8076e1bdd361ce4d08c1dfbc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85548042"
---
# <a name="install-visual-studio-2015"></a>Installer Visual Studio 2015

[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette page comprend des informations détaillées qui vous aideront à installer **Visual Studio 2015**, notre suite intégrée d’outils de productivité pour les développeurs. Nous avons également inclus des liens pour vous aider à accéder rapidement à des informations sur les [fonctionnalités](https://docs.microsoft.com/visualstudio/releasenotes/vs2015-version-history), la [Configuration requise](https://docs.microsoft.com/visualstudio/productinfo/vs2015-sysrequirements-vs), les [téléchargements](https://visualstudio.microsoft.com/vs/older-downloads/)et bien plus encore.

## <a name="quick-links"></a>Liens rapides

Avant d’entrer dans les détails, voici une liste de nos liens les plus demandés.

|Titre|Description|
|------------------|----------------|
|![Télécharger Visual Studio](../install/media/downloads.png "Téléchargements") |**Téléchargements**: pour installer Visual Studio 2015, vous pouvez télécharger un fichier exécutable du produit à partir de la page  [My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20enterprise%202015) (abonnement requis) ou utiliser le support d’installation à partir du produit boxed. [En savoir plus sur le téléchargement des versions actuelles ou précédentes de Visual Studio](https://www.visualstudio.com/vs/older-downloads/).|
|![En savoir plus sur les fonctionnalités](../install/media/features.png "Fonctionnalités") |**Fonctionnalités**: pour en savoir plus sur les fonctionnalités de Visual Studio 2015, consultez les notes de publication pour [RTM](https://docs.microsoft.com/visualstudio/releasenotes/vs2015-rtm-vs), [Update 1](https://docs.microsoft.com/visualstudio/releasenotes/vs2015-update1-vs), [Update 2](https://docs.microsoft.com/visualstudio/releasenotes/vs2015-update2-vs)et [Update 3](https://docs.microsoft.com/visualstudio/releasenotes/vs2015-update3-vs).|
|![Afficher la configuration système requise](../install/media/system-requirements.png "Configuration système requise") |**Configuration système requise**: pour afficher la configuration système requise pour chaque édition de visual studio 2015, consultez la page [ciblage et compatibilité de la plateforme Visual Studio 2015](https://www.visualstudio.com/products/visual-studio-2015-compatibility-vs) .|
|![Localiser votre clé de produit](../install/media/product-keys.png "Clés de produit") |**Clés de produit**: pour localiser votre clé de produit, consultez la rubrique [Comment : localiser la clé de produit Visual Studio](../install/how-to-locate-the-visual-studio-product-key.md) .|
|![En savoir plus sur les licences](../install/media/licensing.png "Licences") |**Licence**: pour en savoir plus sur les options de licence pour les particuliers ou les clients d’entreprise, consultez le livre blanc sur les [licences Visual Studio 2015](https://www.microsoft.com/download/details.aspx?id=13350).|

## <a name="default-vs-custom-setup"></a><a name="custom"></a> Configuration par défaut et installation personnalisée
 Au moment d’installer Visual Studio 2015, vous pouvez inclure les composants que vous prévoyez d’utiliser au quotidien et exclure les autres. Cela signifie qu’une installation par défaut sera souvent plus petite et plus rapide à installer qu’une installation personnalisée. Cela signifie aussi que bon nombre de composants qui étaient installés par défaut dans les versions précédentes sont maintenant considérés comme des composants personnalisés que vous devez sélectionner explicitement dans cette version.

 ![Boîte de dialogue d'installation de Visual Studio 2015](../ide/media/vs2015-setup-screen.png "VS2015_Setup_screen")

 Les composants personnalisés incluent Visual C++, les Visual F#, les SQL Server Data Tools, les outils mobiles multiplateforme et les kits de développement logiciel (SDK) et extensions tierces. Vous pouvez installer les composants personnalisés ultérieurement si vous ne les sélectionnez pas pendant l’installation initiale.

> [!NOTE]
> Une installation personnalisée inclut automatiquement les composants qui figurent dans une installation par défaut.

 Voici la liste complète des composants personnalisés :

|Ensembles de fonctionnalités|Components|
|------------------|----------------|
|**Mises à jour**|Visual Studio 2015 Update 3|
|**Langages de programmation**|Visual C++<br />Visual F#<br />Python Tools for Visual Studio|
|**Développement Windows et web**|Outils de publication de ClickOnce<br />LightSwitch<br />Outils de développement Microsoft Office<br />Microsoft SQL Server Data Tools<br /> Microsoft Web Developer Tools<br />PowerShell Tools for Visual Studio (tiers)<br />Kit de développement Silverlight<br />Outils de développement d’applications Windows universelles<br />Kits de développement logiciel (SDK) et outils Windows 10<br />Outils Windows 8.1 et Windows Phone 8.0/8.1<br />Kits de développement logiciel (SDK) et outils Windows 8.1|
|**Développement multiplateforme pour appareils mobiles**|C#/.NET (Xamarin)<br />HTML/JavaScript (Apache Cordova)<br />Développement mobile Visual C++ pour iOS / Android<br />Clang avec Microsoft CodeGen|
|**Outils courants et kits de développement logiciel**|Android Native Development Kit (3e tiers)<br /> Android SDK [tiers]<br />API d’installation Android SDK (tierce)<br />Apache Ant (tiers)<br /> Java SE Development Kit (tiers)<br /> Joyent Node.js (tiers)|
|**Outils courants**|Git pour Windows (tiers)<br />Extension GitHub pour Visual Studio (tiers)<br /> Outils d'extensibilité de Visual Studio|

## <a name="install-visual-studio"></a><a name="installing"></a> Installer Visual Studio
 Vous pouvez installer Visual Studio à l’aide du support d’installation (DVD), à l’aide de votre service d’abonnement Visual Studio à partir du site Web [My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20enterprise%202015) , en téléchargeant un programme d’installation Web à partir du site Web de [téléchargements de Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/) ou en créant une disposition d’installation hors connexion (consultez la page [créer une installation hors connexion de Visual Studio](../install/create-an-offline-installation-of-visual-studio.md) pour plus d’informations).

> [!IMPORTANT]
> Vous avez besoin d’informations d’identification d’administrateur pour installer [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Toutefois, elles ne sont pas requises pour utiliser [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] après son installation.

 Les privilèges suivants de votre compte d'administrateur local doivent autoriser l'installation de tous les composants de Visual Studio.

|Nom d'affichage de l'objet de stratégie locale|Droit d'utilisateur|
|--------------------------------------|----------------|
|Sauvegarder les fichiers et les répertoires|SeBackupPrivilege|
|Déboguer les programmes|SeDebugPrivilege|
|Gérer le journal d'audit et de sécurité|SeSecurityPrivilege|

 Pour plus d’informations sur cette exigence de compte d’administrateur local, consultez l’article suivant de la Base de connaissances : [Échec de l’installation de SQL Server si le compte d’installation ne possède pas certains droits d’utilisateur](https://support.microsoft.com/kb/2000257).

### <a name="use-installation-media"></a><a name="BKMK_Media"></a> Utiliser le support d’installation
 Pour installer [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], dans le répertoire racine du support d'installation de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , exécutez le fichier d'installation de l'édition souhaitée :

|Édition|Fichier d'installation|
|-------------|-----------------------|
|Visual Studio Enterprise|vs_enterprise.exe|
|Visual Studio Professional|vs_professional.exe|
|Communauté Visual Studio|vs_community.exe|

### <a name="download-from-the-product-website"></a><a name="BKMK_Website"></a> Télécharger à partir du site Web du produit
 Accédez à la page [téléchargements Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/) , puis sélectionnez l’édition de Visual Studio souhaitée.

### <a name="download-from-your-subscription-service"></a>Télécharger à partir de votre service d’abonnement
 Accédez à la page [My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20enterprise%202015) , puis sélectionnez l’édition de Visual Studio souhaitée.

### <a name="create-an-offline-installation-layout"></a><a name="BKMK_Offline"></a> Créer une disposition d’installation hors connexion
 Si vous ne disposez pas du [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] support d’installation, ou si vous n’avez pas d’abonnement Visual Studio, ou si vous ne souhaitez pas installer à [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] l’aide du programme d’installation Web, vous pouvez effectuer une installation « déconnectée » en créant ce que l’on appelle une disposition d’installation hors connexion. Pour plus d’informations, consultez la page [créer une installation hors connexion de Visual Studio](../install/create-an-offline-installation-of-visual-studio.md) .

## <a name="deploy-visual-studio-in-an-enterprise"></a><a name="enterprise"></a> Déployer Visual Studio dans une entreprise
 Pour plus d’informations sur [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] le déploiement sur un réseau, consultez le Guide de l' [Administrateur Visual Studio](../install/visual-studio-administrator-guide.md).

### <a name="install-visual-studio-in-a-virtualized-environment"></a><a name="BKMK_Virtualized"></a> Installer Visual Studio dans un environnement virtualisé
 **Problèmes vidéo avec Hyper-V**

 Si vous exécutez Windows Server 2008 R2 avec Hyper-V activé et une carte graphique accélérée, il se peut que vous rencontriez des ralentissements du système.

 Pour plus d’informations, consultez [performances vidéo pouvant diminuer lorsqu’un ordinateur Windows server 2008 ou Windows server 2008 R2 a le rôle Hyper-V activé et une carte graphique accélérée installée](https://support.microsoft.com/kb/961661).

 **Émulation d’appareils avec Hyper-V**

 Quand vous installez Visual Studio 2015 sur du vrai matériel, sans virtualisation, vous pouvez choisir les fonctionnalités qui permettent d'émuler les appareils Windows et Android avec Hyper-V. En revanche, quand vous effectuez l'installation dans Hyper-V, vous ne pouvez pas émuler les appareils Windows ou Android. Ceci est dû au fait que les émulateurs sont eux-mêmes des machines virtuelles et que vous ne pouvez pas héberger actuellement une machine virtuelle à l'intérieur d'une autre machine virtuelle. Une solution de contournement consiste à faire l'acquisition d'appareils Windows ou Android sur lesquels vous pouvez directement déployer et déboguer votre application.

## <a name="install-optional-components"></a><a name="optionalComponents"></a> Installer les composants facultatifs
 Si vous souhaitez installer des composants que vous n’avez peut-être pas sélectionnés lors de l’installation d’origine, utilisez la procédure suivante.

#### <a name="to-install-optional-components"></a>Pour installer des composants facultatifs

1. Dans **Panneau de configuration**, dans la page **Programmes et fonctionnalités** , sélectionnez l'édition du produit à laquelle vous souhaitez ajouter un ou plusieurs composants, puis cliquez sur **Modifier**.

2. Dans l'Assistant Installation, sélectionnez **Modifier**, puis sélectionnez les composants que vous souhaitez installer.

3. Choisissez **Suivant**, puis suivez les instructions restantes.

## <a name="install-offline-help-content"></a><a name="helpContent"></a> Installer le contenu d’aide hors connexion
 Après avoir installé [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], vous pouvez télécharger le contenu d'aide supplémentaire afin qu'il soit disponible hors connexion.

#### <a name="to-install-or-uninstall-help-content"></a>Pour installer ou désinstaller le contenu de l'aide

1. Dans la barre de menus [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , choisissez **Aide**, **Ajouter et supprimer le contenu d'aide**.

2. Sous l'onglet **Gérer le contenu** de la **Visionneuse d'aide Microsoft**, sélectionnez la source d'installation pour votre contenu d'aide.

3. Si vous recherchez une collection d’aide spécifique, entrez le nom ou le mot clé dans la zone de texte **Rechercher**, puis appuyez sur **Entrée**.

4. À côté du nom de la collection d'aide souhaitée, choisissez le lien **Ajouter** ou **Supprimer** .

5. Cliquez sur le bouton **Mettre à jour**.

   Pour plus d’informations sur l’installation ou le déploiement de l’aide en mode hors connexion, consultez le Guide de l’administrateur de la [visionneuse d’aide](../ide/help-viewer-administrator-guide.md).

## <a name="check-for-service-releases-and-product-updates"></a><a name="serviceReleases"></a> Rechercher les versions de service et les mises à jour du produit
 Comme les extensions ne sont pas toutes compatibles, Visual Studio ne met pas automatiquement à niveau les extensions quand vous effectuez une mise à niveau de versions antérieures. Vous devez réinstaller les extensions à partir du [Visual Studio Marketplace](https://marketplace.visualstudio.com/) ou de l’éditeur de logiciel.

#### <a name="to-automatically-check-for-service-releases"></a>Pour rechercher automatiquement les publications du service

1. Dans la barre de menus, choisissez **Outils**, **options**.

2. Dans la boîte de dialogue **Options** , développez **Environnement**, puis sélectionnez **Extensions et mises à jour**. Assurez-vous de cocher la case **Rechercher automatiquement les mises à jour** , puis choisissez **OK**.

## <a name="register-visual-studio"></a>Inscrire Visual Studio

1. Dans la barre de menus, choisissez **Aide**, **À propos de**.

     La boîte de dialogue **À propos de** affiche le numéro d'identification du produit (PID). Vous avez besoin du PID et des informations d'identification d'un compte Windows (telles qu'une adresse de messagerie Hotmail ou Outlook.com et un mot de passe) pour inscrire le produit.

2. Dans la barre de menus, cliquez sur **Aide**, puis sur **Inscrire le produit**.

## <a name="repair-visual-studio"></a><a name="repair"></a> Réparer Visual Studio

#### <a name="to-repair-visual-studio"></a>Pour réparer Visual Studio

1. Dans le **Panneau de configuration**, dans la page **Programmes et fonctionnalités** , sélectionnez l'édition du produit que vous souhaitez réparer, puis sélectionnez **Modifier**.

2. Dans l'Assistant Installation, sélectionnez **Réparer**, **Suivant**, puis suivez les instructions restantes.

#### <a name="to-repair-visual-studio-in-silent-or-passive-modes-that-is-to-repair-from-source"></a>Pour réparer Visual Studio en mode silencieux ou passif (autrement dit, pour réparer à partir de la source)

1. Sur l'ordinateur où Visual Studio est installé, ouvrez l'invite de commandes Windows.

2. Entrez les paramètres suivants :

     *DVDRoot* \\ DVDRoot < *Fichier* \> d’installation \<`/quiet|/passive`> [/`norestart`]/`Repair`

## <a name="troubleshoot-an-installation"></a><a name="troubleshooting"></a> Résoudre les problèmes d’installation
 Utilisez ces ressources pour obtenir de l'aide sur les problèmes de configuration et d'installation.

- Forum[Installation et configuration de Visual Studio](https://social.msdn.microsoft.com/Forums/en-US/vssetup/threads) . Passez en revue les questions et les réponses des autres dans la communauté Visual Studio. Si vous ne trouvez pas ce dont vous avez besoin, posez vos propres questions.

- [Obtenir de l’aide sur Visual Studio](https://visualstudio.microsoft.com/vs/support/vs2015/). Recherchez des Articles de la base de connaissances et apprenez à contacter Support Microsoft pour plus d’informations sur les problèmes liés à l’installation de Visual Studio.

## <a name="related-topics"></a><a name="relatedTopics"></a> Rubriques connexes

|Titre|Description|
|-----------|-----------------|
|[Créer une installation hors connexion de Visual Studio](../install/create-an-offline-installation-of-visual-studio.md)|Décrit comment installer Visual Studio lorsque vous n’êtes pas connecté à Internet.
|[Installer les versions de Visual Studio côte à côte](../install/install-visual-studio-versions-side-by-side.md)|Fournit des informations concernant l’installation de plusieurs versions de Visual Studio sur le même ordinateur.|
|[Utiliser des paramètres de ligne de commande pour installer Visual Studio](/visualstudio/install/use-command-line-parameters-to-install-visual-studio)|Répertorie les paramètres de ligne de commande que vous pouvez utiliser lorsque vous installez Visual Studio à partir d’une invite de commandes.|
|[Désinstaller Visual Studio](../install/uninstall-visual-studio.md)|Décrit comment désinstaller Visual Studio.|
|[Guide de l’Administrateur Visual Studio](../install/visual-studio-administrator-guide.md)|Fournit des informations concernant des options de déploiement pour Visual Studio.|
|[Bibliothèque d’images Visual Studio](../designers/the-visual-studio-image-library.md)|Fournit des informations concernant l’installation de graphiques qui peuvent être utilisés dans les applications Visual Studio.|
|[Prise en main du développement avec Visual Studio](../ide/get-started-developing-with-visual-studio.md)|Contient des informations et des liens qui peuvent vous aider à utiliser plus efficacement Visual Studio.|

## <a name="see-also"></a>Voir aussi

- [Connexion à Visual Studio](../ide/signing-in-to-visual-studio.md)
