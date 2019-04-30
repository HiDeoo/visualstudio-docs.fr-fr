---
title: 'Procédure pas à pas : Déploiement manuel d’une Application ClickOnce qui ne nécessite pas de nouvelle signature et qui conserve les informations de personnalisation | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- branding
- preserved branding information
- ClickOnce deployment, manually
- multiple ClickOnce deployment and branding
- ClickOnce deployment, SDK tools
- customer deployments
- manual ClickOnce deployments
- manifests [ClickOnce]
- ClickOnce applications, deployed by others
ms.assetid: c21822fb-d4ee-42e4-b72d-41ee9786efe5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 50febcb027ec51b62bdde7ea06a7112470cdc247
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63405838"
---
# <a name="walkthrough-manually-deploy-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information"></a>Procédure pas à pas : Déployer manuellement une application ClickOnce qui ne nécessite pas de nouvelle signature et qui conserve les informations de personnalisation
Lorsque vous créez un [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] application et puis de lui donner à un client pour publier et le déploiement, le client a généralement mis à jour le manifeste de déploiement et de signer à nouveau. Si qui est toujours la méthode recommandée dans la plupart des cas, le .NET Framework 3.5 vous permet de créer [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] déploiements peuvent être déployés par les clients sans avoir à régénérer un nouveau manifeste de déploiement. Pour plus d’informations, consultez [ClickOnce de déployer des applications pour les serveurs de test et de production sans nouvelle signature](../deployment/deploying-clickonce-applications-for-testing-and-production-without-resigning.md).

 Lorsque vous créez un [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] application et puis de lui donner à un client pour publier et le déploiement, l’application peut utiliser la personnalisation du client ou conserve la vôtre. Par exemple, si l’application est une application propriétaire unique, vous souhaiterez conserver votre personnalisation. Si l’application est hautement personnalisée pour chaque client, vous souhaiterez probablement utiliser la personnalisation du client. Le .NET Framework 3.5 permet de vous permettent de préserver votre marque, les informations de serveur de publication et signature de sécurité lorsque vous donnez une application à une organisation à déployer. Pour plus d’informations, consultez [applications ClickOnce créer d’autres utilisateurs peuvent déployer](../deployment/creating-clickonce-applications-for-others-to-deploy.md).

> [!NOTE]
> Dans cette procédure pas à pas vous créez les déploiements manuellement en utilisant l’outil de ligne de commande *Mage.exe* ou l’outil graphique *MageUI.exe*. Pour plus d’informations sur les déploiements manuels, consultez [procédure pas à pas : Déployer manuellement une application ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).

## <a name="prerequisites"></a>Prérequis
 Pour effectuer les étapes dans cette procédure pas à pas, vous devez les éléments suivants :

- Une application Windows Forms que vous êtes prêt à déployer. Cette application sera appelée *WindowsFormsApp1*.

- Visual Studio ou le Kit de développement logiciel Windows.

### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageexe"></a>Pour déployer une application ClickOnce avec plusieurs déploiements et la prise en charge de la personnalisation à l’aide de Mage.exe

1. Ouvrez une invite de commandes Visual Studio ou un [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] invite de commandes et accédez au répertoire dans lequel vous souhaitez stocker votre [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] fichiers.

2. Créez un répertoire nommé d’après la version actuelle de votre déploiement. S’il s’agit de la première fois que vous déployez l’application, vous choisirez probablement **1.0.0.0**.

   > [!NOTE]
   > La version de votre déploiement peut être différente de la version de vos fichiers d’application.

3. Créez un sous-répertoire nommé **bin** et copier tous vos fichiers d’application, y compris les fichiers exécutables, les assemblys, les ressources et les fichiers de données.

4. Générer le manifeste d’application avec un appel à Mage.exe.

   ```cmd
   mage -New Application -ToFile 1.0.0.0\WindowsFormsApp1.exe.manifest -Name "Windows Forms App 1" -Version 1.0.0.0 -FromDirectory 1.0.0.0\bin -UseManifestForTrust true -Publisher "A. Datum Corporation"
   ```

5. Signer le manifeste d’application avec votre certificat numérique.

   ```cmd
   mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx
   ```

6. Générer le manifeste de déploiement avec un appel à *Mage.exe*. Par défaut, *Mage.exe* marque votre [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] déploiement sous la forme d’une application installée, afin qu’il peut être exécuté à la fois en ligne et hors connexion. Pour rendre l’application disponible uniquement lorsque l’utilisateur est en ligne, utilisez le `-i` argument avec la valeur `f`. Étant donné que cette application prend en charge plusieurs déploiements, exclure les `-providerUrl` l’argument de *Mage.exe*. (Dans les versions du .NET Framework antérieures à la version 3.5, à l’exclusion `-providerUrl` pour une application hors connexion entraîne une erreur.)

   ```cmd
   mage -New Deployment -ToFile WindowsFormsApp1.application -Name "Windows Forms App 1" -Version 1.0.0.0 -AppManifest 1.0.0.0\WindowsFormsApp1.manifest
   ```

7. Ne vous connectez pas le manifeste de déploiement.

8. Fournissez tous les fichiers au client, ce qui vous allez déployer l’application sur son réseau.

9. À ce stade, le client doit signer le manifeste de déploiement avec son propre certificat généré automatiquement. Par exemple, si le client fonctionne pour une société nommée Adventure Works, il peut générer un certificat auto-signé à l’aide de la *MakeCert.exe* outil. Ensuite, utilisez le *Pvk2pfx.exe* outil pour combiner les fichiers créés par *MakeCert.exe* dans un fichier PFX qui peut être passé à *Mage.exe*.

    ```cmd
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx
    ```

