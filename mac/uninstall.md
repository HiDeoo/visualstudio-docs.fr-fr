---
title: Désinstallation de Visual Studio pour Mac
description: Instructions de désinstallation de Visual Studio pour Mac et des outils associés.
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.technology: vs-ide-install
ms.assetid: 4EB95F75-BC2E-4982-9564-2975805712D8
ms.openlocfilehash: 2c74cf7ddd78bee538a3d37d7e4c4daa4556e3c9
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2018
ms.locfileid: "43224038"
---
# <a name="uninstalling-visual-studio-for-mac"></a>Désinstallation de Visual Studio pour Mac

Il existe plusieurs produits Xamarin qui permettent le développement d’applications multiplateformes, notamment des applications autonomes comme Visual Studio pour Mac.

Vous pouvez utiliser ce guide pour désinstaller chaque produit individuellement en accédant à la section appropriée, ou utiliser les scripts fournis dans la section [Script de désinstallation](#uninstall-script) pour tout désinstaller.

Si Xamarin Studio était installé sur votre machine, vous devez également suivre les instructions fournies dans le guide [Désinstallation de Xamarin](https://docs.microsoft.com/xamarin/cross-platform/get-started/installation/uninstalling-xamarin#uninstall-xamarin-studio-on-mac), en plus des étapes suivantes.

## <a name="uninstall-script"></a>Script de désinstallation

Deux scripts permettent de désinstaller Visual Studio pour Mac et tous les composants de votre machine :

- [Script Visual Studio et Xamarin](#visual-studio-for-mac-and-xamarin-script)
- [Script .NET Core](#net-core-script)

Les sections suivantes fournissent des informations sur le téléchargement et l’utilisation des scripts.

### <a name="visual-studio-for-mac-and-xamarin-script"></a>Script Visual Studio pour Mac et Xamarin

Vous pouvez désinstaller Visual Studio et les composants Xamarin en une seule fois à l’aide du [script de désinstallation](https://raw.githubusercontent.com/MicrosoftDocs/visualstudio-docs/master/mac/resources/uninstall-vsmac.sh).

Ce script de désinstallation contient la plupart des commandes que vous pouvez trouver dans l’article. Le script omet deux éléments principaux qui ne sont pas inclus en raison de possibles dépendances externes :

- **Désinstallation de Mono**
- **Désinstallation d’Android AVD**

Pour exécuter le script, effectuez les étapes suivantes :

1. Cliquez avec le bouton droit sur le script et sélectionnez **Enregistrer sous**. pour enregistrer le fichier sur votre Mac.
2. Ouvrez Terminal et accédez au répertoire de travail où le script a été téléchargé :

    ```bash
    $ cd /location/of/file
    ```
3. Rendez le script exécutable et exécutez-le avec **sudo** :

    ```bash
    $ chmod +x ./uninstall-vsmac.sh
    $ sudo ./uninstall-vsmac.sh
    ```
4. Enfin, supprimez le script de désinstallation.

### <a name="net-core-script"></a>Script .NET Core

Le script de désinstallation pour .NET Core se trouve dans le [dépôt dotnet cli](https://raw.githubusercontent.com/dotnet/cli/master/scripts/obtain/uninstall/dotnet-uninstall-pkgs.sh).

Pour exécuter le script, effectuez les étapes suivantes :

1. Cliquez avec le bouton droit sur le script et sélectionnez **Enregistrer sous**. pour enregistrer le fichier sur votre Mac.
2. Ouvrez Terminal et accédez au répertoire de travail où le script a été téléchargé :

    ```bash
    $ cd /location/of/file
    ```
3. Rendez le script exécutable et exécutez-le avec **sudo** :

    ```bash
    $ chmod +x ./dotnet-uninstall-pkgs.sh
    $ sudo ./dotnet-uninstall-pkgs.sh
    ```
4. Enfin, supprimez le script de désinstallation .NET Core.

## <a name="uninstall-visual-studio-for-mac"></a>Désinstaller Visual Studio pour Mac

La première étape de désinstallation de Visual Studio sur un Mac consiste à localiser **Visual Studio.app** dans le répertoire **/Applications** et à le faire glisser dans la **Corbeille**. Vous pouvez également cliquer avec le bouton droit et sélectionner **Placer dans la Corbeille**, comme illustré dans l’image suivante :

![Placer l’application Visual Studio dans la corbeille](media/uninstall-image1.png)

La suppression de ce bundle d’applications supprime Visual Studio pour Mac, même s’il peut encore exister d’autres fichiers relatifs à Xamarin sur un système de fichiers.

Pour supprimer toutes les traces de Visual Studio pour Mac, les commandes suivantes doivent être exécutées dans Terminal :

```bash
sudo rm -rf "/Applications/Visual Studio.app"
rm -rf ~/Library/Caches/VisualStudio
rm -rf ~/Library/Preferences/VisualStudio
rm -rf ~/Library/Preferences/Visual\ Studio
rm -rf ~/Library/Logs/VisualStudio
rm -rf ~/Library/VisualStudio
rm -rf ~/Library/Preferences/Xamarin/
rm -rf ~/Library/Developer/Xamarin
rm -rf ~/Library/Application\ Support/VisualStudio
rm -rf ~/Library/Application\ Support/VisualStudio/7.0/LocalInstall/Addins/
```

## <a name="uninstall-mono-sdk-mdk"></a>Désinstaller le SDK Mono (MDK)

Mono est une implémentation open source de Microsoft .NET Framework. Il est utilisé par tous les produits Xamarin (Xamarin.iOS, Xamarin.Android et Xamarin.Mac) pour permettre le développement de ces plateformes en C#.

> [!WARNING]
> Il existe d’autres applications en dehors de Visual Studio pour Mac qui utilisent également Mono, comme Unity.
> Vérifiez qu’il n’existe pas d’autres dépendances de Mono avant de le désinstaller.

Pour supprimer le framework Mono sur une machine, exécutez les commandes suivantes dans Terminal :

```bash
sudo rm -rf /Library/Frameworks/Mono.framework
sudo pkgutil --forget com.xamarin.mono-MDK.pkg
sudo rm -rf /etc/paths.d/mono-commands
```

## <a name="uninstall-xamarinandroid"></a>Désinstaller Xamarin.Android

Plusieurs éléments sont nécessaires pour l’installation et l’utilisation de Xamarin.Android, comme Android SDK et le Java SDK.

Utilisez les commandes suivantes pour supprimer Xamarin.Android :

```bash
sudo rm -rf /Developer/MonoDroid
rm -rf ~/Library/MonoAndroid
sudo pkgutil --forget com.xamarin.android.pkg
sudo rm -rf /Library/Frameworks/Xamarin.Android.framework
```

### <a name="uninstall-android-sdk-and-java-sdk"></a>Désinstaller Android SDK et le Java SDK

Android SDK est nécessaire pour le développement d’applications Android. Pour supprimer complètement toutes les composants d’Android SDK, recherchez le fichier **~/Library/Developer/Xamarin/** et placez-le dans la **Corbeille**.

Il n’est pas nécessaire de désinstaller le SDK Java (JDK), car il existe préalablement sous forme de package dans Mac OS X / macOS.

### <a name="uninstall-android-avd"></a>Désinstaller Android AVD

> [!WARNING]
> Il existe d’autres applications en dehors de Visual Studio pour Mac qui utilisent également Android AVD et des composants Android supplémentaires, comme Android Studio.
> La suppression de ce répertoire peut entraîner le fonctionnement incorrect de projets dans Android Studio. 

Pour supprimer tous les AVD Android et les composants Android supplémentaires, utilisez la commande suivante :

```bash
rm -rf ~/.android
```

Pour supprimer seulement les AVD Android, utilisez la commande suivante :

```bash
rm -rf ~/.android/avd
```

 

## <a name="uninstall-xamarinios"></a>Désinstaller Xamarin.iOS

Xamarin.iOS permet le développement d’applications iOS en utilisant C# ou F# avec Visual Studio pour Mac.

Utilisez les commandes suivantes dans Terminal pour supprimer tous les fichiers Xamarin.iOS d’un système de fichiers :

```bash
rm -rf ~/Library/MonoTouch
sudo rm -rf /Library/Frameworks/Xamarin.iOS.framework
sudo rm -rf /Developer/MonoTouch
sudo pkgutil --forget com.xamarin.monotouch.pkg
sudo pkgutil --forget com.xamarin.xamarin-ios-build-host.pkg
sudo pkgutil --forget com.xamarin.xamarin.ios.pkg
```

## <a name="uninstall-xamarinmac"></a>Désinstaller Xamarin.Mac

Vous pouvez supprimer Xamarin.Mac de votre machine à l’aide des deux commandes suivantes pour supprimer respectivement le produit et la licence de votre Mac :

```bash
sudo rm -rf /Library/Frameworks/Xamarin.Mac.framework
rm -rf ~/Library/Xamarin.Mac
```

## <a name="uninstall-workbooks-and-inspector"></a>Désinstaller Workbooks et Inspector

À compter de la version 1.2.2, Xamarin Workbooks & Inspector peuvent être désinstallés à partir d’un terminal en exécutant :

```bash
sudo /Library/Frameworks/Xamarin.Interactive.framework/Versions/Current/uninstall
```

Pour les versions antérieures, vous devez supprimer manuellement les artefacts suivants :

* Supprimez l’application Workbooks dans`"/Applications/Xamarin Workbooks.app"`
* Supprimez l’application Inspector dans`"Applications/Xamarin Inspector.app"`
* Supprimez les compléments : `"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Interactive"` et `"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Inspector"`
* Supprimez Inspector et les fichiers de prise en charge ici : `/Library/Frameworks/Xamarin.Interactive.framework` et `/Library/Frameworks/Xamarin.Inspector.framework`

## <a name="uninstall-the-xamarin-profiler"></a>Désinstallez Xamarin Profiler

```bash
sudo rm -rf "/Applications/Xamarin Profiler.app"
```

## <a name="uninstall-the-visual-studio-installer"></a>Désinstaller Visual Studio Installer

Utilisez les commandes suivantes pour supprimer toutes les traces de Xamarin Universal Installer :

```bash
rm -rf ~/Library/Caches/XamarinInstaller/
rm -rf ~/Library/Caches/VisualStudioInstaller/
rm -rf ~/Library/Logs/XamarinInstaller/
rm -rf ~/Library/Logs/VisualStudioInstaller/
rm -rf ~/Library/Preferences/Xamarin/
rm -rf "~/Library/Preferences/Visual Studio/"
```
