---
title: Utiliser plusieurs comptes d’utilisateur
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 33f88444d7bbdc0b0fe85bfa5efbdbbd794fa3e4
ms.sourcegitcommit: bc43970c000f07c9cc2051f1264a9742943a9755
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51349387"
---
# <a name="work-with-multiple-user-accounts"></a>Utiliser plusieurs comptes d’utilisateur

Si vous avez plusieurs comptes Microsoft et/ou comptes professionnels ou scolaires, vous pouvez les ajouter à Visual Studio. Vous avez ainsi accès aux ressources de n'importe quel compte sans avoir à vous y connecter séparément. Actuellement, Azure, Application Insights, Team Foundation Server et Office 365 prennent en charge l’expérience de connexion simplifiée. D'autres services pourront être rajoutés au fil du temps.

Après avoir ajouté plusieurs comptes sur un ordinateur, vous pourrez y accéder si vous vous connectez à Visual Studio sur un autre ordinateur. Il est important de noter que, bien que les noms de comptes soient itinérants, les informations d'identification ne le sont pas. Par conséquent, vous devrez entrer les informations d'identification de ces autres comptes la première fois que vous essayerez d'utiliser leurs ressources sur le nouvel ordinateur.

Cette procédure pas à pas montre comment ajouter plusieurs comptes à Visual Studio et comment déterminer si les ressources accessibles à partir de ces comptes sont reflétées dans des endroits comme la boîte de dialogue **Ajouter un service connecté** , l' **Explorateur de serveurs**et **Team Explorer**.

## <a name="sign-in-to-visual-studio"></a>Connectez-vous à Visual Studio

- Connectez-vous à Visual Studio avec un compte Microsoft ou un compte professionnel. Votre nom d’utilisateur doit apparaître dans le coin supérieur de la fenêtre, comme ceci :

     ![Utilisateur actuellement connecté](../ide/media/vs2015_username.png)

### <a name="access-your-azure-account-in-server-explorer"></a>Accès à votre compte Azure dans l'Explorateur de serveurs

Appuyez sur **Ctrl**+**Alt**+**S** pour ouvrir **l’Explorateur de serveurs**. Choisissez l’icône **Azure** pour la développer. Les ressources disponibles dans le compte Azure associé à l’ID que vous avez utilisé pour vous connecter à Visual Studio s’affichent alors. L’écran doit ressembler à ce qui suit (à ceci près que vous verrez vos propres ressources).

![Explorateur de serveurs avec le nœud Azure Tools développé](../ide/media/vs2015_serverexplorer.png)

La première fois que vous utilisez Visual Studio sur un appareil spécifique, la boîte de dialogue affiche uniquement les abonnements inscrits sous l'ID avec lequel vous vous êtes connecté à l'IDE. Vous pouvez accéder aux ressources de n’importe lequel de vos autres comptes directement de **l’Explorateur de serveurs** en cliquant avec le bouton droit sur le nœud **Azure**, en choisissant **Gérer et filtrer les abonnements**, puis en ajoutant vos comptes à partir du contrôle de sélecteur de compte. Si vous le souhaitez, vous pouvez ensuite choisir un autre compte en cliquant sur la flèche déroulante vers le bas et en faisant une sélection dans la liste des comptes. Après avoir choisi le compte, vous pouvez choisir les abonnements inscrits sous ce compte que vous voulez afficher dans **l’Explorateur de serveurs**.

![Boîte de dialogue Gérer les abonnements Azure](../ide/media/vs2015_manage_subs.png)

La prochaine fois que vous ouvrez **l’Explorateur de serveurs**, les ressources correspondant à ces abonnements s’affichent.

### <a name="access-your-azure-account-via-add-connected-service-dialog"></a>Accès à votre compte Azure via la boîte de dialogue Ajouter un service connecté

1. Créez un projet Application UWP en C#.

1. Choisissez le nœud du projet dans **l’Explorateur de solutions**, puis choisissez **Ajouter** > **Service connecté**. Dans l’Assistant **Ajouter un service connecté** qui apparaît, vous pouvez voir la liste des services dans le compte Azure associé à votre ID de connexion Visual Studio. Notez que vous n'êtes pas obligé de vous connecter séparément à Azure. Vous devez néanmoins vous connecter aux autres comptes la première fois que vous tentez d'accéder à leurs ressources à partir d'un ordinateur donné.

    > [!WARNING]
    > Si c’est la première fois que vous créez une application UWP dans Visual Studio sur un ordinateur spécifique, vous êtes invité à activer le mode Développement sur votre appareil. Pour cela, accédez à **Paramètres** > **Mises à jour et sécurité** > **Pour les développeurs** sur votre ordinateur. Pour plus d’informations, consultez [Activer votre appareil pour le développement](/windows/uwp/get-started/enable-your-device-for-development).