10. Le client utilise ensuite ce certificat pour signer le manifeste de déploiement.

    ```cmd
    mage -Sign WindowsFormsApp1.application -CertFile MyCert.pfx
    ```

11. Le client déploie l’application à leurs utilisateurs.

### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageuiexe"></a>Pour déployer une application ClickOnce avec plusieurs déploiements et la prise en charge de la personnalisation à l’aide de MageUI.exe

1. Ouvrez une invite de commandes Visual Studio ou un [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] invite de commandes et accédez au répertoire dans lequel vous souhaitez stocker votre [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] fichiers.

2. Créez un sous-répertoire nommé **bin** et copier tous vos fichiers d’application, y compris les fichiers exécutables, les assemblys, les ressources et les fichiers de données.

3. Créez un sous-répertoire nommé d’après la version actuelle de votre déploiement. S’il s’agit de la première fois que vous déployez l’application, vous choisirez probablement **1.0.0.0**.

   > [!NOTE]
   > La version de votre déploiement peut être différente de la version de vos fichiers d’application.

4. Déplacer le \\ **bin** répertoire dans le répertoire que vous avez créé à l’étape 2.

5. Démarrez l’outil graphique *MageUI.exe*.

   ```cmd
   MageUI.exe
   ```

6. Créer un nouveau manifeste d’application en sélectionnant **fichier**, **New**, **manifeste d’Application** dans le menu.

7. Sur la valeur par défaut **nom** , entrez le nom et numéro de version de ce déploiement. Vous devez également fournir une valeur pour **Publisher**, qui sera utilisé comme nom de dossier pour le lien de raccourci de l’application dans le menu Démarrer, lorsqu’elle est déployée.

8. Sélectionnez le **Options d’Application** onglet et cliquez sur **utiliser le manifeste d’Application pour les informations d’approbation**. Cela permettra de personnalisation pour ce tiers [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] application.

9. Sélectionnez le **fichiers** onglet et cliquez sur le **Parcourir** situé en regard du **répertoire de l’Application** zone de texte.

10. Sélectionnez le répertoire qui contient vos fichiers d’application que vous avez créé à l’étape 2, puis cliquez sur **OK** dans la boîte de dialogue de sélection de dossier.

11. Cliquez sur le **Populate** pour ajouter tous les fichiers de votre application à la liste des fichiers. Si votre application contient plusieurs fichiers exécutables, marquez le fichier exécutable principal de ce déploiement comme application de démarrage en sélectionnant **Point d’entrée** à partir de la **Type de fichier** liste déroulante. (Si votre application ne contient qu’un seul fichier exécutable, *MageUI.exe* marquera pour vous.)

12. Sélectionnez le **autorisations requises** onglet et sélectionnez le niveau de confiance que votre application doit déclarer. La valeur par défaut est **confiance totale**, ce qui convient à la plupart des applications.

13. Sélectionnez **fichier**, **enregistrer** dans le menu, puis enregistrez le manifeste d’application. Vous devrez signer le manifeste d’application lorsque vous l’enregistrez.

14. Si vous avez un certificat stocké en tant que fichier sur votre système de fichiers, utilisez le **connexion en tant que fichier de certificat** option et sélectionnez le certificat dans le système de fichiers avec les points de suspension (**...** ) bouton.

     - ou -

     Si votre certificat est conservé dans un magasin de certificats est accessible à partir de votre ordinateur, sélectionnez le **signer avec l’option de certificat stockées**, puis sélectionnez le certificat dans la liste fournie.

15. Sélectionnez **fichier**, **New**, **du manifeste de déploiement** dans le menu pour créer votre manifeste de déploiement, puis, sous la **nom** onglet, fournissez un nom et numéro de version (**1.0.0.0** dans cet exemple).

16. Basculez vers le **mettre à jour** onglet et spécifier la fréquence à laquelle vous souhaitez que cette application pour mettre à jour. Si votre application utilise le [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] API de déploiement pour vérifier les mises à jour elle-même, désactivez la case à cocher intitulée **cette application doit rechercher les mises à jour**.

17. Basculez vers le **Application référence** onglet. Vous pouvez préremplir toutes les valeurs de cet onglet en cliquant sur le **sélectionner un manifeste** bouton et en sélectionnant le manifeste d’application que vous avez créé dans les étapes précédentes.

18. Choisissez **enregistrer** et enregistrer le manifeste de déploiement sur le disque. Vous devrez signer le manifeste d’application lorsque vous l’enregistrez. Cliquez sur **Annuler** pour enregistrer le manifeste sans le signer.

19. Fournissez tous les fichiers d’application au client.

20. À ce stade, le client doit signer le manifeste de déploiement avec son propre certificat généré automatiquement. Par exemple, si le client fonctionne pour une société nommée Adventure Works, il peut générer un certificat auto-signé à l’aide de la *MakeCert.exe* outil. Ensuite, utilisez le *Pvk2pfx.exe* outil pour combiner les fichiers créés par *MakeCert.exe* dans un fichier PFX qui peut être passé à *MageUI.exe*.

    ```cmd
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx
    ```

21. Avec le certificat généré, le client signe maintenant le manifeste de déploiement en ouvrant le manifeste de déploiement dans *MageUI.exe*, puis l’enregistrement. Lorsque la signature de la boîte de dialogue s’affiche, le client sélectionne **connexion en tant que fichier de certificat** option et choisit le fichier PFX qu’il a enregistré sur le disque.

22. Le client déploie l’application à leurs utilisateurs.

## <a name="see-also"></a>Voir aussi
- [Mage.exe (outil Manifest Generation and Editing)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)
- [MageUI.exe (outil Manifest Generation and Editing, client graphique)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)
- [MakeCert](/windows/desktop/SecCrypto/makecert)