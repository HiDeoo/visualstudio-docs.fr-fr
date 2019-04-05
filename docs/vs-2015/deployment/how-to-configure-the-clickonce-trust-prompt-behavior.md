---
title: 'Procédure : Configurer le comportement d’invite d’approbation ClickOnce | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, install without prompting
- deploying applications [ClickOnce], trust prompt
- ClickOnce applications, install without prompting
- ClickOnce applications, trust prompt
- ClickOnce deployment, trust prompt
ms.assetid: cc04fa75-012b-47c9-9347-f4216be23cf2
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f5a1174f96e34773aac524562d6f62514e92ba5e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "59001168"
---
# <a name="how-to-configure-the-clickonce-trust-prompt-behavior"></a>Procédure : Configurer le comportement de l’invite d’approbation ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez configurer l’invite d’approbation ClickOnce pour contrôler si les utilisateurs finaux reçoivent l’option d’installation d’applications ClickOnce, telles que les applications Windows Forms, les applications Windows Presentation Foundation, les applications console, de navigateur WPF les applications et les solutions Office. Vous configurez l’invite d’approbation en définissant des clés de Registre sur l’ordinateur de chaque utilisateur final.  
  
 Le tableau suivant montre les options de configuration qui peuvent être appliquées à chacune des cinq zones (Internet, UntrustedSites, MyComputer, LocalIntranet et TrustedSites).  
  
|Option|Valeur de paramètre de Registre|Description|  
|------------|----------------------------|-----------------|  
|Activer l’invite d’approbation.|`Enabled`|L’invite d’approbation ClickOnce s’affiche afin que les utilisateurs finaux puissent approuver les applications ClickOnce.|  
|Restreindre l’invite d’approbation.|`AuthenticodeRequired`|L’invite d’approbation ClickOnce s’affiche uniquement si les applications ClickOnce sont signées avec un certificat qui identifie le serveur de publication.|  
|Désactiver l’invite d’approbation.|`Disabled`|L’invite d’approbation ClickOnce n’est pas affichée pour les applications ClickOnce qui ne sont pas signées avec un certificat explicitement approuvé.|  
  
 Le tableau suivant montre le comportement par défaut pour chaque zone. La colonne Applications fait référence à des applications Windows Forms, les applications Windows Presentation Foundation, les applications de navigateur WPF et applications de console.  
  
|Zone|Applications|solutions Office|  
|----------|------------------|----------------------|  
|`MyComputer`|`Enabled`|`Enabled`|  
|`LocalIntranet`|`Enabled`|`Enabled`|  
|`TrustedSites`|`Enabled`|`Enabled`|  
|`Internet`|`Enabled`|`AuthenticodeRequired`|  
|`UntrustedSites`|`Disabled`|`Disabled`|  
  
 Vous pouvez remplacer ces paramètres en activant, restriction ou la désactivation de l’invite d’approbation ClickOnce.  
  
## <a name="enabling-the-clickonce-trust-prompt"></a>L’activation de l’invite d’approbation ClickOnce  
 Activer l’invite d’approbation pour une zone lorsque vous souhaitez que les utilisateurs finaux aient la possibilité d’installer et exécuter les applications ClickOnce provenant de cette zone.  
  
#### <a name="to-enable-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>Pour activer l’invite d’approbation ClickOnce à l’aide de l’Éditeur du Registre  
  
1.  Ouvrez l’Éditeur du Registre :  
  
    1.  Cliquez sur **Démarrer** puis sur **Exécuter**.  
  
    2.  Dans le **Open** , tapez `regedit` (ou `regedit32` sur 32 bits Windows), puis cliquez sur **OK**.  
  
2.  Recherchez la clé de Registre suivante :  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Si la clé n’existe pas, créez-le.  
  
3.  Ajoutez les sous-clés suivantes en tant que **valeur de chaîne**, si elles n’existent pas déjà, avec les valeurs associées présentées dans le tableau suivant.  
  
    |Sous-clé de valeur de chaîne|Value|  
    |-------------------------|-----------|  
    |`Internet`|`Enabled`|  
    |`UntrustedSites`|`Disabled`|  
    |`MyComputer`|`Enabled`|  
    |`LocalIntranet`|`Enabled`|  
    |`TrustedSites`|`Enabled`|  
  
     Pour les solutions Office, `Internet` a la valeur par défaut `AuthenticodeRequired` et `UntrustedSites` a la valeur `Disabled`. Pour tous les autres, `Internet` a la valeur par défaut `Enabled`.  
  
#### <a name="to-enable-the-clickonce-trust-prompt-programmatically"></a>Pour activer l’invite d’approbation ClickOnce par programmation  
  
1.  Créer une application console Visual Basic ou Visual c# dans Visual Studio.  
  
2.  Ouvrez le fichier Program.vb ou Program.cs pour l’édition et ajoutez le code suivant.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Enabled")  
    key.SetValue("LocalIntranet", "Enabled")  
    key.SetValue("Internet", "Enabled")  
    key.SetValue("TrustedSites", "Enabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Enabled");  
    key.SetValue("LocalIntranet", "Enabled");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "Enabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Générez et exécutez l’application.  
  
