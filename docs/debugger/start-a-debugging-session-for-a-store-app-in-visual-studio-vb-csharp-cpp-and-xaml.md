---
title: Démarrer une session de débogage pour une application UWP dans Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/04/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- VC.Project.IVCAppHostRemoteDebugPageObject.MachineName
- VC.Project.IVCAppHostRemoteDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostTetheredDebugPageObject.DebuggerType
- VC.Project.IVCAppHostLocalDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostRemoteDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.DebuggerType
- ImmersiveProjects.Properties.Debug
- VC.Project.IVCAppHostTetheredDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostLocalDebugPageObject.AllowLocalNetworkLoopback
- AppPackage.Properties.Debug
- VC.Project.IVCAppHostRemoteDebugPageObject.Authentication
- VC.Project.IVCAppHostRemoteDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.BreakpointBehavior
- vs.debug.installedapppackagelauncher
- vs.debug.error.wwahost_scriptdebuggingdisabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: a7a9f74450ccf2cb493e44fa1fecef0630a27569
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49818782"
---
# <a name="start-a-debugging-session-for-a-uwp-app-in-visual-studio"></a>Démarrer une session de débogage pour une application UWP dans Visual Studio
  
 Cette rubrique décrit comment démarrer une session de débogage pour les applications UWP écrites en XAML et Visual C++, Visual C#, ou Visual Basic et pour les applications UWP écrites en HTML et JavaScript. Le débogage d'une application implique la configuration de la session de débogage et le choix de la méthode de démarrage de l'application.  
  
##  <a name="BKMK_The_easy_way_to_start_debugging"></a> La méthode simple pour démarrer le débogage  
  
1. Ouvrez la solution d'application dans Visual Studio.  
  
2. Appuyez sur F5.  
  
   Visual Studio génère et démarre l'application avec le débogueur attaché. L'exécution se poursuit jusqu'à ce qu'un point d'arrêt soit atteint, que vous suspendiez manuellement l'exécution, qu'une exception non gérée se produise ou que l'application se termine.  
  
##  <a name="BKMK_Choose_the_build_configuration_options"></a> Choisir les options de configuration de build  
  
1.   Dans la liste déroulante liste en regard du **démarrer le débogage** bouton sur le débogueur **Standard** barre d’outils, choisissez **déboguer**.  
  
2.  Dans la liste **Plateforme** , sélectionnez la plateforme cible à générer.  
  
##  <a name="BKMK_Choose_the_deployment_target"></a> Sélectionner la cible de déploiement  
  
Vous pouvez déployer et déboguer une application UWP sur l’ordinateur Visual Studio, un appareil connecté, le simulateur Visual Studio sur l’ordinateur local, un appareil distant ou un émulateur. Sélectionnez la cible de déploiement à partir de la liste déroulante à droite de la **plateforme** cible sur le débogueur **Standard** barre d’outils.
  
![Sélectionnez une cible de déploiement](../debugger/media/vsrun_select_target_device.png)  
  
Choisissez l'une des options suivantes :  
  
|||  
|-|-|  
|**Ordinateur local**|Déboguez l'application dans la session active sur votre ordinateur local.|  
|**Simulateur**|Déboguez l’application dans le simulateur Visual Studio pour les applications UWP. Le simulateur est une fenêtre du bureau qui vous permet de déboguer les fonctionnalités de l’appareil, telles que les mouvements tactiles et la rotation de l’appareil, qui n’est peut-être pas disponible sur l’ordinateur local. Cette option est disponible uniquement si votre application **minimale de la plateforme cible. Version** est inférieur ou égal au système d’exploitation sur votre ordinateur de développement. Consultez [exécuter des applications UWP dans le simulateur](../debugger/run-windows-store-apps-in-the-simulator.md).|  
|**Ordinateur distant**|Déboguez l'application sur un périphérique qui est connecté à l'ordinateur local sur un intranet ou directement connecté via un câble Ethernet. Pour déboguer à distance, les outils à distance pour Visual Studio doivent être installés et en cours d’exécution sur le périphérique distant. Consultez [exécuter des applications UWP sur un ordinateur distant](../debugger/run-windows-store-apps-on-a-remote-machine.md).|  
|**APPAREIL**|Déboguez l’application sur un périphérique USB connecté. L’appareil doit être déverrouillé de développeur et l’écran déverrouillé.|  
|**Émulateur mobile**|Démarrer un émulateur avec la configuration spécifiée dans le nom de l’émulateur, déployez l’application et démarrer le débogage. Émulateurs sont disponibles uniquement sur les machines Hyper-V est activé.|  