### <a name="access_azure"></a> Accès à Azure Active Directory dans un projet web

Azure AD permet de prendre en charge l'authentification unique des utilisateurs finaux dans les applications web MVC ASP.NET ou l'authentification AD dans les services API web. L'authentification de domaine est différente de l'authentification de comptes d'utilisateurs individuels ; les utilisateurs qui ont accès à votre domaine Active Directory peuvent utiliser leur compte Azure AD existant pour se connecter à vos applications web. Les applications Office 365 peuvent également utiliser l'authentification de domaine. Pour voir à quoi cela ressemble concrètement, créez une application web (**Fichier** > **Nouveau projet** > **C#** > **Cloud** > **Application web ASP.NET**). Dans la boîte de dialogue **Nouveau projet ASP.NET**, choisissez **Modifier l’authentification**. L'Assistant Authentification s'affiche et vous permet de choisir le type d'authentification à utiliser dans votre application.

![Boîte de dialogue Modifier l'authentification pour ASP.NET](../ide/media/vs2015_change_authentication.png)

Pour plus d’informations sur les différents types d’authentification dans ASP.NET, consultez [Creating ASP.NET web projects in Visual Studio 2013](http://www.asp.net/visual-studio/overview/2013/creating-web-projects-in-visual-studio#orgauth) (les informations relatives à l’authentification sont toujours applicables aux versions actuelles de Visual Studio).

### <a name="access-your-team-foundation-server-tfs-organization"></a>Accéder à votre organisation Team Foundation Server (TFS)

Dans le menu principal, choisissez **Équipe** > **Se connecter à Team Foundation Server** pour afficher la fenêtre **Team Explorer**. Cliquez sur **Sélectionner des projets** puis, dans la zone de liste sous **Sélectionner un serveur Team Foundation Server**, vous devez voir l’URL de votre organisation Team Foundation Server. Lorsque vous sélectionnez l'URL, vous êtes connecté sans avoir à entrer une nouvelle fois vos informations d'identification.

## <a name="add-a-second-user-account-to-visual-studio"></a>Ajouter un deuxième compte d'utilisateur à Visual Studio

Cliquez sur la flèche bas à côté de votre nom d’utilisateur dans le coin supérieur de Visual Studio. Choisissez ensuite l’élément de menu **Paramètres du compte** . La boîte de dialogue **Gestionnaire de comptes** apparaît et affiche le compte avec lequel vous vous êtes connecté. Choisissez le lien **Ajouter un compte** dans l’angle inférieur de la boîte de dialogue pour ajouter un nouveau compte Microsoft ou un nouveau compte professionnel ou scolaire.

![Sélecteur de compte Visual Studio](../ide/media/vs2015_acct_picker.png)

Suivez les instructions pour entrer les nouvelles informations d'identification du compte. L’illustration suivante montre le **Gestionnaire de comptes** après l’ajout du compte professionnel *Contoso.com* par un utilisateur.

![Gestionnaire de comptes](../ide/media/vs2015_accountmanager.gif)

## <a name="revisit-the-add-connected-services-wizard-and-server-explorer"></a>Revisiter l’Assistant Ajout d’un service connecté et l’Explorateur de serveurs

À présent, accédez de nouveau à **l’Explorateur de serveurs**, cliquez avec le bouton droit sur le nœud **Azure**, puis choisissez **Gérer et filtrer les abonnements**. Choisissez le nouveau compte en cliquant sur la flèche déroulante vers le bas située à côté du compte actif, puis choisissez les abonnements que vous voulez afficher dans **l’Explorateur de serveurs**. Vous devez voir tous les services associés à l’abonnement spécifié. Même si vous n’êtes pas connecté à l’IDE Visual Studio avec le deuxième compte, vous êtes connecté aux services et aux ressources de ce compte. Il en va de même pour **Projet** > **Ajouter un service connecté** et **Équipe** > **Se connecter à Team Foundation Server**.

## <a name="see-also"></a>Voir aussi

- [Se connecter à Visual Studio](signing-in-to-visual-studio.md)
- [Se connecter à Visual Studio pour Mac](/visualstudio/mac/signing-in)