## <a name="restricting-the-clickonce-trust-prompt"></a>Restriction de l’invite d’approbation ClickOnce  
 Restreindre l’invite d’approbation afin que les solutions doivent être signées avec des certificats Authenticode dont l’identité est connue avant que les utilisateurs soient invités à une décision d’approbation.  
  
#### <a name="to-restrict-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>Pour restreindre l’invite d’approbation ClickOnce à l’aide de l’Éditeur du Registre  
  
1.  Ouvrez l’Éditeur du Registre :  
  
    1.  Cliquez sur **Démarrer** puis sur **Exécuter**.  
  
    2.  Dans le **Open** , tapez `regedit` (ou `regedit32` sur 32 bits Windows), puis cliquez sur **OK**.  
  
2.  Recherchez la clé de Registre suivante :  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Si la clé n’existe pas, créez-le.  
  
3.  Ajoutez les sous-clés suivantes en tant que **valeur de chaîne**, si elles n’existent pas déjà, avec les valeurs associées présentées dans le tableau suivant.  
  
    |Sous-clé de valeur de chaîne|Value|  
    |-------------------------|-----------|  
    |`UntrustedSites`|`Disabled`|  
    |`Internet`|`AuthenticodeRequired`|  
    |`MyComputer`|`AuthenticodeRequired`|  
    |`LocalIntranet`|`AuthenticodeRequired`|  
    |`TrustedSites`|`AuthenticodeRequired`|  
  
#### <a name="to-restrict-the-clickonce-trust-prompt-programmatically"></a>Pour restreindre l’invite d’approbation ClickOnce par programmation  
  
1.  Créer une application console Visual Basic ou Visual c# dans Visual Studio.  
  
2.  Ouvrez le fichier Program.vb ou Program.cs pour l’édition et ajoutez le code suivant.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "AuthenticodeRequired")  
    key.SetValue("LocalIntranet", "AuthenticodeRequired")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "AuthenticodeRequired")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "AuthenticodeRequired");  
    key.SetValue("LocalIntranet", "AuthenticodeRequired");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "AuthenticodeRequired");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Générez et exécutez l’application.  
  
## <a name="disabling-the-clickonce-trust-prompt"></a>La désactivation de l’invite d’approbation ClickOnce  
 Vous pouvez désactiver l’invite d’approbation afin que les utilisateurs finaux reçoivent pas l’option d’installation des solutions qui ne sont pas déjà approuvées dans leur stratégie de sécurité.  
  
#### <a name="to-disable-the-clickonce-trust-prompt-by-using-the-registry-editor"></a>Pour désactiver l’invite d’approbation ClickOnce à l’aide de l’Éditeur du Registre  
  
1.  Ouvrez l’Éditeur du Registre :  
  
    1.  Cliquez sur **Démarrer** puis sur **Exécuter**.  
  
    2.  Dans le **Open** , tapez `regedit` (ou `regedit32` sur 32 bits Windows), puis cliquez sur **OK**.  
  
2.  Recherchez la clé de Registre suivante :  
  
     \HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\. NETFramework\Security\TrustManager\PromptingLevel  
  
     Si la clé n’existe pas, créez-le.  
  
3.  Ajoutez les sous-clés suivantes en tant que **valeur de chaîne**, si elles n’existent pas déjà, avec les valeurs associées présentées dans le tableau suivant.  
  
    |Sous-clé de valeur de chaîne|Value|  
    |-------------------------|-----------|  
    |`UntrustedSites`|`Disabled`|  
    |`Internet`|`Disabled`|  
    |`MyComputer`|`Disabled`|  
    |`LocalIntranet`|`Disabled`|  
    |`TrustedSites`|`Disabled`|  
  
#### <a name="to-disable-the-clickonce-trust-prompt-programmatically"></a>Pour désactiver l’invite d’approbation ClickOnce par programmation  
  
1.  Créer une application console Visual Basic ou Visual c# dans Visual Studio.  
  
2.  Ouvrez le fichier Program.vb ou Program.cs pour l’édition et ajoutez le code suivant.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Disabled")  
    key.SetValue("LocalIntranet", "Disabled")  
    key.SetValue("Internet", "Disabled")  
    key.SetValue("TrustedSites", "Disabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Disabled");  
    key.SetValue("LocalIntranet", "Disabled");  
    key.SetValue("Internet", "Disabled");  
    key.SetValue("TrustedSites", "Disabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
  
    ```  
  
3.  Générez et exécutez l’application.  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurisation des applications ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Sécurité d’accès du code pour les applications ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce et Authenticode](../deployment/clickonce-and-authenticode.md)   
 [Vue d’ensemble du déploiement d’applications approuvées](../deployment/trusted-application-deployment-overview.md)   
 [Guide pratique pour Activer les paramètres de sécurité ClickOnce](../deployment/how-to-enable-clickonce-security-settings.md)   
 [Guide pratique pour Définir une Zone de sécurité pour une Application ClickOnce](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Guide pratique pour Définir des autorisations personnalisées pour une Application ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Guide pratique pour Déboguer une Application ClickOnce avec des autorisations restreintes](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Guide pratique pour Ajouter un éditeur approuvé à un ordinateur Client pour les Applications ClickOnce](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [Guide pratique pour re-signer des manifestes d’application et de déploiement](../deployment/how-to-re-sign-application-and-deployment-manifests.md)