##  <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a> Choisissez les options de débogage supplémentaires  

Si vous avez besoin configurer les options de débogage supplémentaires, ouvrez la page de propriétés pour le projet.
  
1.  Dans l'Explorateur de solutions, sélectionnez le projet. Dans le menu contextuel, choisissez **Propriétés**.  
  
2.  Cela permet d’ouvrir la page de propriétés de débogage pour le projet :  
  
    -   Pour les applications Visual C# et Visual Basic, choisissez **Déboguer**.  
  
         ![C&#35; &#47; page de propriétés de débogage de projet VB](../debugger/media/dbg_csvb_debugpropertypage.png)  
  
    -   Pour les applications Visual C++ et JavaScript, développez le **propriétés de Configuration** nœud, puis choisissez **débogage**.  
  
         ![C&#43; &#43; page de propriétés de débogage de l’application UWP](../debugger/media/dbg_cpp_debugpropertypage.png)  

###  <a name="BKMK_Choose_the_debugger_to_use"></a> Choisir le débogueur à utiliser  
Par défaut, Visual Studio débogue le code managé dans des applications C# et Visual Basic. Pour les applications C# et Visual Basic, vous pouvez choisir de déboguer le code managé et natif C/C++ dans votre application. Dans les applications C++, Visual Studio débogue le code natif par défaut. Dans les applications JavaScript, Visual Studio débogue le script par défaut. 
  
Pour les applications C++ et JavaScript, vous pouvez choisir de déboguer des types spécifiques de code qui se trouvent dans les composants de votre application à la place ou en plus, le code natif. Spécifiez le code à déboguer dans la liste **Type de débogueur** de la page des propriétés de **débogage** du projet d'application.  
  
Choisissez l'un de ces débogueurs dans la liste **Processus d'application** :  
  
|||  
|-|-|  
|**Managé uniquement**|Déboguez le code managé dans votre application. Le code JavaScript et le code natif C/C++ sont ignorés.|  
|**Natif uniquement**|Déboguez le code natif C/C++ dans votre application. Le code managé et le code JavaScript sont ignorés.|  
|**Mixte (natif et managé)**|Déboguez le code natif et managé C/C++ dans votre application. Le code JavaScript est ignoré. Dans les projets C++, cette option est appelée **(managé et natif)**.|  
|**Script uniquement**|Déboguez le code JavaScript dans votre application. Le code managé et le code natif sont ignorés.|  
|**Script et natif**|Déboguer le code C/C++ natif et le code JavaScript dans votre application. Le code managé est ignoré. Disponible dans les projets C++ uniquement.|  
|**GPU uniquement (C++ AMP)**|Déboguez le code C++ natif qui s'exécute sur une unité de traitement graphique (GPU). Disponible dans les projets C++ uniquement.|  

Dans C# et les applications Visual Basic, vous pouvez également définir les mêmes **type de débogueur** valeurs pour les tâches en arrière-plan qui font partie du projet.
  
###  <a name="BKMK__Optional__Delay_starting_the_debug_session"></a> Différer le démarrage de la session de débogage (facultatif)  
 Par défaut, Visual Studio démarre immédiatement l'application lorsque vous démarrez le débogage. Vous pouvez également démarrer une session de débogage et retarder le démarrage de votre application. Lorsque vous choisissez cette option, l'application est lancée dans le débogueur lorsqu'elle est lancée depuis l'écran Démarrer ou par un contrat d'activation, ou lorsqu'elle est démarrée par un autre processus ou méthode. Vous pouvez également différer le démarrage de votre application lorsque vous souhaitez déboguer une tâche en arrière-plan alors que l'application proprement dite n'est pas en cours d'exécution.  
  
 Pour différer le lancement de votre application, vous pouvez :  
  
-   Pour les applications Visual C# et Visual Basic, sélectionnez **Ne pas lancer, mais déboguer mon code au démarrage** dans la page des propriétés **Déboguer** .  
  
-   Pour les applications Visual C++ et JavaScript, choisissez **non** à partir de la **lancer l’Application** liste sur le **débogage** page de propriétés.  
  
###  <a name="BKMK__Optional__Disable_network_loopbacks"></a> Désactiver les bouclages de réseau (facultatif)  
  
 Pour des raisons de sécurité, une application UWP qui est installée en mode standard n’est pas autorisée à effectuer des appels réseau à l’appareil sur que n’est installé. Par défaut, le déploiement Visual Studio crée une exemption à cette règle pour l'application déployée. Cette exemption vous permet de tester les procédures de communication sur un seul ordinateur. Avant de soumettre votre application à Microsoft Store, vous devez tester votre application sans l’exemption.  
  
 Pour supprimer l'exemption du bouclage de réseau :  
  
-   Pour Visual C# et les applications Visual Basic, désactivez le **autoriser le bouclage de réseau local** case à cocher sur la **déboguer** page de propriétés.  
  
-   Pour les applications Visual C++ et JavaScript, choisissez **non** à partir de la **autoriser le bouclage de réseau Local** liste sur le **débogage** page de propriétés.  
  
###  <a name="BKMK__Optional__Reinstall_the_app_when_you_start_debugging"></a> Réinstaller l'application au démarrage du débogage (facultatif)  
 Pour diagnostiquer les problèmes liés à l'installation et à la configuration initiale de votre application Visual C# ou Visual Basic, choisissez **Désinstaller et réinstaller mon package** sur la page des propriétés **Déboguer**  pour recréer une installation d'origine lorsque vous démarrez le débogage. Cette option n’est pas disponible pour les projets Visual C++ et JavaScript.  
  
###  <a name="BKMK__Optional__Disable_authentication_requirement_to_start_the_remote_debugger"></a> (Facultatif) Désactivez la condition d'authentification pour démarrer le débogueur distant  
  
 Par défaut, vous devez fournir des informations d’identification pour exécuter le débogueur distant lorsque vous sélectionnez **Machine distante** comme cible de déploiement.
  
> [!IMPORTANT]
>  Vous pouvez choisir d’exécuter le débogueur distant sans authentification, mais ce mode est fortement déconseillé. Il n'existe aucune sécurité du réseau lorsque vous lancez l'exécution dans ce mode. Ne choisissez Aucune authentification uniquement si vous êtes sûr que le réseau n’est pas exposés à un code malveillant ou de trafic hostile.  
  
 Pour annuler la condition d'authentification :  
  
1.  Pour Visual C# et les applications Visual Basic, sélectionnez **Machine distante** en tant que le **appareil cible** sur le **déboguer** page de propriétés, puis définissez **l’authentification Mode** à **aucun** ou **universel (protocole non chiffré)**.
  
2.  Pour les applications Visual C++ et JavaScript, sélectionnez **Machine distante** en tant que le **appareil cible** sur le **débogage** page de propriétés, puis définissez **nécessitent Authentification** à **aucun** ou **universel (protocole non chiffré)**.  

    **Universel (protocole non chiffré)** est à utiliser lorsque vous déployez sur un périphérique distant. Actuellement, il s’agit d’appareils IoT, Xbox, appareils et les appareils HoloLens, ainsi que Creators Update ou PC récents. Universel (protocole non chiffré) doit uniquement être utilisée sur des réseaux approuvés. La connexion de débogage est vulnérable aux utilisateurs malveillants qui pourrait intercepter et modifier des données transmises entre le développement et l’ordinateur distant.  
  
##  <a name="BKMK_Start_the_debugging_session"></a> Démarrer la session de débogage  
  
###  <a name="BKMK_Start_debugging__F5_"></a> Démarrer le débogage (F5)  
 Lorsque vous choisissez **démarrer le débogage** (clavier : F5) sur le **déboguer** menu, Visual Studio lance l’application avec le débogueur attaché. L'exécution se poursuit jusqu'à ce qu'un point d'arrêt soit atteint, que vous suspendiez manuellement l'exécution, qu'une exception se produise ou que l'application se termine.  
  
###  <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a> Démarrer le débogage (F5), mais différer le démarrage de l'application  
 Vous pouvez configurer l'application pour s'exécuter en mode débogage, mais la démarrer par une autre méthode que le débogueur. Par exemple, vous pouvez faire pour déboguer le lancement de votre application dans le menu Démarrer, ou pour déboguer un processus en arrière-plan dans l’application sans démarrer l’application. Pour différer le démarrage de l’application, procédez comme suit :  
  
- Sur le **déboguer** page de propriétés de l’application (**débogage** dans Visual C++ et JavaScript)  
  
  -   Pour les applications Visual C# et Visual Basic, choisissez **Ne pas lancer, mais déboguer mon code au démarrage**.  
  
  -   Pour les applications Visual C++ et JavaScript, choisissez **Oui** à partir de la **lancer l’Application** liste.  
  
- Choisissez **démarrer le débogage** sur le **déboguer** menu (clavier : F5).  
  
- Démarrez votre application dans le menu Démarrer, avec un contrat de exécution ou en suivant une autre procédure.  
  
  L'application démarre en mode débogage. L'exécution se poursuit jusqu'à ce qu'un point d'arrêt soit atteint, que vous suspendiez manuellement l'exécution, qu'une exception non gérée se produise ou que l'application se termine.  
  
  Pour plus d’informations sur le débogage des tâches en arrière-plan, consultez [déclencheur suspendre, reprendre, événements et d’arrière-plan pour les applications UWP)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
###  <a name="BKMK_Start_an_installed_app_in_the_debugger"></a> Démarrer une application installée dans le débogueur  
Lorsque vous lancez le débogage en appuyant sur la touche F5, Visual Studio génère et déploie l'application, la configure pour s'exécuter en mode débogage, puis la démarre. Pour démarrer une application qui est déjà installée sur un appareil, utilisez le **déboguer le Package d’application installé** boîte de dialogue. Cette procédure est utile lorsque vous devez déboguer une application qui a été installée à partir de Microsoft Store, ou lorsque vous disposez des fichiers source pour l’application, mais vous n’avez pas d’un projet Visual Studio pour l’application. Par exemple, vous pouvez avoir un système de génération personnalisée qui n'utilise pas les projets ou les solutions Visual Studio.  
  
Vous pouvez installer l'application sur le périphérique local ou sur un périphérique distant.  Vous pouvez démarrer l'application immédiatement, ou bien la configurer pour s'exécuter dans le débogueur au démarrage de ce dernier par un autre processus ou une autre méthode, depuis le menu Démarrer ou par un contrat d'activation, par exemple. Vous pouvez également configurer l'application pour s'exécuter en mode débogage lorsque vous souhaitez déboguer un processus en arrière-plan sans démarrer l'application. Pour plus d’informations, consultez [déclencheur suspendre, reprendre, événements et d’arrière-plan pour les applications UWP)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
Pour démarrer une application installée dans le débogueur, choisissez **déboguer**, puis **autres cibles de débogage**, puis **déboguer le Package d’application installé**. Pour obtenir des instructions supplémentaires, consultez [déboguer un package d’application installé](../debugger/debug-installed-app-package.md).

###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a> Attacher le débogueur à une application UWP en cours d’exécution  

Pour déboguer une application UWP en cours d’exécution, choisissez **déboguer**, puis **autres cibles de débogage**, puis **déboguer le Package d’application installé**. Pour obtenir des instructions supplémentaires, consultez [déboguer un package d’application installé](../debugger/debug-installed-app-package.md).
  
###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a> Attacher le débogueur à une exécution de l’application Windows 8.x
 Pour attacher le débogueur à une application [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] , vous devez utiliser Debuggable Package Manager pour configurer l'application à exécuter en mode débogage. Debuggable Package Manager est installé avec les outils à distance pour Visual Studio.  
  
 Attacher le débogueur à une application est utile lorsque vous devez déboguer une application déjà installée, telle qu'une application qui a été installée à partir de [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]. L'attachement est requis lorsque vous possédez les fichiers sources de l'application, mais que vous n'avez pas de projet Visual Studio pour l'application. Par exemple, vous pouvez avoir un système de génération personnalisée qui n'utilise pas les projets ou les solutions Visual Studio.  
  
 Attacher le débogueur à une application nécessite les étapes suivantes :  
  
1.  Configurez l'application pour l'exécuter en mode débogage. Cela doit s'effectuer lorsque l'application n'est pas en cours d'exécution.  
  
2.  Démarrez l'application. Vous pouvez démarrer l'application à partir de l'écran Démarre, avec un contrat d'exécution ou tout autre méthode.  
  
3.  Attacher le débogueur à l'application en cours d'exécution.  
  
####  <a name="BKMK_Set_the_app_to_run_in_debug_mode"></a> Configurer l'application pour l'exécuter en mode débogage  
  
1.  Installer les outils à distance pour Visual Studio sur l’appareil où l’application est installée. Consultez [l’installation des outils à distance](../debugger/remote-debugging.md).  
  
2.  Sur l'écran Démarrer, recherchez `Debuggable Package Manager` , puis démarrez-le.  
  
     Une fenêtre PowerShell correctement configurée pour l'applet de commande AppxDebug s'affiche.  
  
3.  Pour activer le débogage d'une application, vous devez spécifier l'identificateur PackageFullName de l'application. Pour afficher une liste de toutes les applications qui incluent PackageFullName, entrez `Get-AppxPackage` à l'invite de PowerShell.  
  
4.  À l'invite de PowerShell, entrez `Enable-AppxDebug` *PackageFullName* , où *PackageFullName* est l'identificateur PackageFullName de l'application.  
  
####  <a name="BKMK_Attach_the_debugger"></a> Attacher le débogueur  
 Pour attacher le débogueur :  
  
1. Dans le menu **Débogage** , sélectionnez **Attacher au processus**.  
  
    La boîte de dialogue **Attacher au processus** s'affiche.  
  
2. Pour attacher une application sur un périphérique distant, spécifiez le périphérique distant dans la zone **Qualificateur** . Vous pouvez :  
  
   -   Entrez le nom dans la zone **Qualificateur** .  
  
   -   Cliquez sur la flèche Bas dans la zone **Qualificateur** , puis choisissez le périphérique dans une liste que vous avez associée précédemment.  
  
   -   Choisissez **Rechercher** pour sélectionner le périphérique dans une liste de périphériques sur votre sous-réseau local.  
  
3. Spécifiez le type de code à déboguer dans la zone **Attacher à** .  
  
    Choisissez **Sélectionner** , puis effectuez l'une des opérations suivantes :  
  
   -   Choisissez **Déterminer automatiquement le type de code à déboguer**  
  
   -   Choisissez **Déboguer ces types de codes** , puis sélectionnez un ou plusieurs types dans la liste.  
  
4. Dans la liste **Processus disponibles**  , sélectionnez le processus de l'application.  

   > [!NOTE]
   >  Contrairement à d’autres types d’applications, les applications JavaScript s’exécutent dans une instance du processus wwahost.exe. Si d'autres applications JavaScript sont en cours d'exécution pendant l'attachement à l'application, vous devez connaître l'identifiant de processus (PID) numérique du processus wwahost.exe dans lequel l'application s'exécute.  
   >   
   >  La solution la plus simple pour gérer cette situation consiste à fermer toutes les autres applications JavaScript. Sinon, vous pouvez ouvrir le Gestionnaire de tâches Windows avant de démarrer l’application et de noter les identifiants des processus wwahost.exe. Lorsque vous spécifiez le processus à attacher à la **processus disponibles** boîte de dialogue, le wwahost.exe de l’application aura un identifiant qui est différent de ceux que vous avez déjà notés.  
  
5. Choisissez **Attacher**.  
  
   Visual Studio attache le débogueur au processus. L'exécution se poursuit jusqu'à ce qu'un point d'arrêt soit atteint, que vous suspendiez manuellement l'exécution, qu'une exception non gérée se produise ou que l'application se termine.  
  
## <a name="see-also"></a>Voir aussi  
 [Déboguer des applications dans Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)   