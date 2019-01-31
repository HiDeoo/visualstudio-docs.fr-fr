---
title: Guide de l’administrateur Visual Studio
titleSuffix: ''
description: En savoir plus sur le déploiement de Visual Studio dans un environnement d’entreprise.
ms.date: 05/29/2018
ms.custom: seodec18
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 507a26290143bd3a5605e3b97b388d4cfeef4112
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54985797"
---
# <a name="visual-studio-2017-administrator-guide"></a>Guide de l’administrateur Visual Studio 2017

Dans les environnements d’entreprise, il est courant pour les administrateurs système de déployer des installations sur les utilisateurs finaux à partir d’un partage réseau ou à l’aide d’un logiciel de gestion de systèmes. Nous avons conçu le moteur d’installation de Visual Studio pour prendre en charge le déploiement d’entreprise, ce qui permet aux administrateurs système de créer un emplacement d’installation réseau pour préconfigurer les paramètres d’installation par défaut, déployer des clés de produit pendant le processus d’installation et gérer les mises à jour de produit après un déploiement réussi. Ce guide de l’administrateur fournit des conseils basés sur des scénarios pour un déploiement d’entreprise dans les environnements réseau.

## <a name="deploy-visual-studio-2017-in-an-enterprise-environment"></a>Déployer Visual Studio 2017 dans un environnement d’entreprise

Vous pouvez déployer Visual Studio 2017 sur les stations de travail clientes tant que chaque ordinateur cible satisfait aux [conditions d’installation minimales](/visualstudio/productinfo/vs2017-system-requirements-vs). Que votre déploiement s’effectue à l’aide de logiciels comme System Center ou à l’aide d’un fichier de commandes, vous voulez généralement effectuer les étapes suivantes :

1. [Créer un partage réseau qui contient les fichiers du produit Visual Studio](create-a-network-installation-of-visual-studio.md) à un emplacement réseau.

2. [Sélectionner les charges de travail et les composants](workload-and-component-ids.md) à installer.

3. [Créer un fichier réponse](automated-installation-with-response-file.md) qui contient les options d’installation par défaut. Vous pouvez aussi [générer un script d’installation](use-command-line-parameters-to-install-visual-studio.md) qui utilise des paramètres de ligne de commande pour contrôler l’installation.

4. Éventuellement, [appliquer une clé de produit de licence en volume](automatically-apply-product-keys-when-deploying-visual-studio.md) dans le cadre du script d’installation afin que les utilisateurs n’aient pas à activer le logiciel séparément.

5. Mettez à jour la disposition réseau pour [contrôler le moment où les mises à jour de produit sont remises aux utilisateurs finaux](controlling-updates-to-visual-studio-deployments.md).

6. Si vous le souhaitez, vous pouvez définir des clés de Registre pour [contrôler les éléments mis en cache sur les stations de travail clientes](set-defaults-for-enterprise-deployments.md).

7. Utilisez la technologie de déploiement de votre choix pour exécuter le script généré dans les étapes précédentes sur vos stations de travail de développement cibles.

8. [Actualiser votre emplacement réseau avec les dernières mises à jour](update-a-network-installation-of-visual-studio.md) de Visual Studio en exécutant régulièrement la commande utilisée à l’étape 1 pour ajouter des composants mis à jour.

> [!IMPORTANT]
> Notez que les installations effectuées à partir d’un partage réseau « mémorisent » l’emplacement source dont elles sont issues. Cela signifie que la réparation d’un ordinateur client peut devoir retourner sur le partage réseau à partir duquel le client a été initialement installé. Choisissez soigneusement votre emplacement réseau : sa durée de vie doit être au moins aussi longue que celle des clients Visual Studio 2017 qui s’exécutent dans votre organisation.

## <a name="use-visual-studio-tools"></a>Utiliser Visual Studio Tools

Plusieurs outils sont disponibles pour vous aider à [détecter et à gérer les instances de Visual Studio installées](tools-for-managing-visual-studio-instances.md) sur les ordinateurs clients.

> [!TIP]
> Outre la documentation du guide de l’administrateur, le [blog d’Heath Stewart](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/) constitue une bonne source d’informations sur l’installation de Visual Studio 2017.

## <a name="specify-customer-feedback-settings"></a>Spécifier les paramètres des commentaires client

Par défaut, l’installation de Visual Studio active les commentaires client. Lorsque vous activez la stratégie de groupe, vous pouvez configurer Visual Studio pour désactiver les commentaires client sur des ordinateurs individuels. Pour ce faire, définissez une stratégie basée sur le Registre sur la clé suivante :

**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\SQM**

Entry = **OptIn**

Value = (DWORD)
* **0** est désinscrit
* **1** est inscrit

Pour plus d’informations sur les paramètres des commentaires client, consultez la page [Programme d’amélioration de l’expérience utilisateur Visual Studio](../ide/visual-studio-experience-improvement-program.md).

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Voir aussi

* [Installer Visual Studio 2017](install-visual-studio.md)
* [Utiliser les paramètres de ligne de commande pour installer Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md)
  * [Exemples de paramètres de ligne de commande](command-line-parameter-examples.md)
  * [Informations de référence sur les ID de charge de travail et de composant](workload-and-component-ids.md)
* [Créer une installation réseau de Visual Studio](create-a-network-installation-of-visual-studio.md)
  * [Installer les certificats nécessaires à l’installation hors connexion de Visual Studio](install-certificates-for-visual-studio-offline.md)
* [Automatiser Visual Studio avec un fichier réponse](automated-installation-with-response-file.md)
* [Appliquer automatiquement des clés de produit lors du déploiement de Visual Studio](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [Définir les valeurs par défaut des déploiements d’entreprise de Visual Studio](set-defaults-for-enterprise-deployments.md)
* [Désactiver ou déplacer le cache du package](disable-or-move-the-package-cache.md)
* [Mettre à jour une installation réseau de Visual Studio](update-a-network-installation-of-visual-studio.md)
* [Contrôler les mises à jour applicables aux déploiements de Visual Studio](controlling-updates-to-visual-studio-deployments.md)
* [Outils de détection et de gestion des instances de Visual Studio](tools-for-managing-visual-studio-instances.md)
