---
title: 'Procédure pas à pas : Déploiement manuel d’une Application ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Mage.exe, manual ClickOnce deployments
- MageUI.exe, manual ClickOnce deployments
- deploying applications [ClickOnce], manual ClickOnce deployments
- ClickOnce deployment, manually
- ClickOnce deployment, SDK tools
- manual ClickOnce deployments
- manifests [ClickOnce]
ms.assetid: ccee6551-a1b9-4ca2-8845-9c1cf4ac2560
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4f01b4cb17dd51c9da3e74620f9c25b7a3764566
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39155488"
---
# <a name="walkthrough-manually-deploy-a-clickonce-application"></a>Procédure pas à pas : Déployer manuellement une application ClickOnce
Si vous ne pouvez pas utiliser Visual Studio pour déployer votre [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] application, ou vous devez utiliser les fonctionnalités de déploiement avancées comme le déploiement d’applications approuvées, vous devez utiliser le *Mage.exe* outil de ligne de commande pour créer votre [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestes. Cette procédure pas à pas décrit comment créer un [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] déploiement à l’aide de la version de ligne de commande (*Mage.exe*) ou la version graphique (*MageUI.exe*) de la génération de manifeste et Outil d’édition.  
  
## <a name="prerequisites"></a>Prérequis  
 Cette procédure pas à pas a certaines conditions préalables et les options dont vous avez besoin pour choisir avant de générer un déploiement.  
  
-   Installer *Mage.exe* et *MageUI.exe*.  
  
     *Mage.exe* et *MageUI.exe* font partie de la [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Vous devez disposer du [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] installé ou la version de la [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] inclus avec Visual Studio. Pour plus d’informations, consultez [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=158044) sur MSDN.  
  
-   Fournir une application à déployer.  
  
     Cette procédure pas à pas suppose que vous disposez d’une application Windows que vous êtes prêt à déployer. Cette application sera appelée AppToDeploy.  
  
-   Déterminez comment le déploiement sera distribué.  
  
     Les options de distribution incluent : Web, partage de fichiers ou CD. Pour plus d'informations, consultez [ClickOnce Security and Deployment](../deployment/clickonce-security-and-deployment.md).  
  
-   Déterminer si l’application requiert un niveau élevé de confiance.  
  
     Si votre application exige une confiance totale, par exemple, un accès complet au système de l’utilisateur, vous pouvez utiliser la `-TrustLevel` option de *Mage.exe* définir cette. Si vous souhaitez définir une autorisation personnalisée pour votre application, vous pouvez copier la section autorisation Internet ou intranet à partir d’un autre manifeste, modifiez-le selon vos besoins et ajoutez-le au manifeste d’application en utilisant un éditeur de texte ou  *MageUI.exe*. Pour plus d’informations, consultez [vue d’ensemble du déploiement d’applications approuvées](../deployment/trusted-application-deployment-overview.md).  
  
-   Obtenez un certificat Authenticode.  
  
     Vous devez signer votre déploiement avec un certificat Authenticode. Vous pouvez générer un certificat de test à l’aide de Visual Studio, *MageUI.exe*, ou *MakeCert.exe* et *Pvk2Pfx.exe* outils, ou vous pouvez obtenir un certificat à partir d’un certificat Autorité (CA). Si vous choisissez d’utiliser le déploiement d’applications approuvées, vous devez également effectuer une installation unique du certificat sur tous les ordinateurs clients. Pour plus d'informations, consultez [Trusted Application Deployment Overview](../deployment/trusted-application-deployment-overview.md).  
  
    > [!NOTE]
    >  Vous pouvez également signer votre déploiement avec un certificat CNG que vous pouvez obtenir à partir d’une autorité de certification.  
  
-   Assurez-vous que l’application n’a pas d’un manifeste avec des informations de compte d’utilisateur.  
  
     Vous devez déterminer si votre application contient un manifeste avec des informations de contrôle de compte utilisateur (UAC), comme un `<dependentAssembly>` élément. Pour examiner un manifeste d’application, vous pouvez utiliser Windows Sysinternals [Sigcheck](http://go.microsoft.com/fwlink/?LinkId=158035) utilitaire.  
  
     Si votre application contient un manifeste avec des détails de l’UAC, vous devez régénérer sans les informations de compte d’utilisateur. Pour un projet c# dans Visual Studio, ouvrez les propriétés du projet et sélectionnez l’onglet Application. Dans le **manifeste** liste déroulante, sélectionnez **créer l’application sans manifeste**. Pour un projet Visual Basic dans Visual Studio, ouvrez les propriétés du projet, sélectionnez l’onglet Application, puis cliquez sur **afficher les paramètres UAC**. Dans le fichier manifeste ouvert, supprimez tous les éléments dans le même `<asmv1:assembly>` élément.  
  
-   Déterminer si l’application requiert les composants requis sur l’ordinateur client.  
  
     [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] les applications déployées à partir de Visual Studio peuvent inclure un programme d’amorçage de l’installation des composants requis (*setup.exe*) avec votre déploiement. Cette procédure pas à pas crée deux manifestes requis pour un [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] déploiement. Vous pouvez créer un programme d’amorçage requis à l’aide de la [GenerateBootstrapper, tâche](../msbuild/generatebootstrapper-task.md).  
  
### <a name="to-deploy-an-application-with-the-mageexe-command-line-tool"></a>Pour déployer une application avec l’outil de ligne de commande Mage.exe  
  
1.  Créez un répertoire où vous stockerez vos [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] des fichiers de déploiement.  
  
2.  Dans le répertoire de déploiement que vous venez de créer, créez un sous-répertoire de version. S’il s’agit de la première fois que vous déployez l’application, nommez le sous-répertoire de version **1.0.0.0**.  
  
    > [!NOTE]
    >  La version de votre déploiement peut être différente de la version de votre application.  
  
3.  Copiez tous les fichiers de votre application dans le sous-répertoire de version, y compris les fichiers exécutables, les assemblys, les ressources et les fichiers de données. Si nécessaire, vous pouvez créer des sous-répertoires supplémentaires qui contiennent des fichiers supplémentaires.  
  
4.  Ouvrez le [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] ou commande de Visual Studio invite et accédez au sous-répertoire de version.  
  
5.  Créer le manifeste d’application avec un appel à *Mage.exe*. L’instruction suivante crée un manifeste d’application pour le code compilé pour s’exécuter sur le processeur Intel x86.  
  
    ```cmd
    mage -New Application -Processor x86 -ToFile AppToDeploy.exe.manifest -name "My App" -Version 1.0.0.0 -FromDirectory .   
    ```  
  
    > [!NOTE]
    >  Veillez à inclure le point (.) après le `-FromDirectory` option, qui indique le répertoire actif. Si vous n’incluez pas le point, vous devez spécifier le chemin d’accès à vos fichiers d’application.  
  
6.  Signer le manifeste d’application avec votre certificat Authenticode. Remplacez *mycert.pfx* avec le chemin d’accès à votre fichier de certificat. Remplacez *passwd* avec le mot de passe pour votre fichier de certificat.  
  
    ```cmd
    mage -Sign AppToDeploy.exe.manifest -CertFile mycert.pfx -Password passwd  
    ```  
  
    En commençant par le Kit de développement logiciel .NET Framework 4.6.2, qui est distribué avec Visual Studio et avec le SDK Windows, *mage.exe* signe les manifestes avec CNG ainsi qu’avec des certificats Authenticode. Utilisez les mêmes paramètres de ligne de commande à l’instar de certificats Authenticode.
    
7.  Accéder à la racine du répertoire de déploiement.  
  
8.  Générer le manifeste de déploiement avec un appel à *Mage.exe*. Par défaut, *Mage.exe* marque votre [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] déploiement sous la forme d’une application installée, afin qu’il peut être exécuté à la fois en ligne et hors connexion. Pour rendre l’application disponible uniquement lorsque l’utilisateur est en ligne, utilisez le `-Install` option avec la valeur `false`. Si vous utilisez la valeur par défaut, et les utilisateurs installent votre application à partir d’un site Web ou un partage de fichiers, assurez-vous que la valeur de la `-ProviderUrl` pointe d’option à l’emplacement de l’application manifeste sur le serveur Web ou le partage.  
  
    ```cmd  
    mage -New Deployment -Processor x86 -Install true -Publisher "My Co." -ProviderUrl "\\myServer\myShare\AppToDeploy.application" -AppManifest 1.0.0.0\AppToDeploy.exe.manifest -ToFile AppToDeploy.application  
    ```  
  
9. Signer le manifeste de déploiement avec votre certificat Authenticode ou CNG.  
  
    ```cmd  
    mage -Sign AppToDeploy.application -CertFile mycert.pfx -Password passwd  
    ```  
  
10. Copiez tous les fichiers dans le répertoire de déploiement à la destination du déploiement ou le média. Cela peut être soit un dossier sur un site Web ou FTP site, un partage de fichiers ou un CD-ROM.  
  
11. Fournir à vos utilisateurs avec l’URL, une UNC ou un support physique requis pour installer votre application. Si vous fournissez une URL ou un chemin UNC, vous devez communiquer aux utilisateurs le chemin d’accès complet au manifeste de déploiement. Par exemple, si AppToDeploy est déployé sur http://webserver01/ dans le répertoire AppToDeploy, le chemin d’accès URL complète serait http://webserver01/AppToDeploy/AppToDeploy.application.  
  
### <a name="to-deploy-an-application-with-the-mageuiexe-graphical-tool"></a>Pour déployer une application avec l’outil graphique MageUI.exe  
  
1.  Créez un répertoire où vous stockerez vos [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] des fichiers de déploiement.  
  
2.  Dans le répertoire de déploiement que vous venez de créer, créez un sous-répertoire de version. S’il s’agit de la première fois que vous déployez l’application, nommez le sous-répertoire de version **1.0.0.0**.  
  
    > [!NOTE]
    >  La version de votre déploiement est probablement différent de la version de votre application.  
  
3.  Copiez tous les fichiers de votre application dans le sous-répertoire de version, y compris les fichiers exécutables, les assemblys, les ressources et les fichiers de données. Si nécessaire, vous pouvez créer des sous-répertoires supplémentaires qui contiennent des fichiers supplémentaires.  
  
4.  Démarrer le *MageUI.exe* outil graphique.  
  
    ```cmd  
    MageUI.exe  
    ```  
  
5.  Créer un nouveau manifeste d’application en sélectionnant **fichier**, **New**, **manifeste d’Application** dans le menu.  
  
6.  Sur la valeur par défaut **nom** , tapez le nom et numéro de version de ce déploiement. Spécifiez également le **processeur** que votre application est générée, par exemple x86.  
  
7.  Sélectionnez le **fichiers** onglet et cliquez sur le bouton de sélection (**...** ) situé en regard du **répertoire de l’Application** zone de texte. Un **rechercher un dossier** boîte de dialogue s’affiche.  
  
8.  Sélectionnez le sous-répertoire de version contenant vos fichiers d’application, puis cliquez sur **OK**.  
  
9. Si vous allez déployer à partir de Internet Information Services (IIS), sélectionnez le **lorsque le remplissage d’ajouter l’extension .deploy à n’importe quel fichier qui ne l’a pas** case à cocher.  
  
10. Cliquez sur le **Populate** pour ajouter tous les fichiers de votre application à la liste des fichiers. Si votre application contient plusieurs fichiers exécutables, marquez le fichier exécutable principal de ce déploiement comme application de démarrage en sélectionnant **Point d’entrée** à partir de la **Type de fichier** liste déroulante. (Si votre application ne contient qu’un seul fichier exécutable, *MageUI.exe* marquera pour vous.)  
  
11. Sélectionnez le **autorisations requises** onglet et sélectionnez le niveau de confiance que vous avez besoin de votre application doit déclarer. La valeur par défaut est **FullTrust**, qui convient pour la plupart des applications.  
  
12. Sélectionnez **fichier**, **Enregistrer sous** dans le menu. Une boîte de dialogue Options de signature s’affiche et vous invite à signer le manifeste d’application.  
  
13. Si vous avez un certificat stocké en tant que fichier sur votre système de fichiers, utilisez le **signer avec le fichier de certificat** option et sélectionnez le certificat du système de fichiers en utilisant les points de suspension (**...** ) bouton. Puis tapez votre mot de passe du certificat.  
  
     - ou -  
  
     Si votre certificat est conservé dans un magasin de certificats accessible à partir de votre ordinateur, sélectionnez le **signer avec un certificat stocké** option et sélectionnez le certificat dans la liste fournie.  
  
14. Cliquez sur **OK** pour signer votre manifeste d’application. Le **Enregistrer sous** boîte de dialogue s’affiche.  
  
15. Dans le **enregistrer en tant que** boîte de dialogue, spécifiez le répertoire de version, puis cliquez sur **enregistrer**.  
  
16. Sélectionnez **fichier**, **New**, **du manifeste de déploiement** dans le menu pour créer votre manifeste de déploiement.  
  
17. Sur le **nom** onglet, spécifiez un nom et numéro de version pour ce déploiement (**1.0.0.0** dans cet exemple). Spécifiez également le **processeur** que votre application est générée, par exemple x86.  
  
18. Sélectionnez le **Description** onglet et spécifier des valeurs pour **Publisher** et **produit**. (**Produit** est le nom donné à votre application dans le menu Démarrer de Windows lorsque votre application s’installe sur un ordinateur client pour une utilisation hors connexion.)  
  
19. Sélectionnez le **Options de déploiement** onglet, puis, dans le **Start Location** texte, spécifiez l’emplacement du manifeste d’application sur le serveur Web ou le partage. Par exemple,  *\\\myServer\myShare\AppToDeploy.application*.  
  
20. Si vous avez ajouté le *.deploy* extension à l’étape précédente, sélectionnez également **utiliser l’extension de nom de fichier .deploy** ici.  
  
21. Sélectionnez le **mettre à jour les Options** onglet et spécifier la fréquence à laquelle vous souhaitez que cette application pour mettre à jour. Si votre application utilise <xref:System.Deployment.Application.UpdateCheckInfo> pour vérifier les mises à jour lui-même, désactivez le **cette application doit rechercher les mises à jour** case à cocher.  
  
22. Sélectionnez le **Application référence** onglet, puis cliquez sur le **sélectionner un manifeste** bouton. Une boîte de dialogue Ouvrir s’affiche.  
  
23. Sélectionnez le manifeste d’application que vous avez créé précédemment, puis cliquez **Open**.  
  
24. Sélectionnez **fichier**, **Enregistrer sous** dans le menu. Un **Options de signature** boîte de dialogue s’affiche et vous invite à signer le manifeste de déploiement.  
  
25. Si vous avez un certificat stocké en tant que fichier sur votre système de fichiers, utilisez le **signer avec le fichier de certificat** option et sélectionnez le certificat du système de fichiers en utilisant les points de suspension (**...** ) bouton. Puis tapez votre mot de passe du certificat.  
  
     - ou -  
  
     Si votre certificat est conservé dans un magasin de certificats accessible à partir de votre ordinateur, sélectionnez le **signer avec un certificat stocké** option et sélectionnez le certificat dans la liste fournie.  
  
26. Cliquez sur **OK** pour signer votre manifeste de déploiement. Le **Enregistrer sous** boîte de dialogue s’affiche.  
  
27. Dans le **enregistrer en tant que** boîte de dialogue, déplacement d’un répertoire à la racine de votre déploiement puis cliquez sur **enregistrer**.  
  
28. Copiez tous les fichiers dans le répertoire de déploiement à la destination du déploiement ou le média. Cela peut être soit un dossier sur un site Web ou FTP site, un partage de fichiers ou un CD-ROM.  
  
29. Fournir à vos utilisateurs avec l’URL, une UNC ou un support physique requis pour installer votre application. Si vous fournissez une URL ou un chemin UNC, vous devez donner à vos utilisateurs le chemin d’accès complet du manifeste de déploiement. Par exemple, si AppToDeploy est déployé sur http://webserver01/ dans le répertoire AppToDeploy, le chemin d’accès URL complète serait http://webserver01/AppToDeploy/AppToDeploy.application.  
  
## <a name="next-steps"></a>Étapes suivantes  
 Lorsque vous avez besoin déployer une nouvelle version de l’application, créez un répertoire nommé d’après la nouvelle version, par exemple, 1.0.0.1 copier les nouveaux fichiers d’application dans le nouveau répertoire. Ensuite, vous devez suivre les étapes précédentes pour créer et signer un manifeste d’application et mettre à jour et signer le manifeste de déploiement. Veillez à spécifier la même version supérieure à la fois dans le *Mage.exe* `-New` et `-Update` appels, en tant que [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] met à jour uniquement les versions ultérieures, avec l’entier le plus à gauche plus significatif. Si vous avez utilisé *MageUI.exe*, vous pouvez mettre à jour le manifeste de déploiement en l’ouvrant, en sélectionnant le **Application référence** onglet, en cliquant sur le **sélectionner un manifeste** bouton, et puis en sélectionnant le manifeste d’application mis à jour.  
  
## <a name="see-also"></a>Voir aussi  
 [Mage.exe (outil Manifest Generation and Editing)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (outil Manifest Generation and Editing, client graphique)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [Publier des applications ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Manifeste de déploiement ClickOnce](../deployment/clickonce-deployment-manifest.md)   
 [Manifeste d’application ClickOnce](../deployment/clickonce-application-manifest.md)