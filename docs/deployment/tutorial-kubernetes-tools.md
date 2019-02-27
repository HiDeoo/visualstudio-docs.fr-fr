---
title: Didacticiel d’outils Kubernetes | Microsoft Docs
ms.date: 06/08/2018
ms.topic: conceptual
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- azure
ms.openlocfilehash: e819e4935a14d3902245432b5a5c843071af0fbf
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56843232"
---
# <a name="get-started-with-visual-studio-kubernetes-tools"></a>Bien démarrer avec Visual Studio Tools de Kubernetes

Les outils Kubernetes de Visual Studio vous aider à rationaliser le développement d’applications en conteneur ciblant Kubernetes. Visual Studio peut automatiquement créer les fichiers de configuration en tant que code nécessaires pour prendre en charge le déploiement de Kubernetes, telles que des graphiques Dockerfiles et Helm. Vous pouvez déboguer votre code dans un cluster Azure Kubernetes Service (AKS) en direct à l’aide d’espaces de développement Azure, ou publier directement sur un cluster AKS à partir de Visual Studio.

Ce didacticiel couvre l’utilisation de Visual Studio pour ajouter la prise en charge de Kubernetes à un projet et publier sur AKS. Si vous êtes principalement intéressé par l’utilisation [Azure Dev espaces](https://aka.ms/get-azds) pour déboguer et tester votre projet en cours d’exécution dans ACS, vous pouvez passer à la [didacticiel d’Azure Dev espaces](https://docs.microsoft.com/azure/dev-spaces/get-started-netcore-visualstudio) à la place.

## <a name="prerequisites"></a>Prérequis

Pour tirer parti de cette nouvelle fonctionnalité, vous devez :

- La dernière version de [Visual Studio 2017](https://visualstudio.microsoft.com/download) avec la *ASP.NET et développement web* charge de travail.

- Le [outils Kubernetes pour Visual Studio](https://aka.ms/get-vsk8stools), disponible en téléchargement séparé.

- [Docker pour Windows](https://store.docker.com/editions/community/docker-ce-desktop-windows) installé sur votre station de travail de développement (autrement dit, où vous exécutez Visual Studio), si vous souhaitez générer des images Docker, déboguer les conteneurs Docker s’exécutant localement, ou publier dans AKS. (Est docker *pas* requis pour générer et déboguer les conteneurs Docker dans ACS à l’aide d’espaces de développement Azure.)

- Si vous souhaitez publier sur AKS à partir de Visual Studio (*pas* requis pour le débogage dans ACS à l’aide d’Azure Dev espaces) :

    1.  Le [AKS outils de publication](https://aka.ms/get-vsk8spublish), disponible en téléchargement séparé.

    1.  Un cluster Azure Kubernetes Service. Pour plus d’informations, consultez [création d’un cluster AKS](/azure/aks/kubernetes-walkthrough-portal#create-aks-cluster). Veillez à [se connecter au cluster](/azure/aks/kubernetes-walkthrough#connect-to-the-cluster) à partir de votre station de travail de développement.

    1.  Helm CLI est installée sur votre station de travail de développement. Pour plus d’informations, consultez [installation de Helm](https://github.com/kubernetes/helm/blob/master/docs/install.md).

    1.  Helm configuré sur votre cluster AKS à l’aide de la `helm init` commande. Pour plus d’informations sur la façon de procéder, consultez [comment configurer Helm](/azure/aks/kubernetes-helm#configure-helm).

## <a name="create-a-new-kubernetes-project"></a>Créer un nouveau projet de Kubernetes

Une fois que vous avez installé les outils appropriés, lancez Visual Studio et créez un nouveau projet. Sous **Cloud**, choisissez le **Application conteneur pour Kubernetes** type de projet. Sélectionnez ce type de projet et choisissez **OK**.

![Capture d’écran de création d’un nouveau projet d’application de Kubernetes](media/k8s-tools-new-k8s-app.png)

Vous pouvez ensuite choisir quel type d’ASP.NET Core application web à créer. Choisissez **Web Application** et choisissez **OK**. Habituelles **activer la prise en charge Docker** option n’apparaît pas dans cette boîte de dialogue.  Prise en charge de docker est activée par défaut pour une application de conteneur pour Kubernetes.

![Capture d’écran de sélection de l’application web](media/k8s-tools-web-app-selection-screen.png)

## <a name="add-kubernetes-support-to-an-existing-project"></a>Ajouter la prise en charge de Kubernetes à un projet existant

Ou bien, vous pouvez ajouter prise en charge de Kubernetes à un projet d’application web ASP.NET Core existant. Pour ce faire, avec le bouton droit sur le projet, puis choisissez **ajouter** > **prise en charge de conteneurs Orchestrator**.

![Élément de menu de capture d’écran d’orchestrateur de conteneurs ajouter](media/k8s-tools-add-container-orchestrator.png)

Dans la boîte de dialogue, sélectionnez « Kubernetes/Helm » et choisissez **OK**.

![Boîte de dialogue de capture d’écran d’orchestrateur de conteneurs ajouter](media/k8s-tools-add-container-orchestrator-dialog-box.PNG)

## <a name="what-visual-studio-creates-for-you"></a>Ce que Visual Studio crée pour vous

Après avoir créé un nouveau **Application conteneur pour Kubernetes** projet ou l’ajout de prise en charge d’orchestrateur de conteneurs Kubernetes à un projet existant, vous consultez des fichiers supplémentaires dans votre projet qui facilitent le déploiement sur Kubernetes.

![Capture d’écran de l’Explorateur de solutions après avoir ajouté la prise en charge de l’orchestrateur de conteneurs](media/k8s-tools-solution-explorer.png)

Les fichiers ajoutés sont :

- un fichier Dockerfile, ce qui vous permet de générer une commande Docker image de conteneur qui héberge cette application web. Comme vous le verrez, les outils de Visual Studio s’appuie sur ce fichier Dockerfile lors du débogage et de déploiement sur Kubernetes. Si vous préférez travailler directement avec l’image Docker, vous pouvez avec le bouton droit sur le fichier Dockerfile et choisissez **génération d’Image Docker**.

   ![Option de capture d’écran de génération Docker d’Image](media/k8s-tools-build-docker-image.png)

- un graphique Helm et un *graphiques* dossier. Ces fichiers yaml composent le graphique Helm pour l’application, vous pouvez utiliser pour déployer sur Kubernetes. Pour plus d’informations sur Helm, consultez [ https://www.helm.sh ](https://www.helm.sh).

- *azds.yaml*. Il contient des paramètres pour les espaces de développement Azure, qui fournit une expérience de débogage rapide et itérative dans Azure Kubernetes Service. Pour plus d’informations, veuillez vous reporter [la documentation Azure Dev espaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces).

## <a name="publish-to-azure-kubernetes-service-aks"></a>Publier sur Azure Kubernetes Service (AKS)

Avec tous ces fichiers en place, vous pouvez utiliser l’IDE Visual Studio pour écrire et déboguer votre code d’application, tout comme vous avez toujours. Vous pouvez également utiliser [Azure Dev espaces](https://aka.ms/get-azds) pour exécuter et déboguer votre code en temps réel dans un cluster AKS rapidement. Pour plus d’informations, veuillez vous reporter la [didacticiel d’espaces de développement Azure](https://docs.microsoft.com/azure/dev-spaces/get-started-netcore-visualstudio)

Une fois que vous disposez de votre code en cours d’exécution comme vous le souhaitez, vous pouvez publier directement à partir de Visual Studio sur un cluster AKS.

Pour ce faire, vous devez tout d’abord vérifier que vous avez installé tous les éléments comme décrit dans la [conditions préalables](#prerequisites) section sous l’élément pour la publication sur AKS, puis exécutez toutes les étapes de ligne de commande donné dans les liens. Ensuite, configurez un profil de publication qui publie votre image de conteneur Azure Container Registry (ACR). ACS peut extraire votre image de conteneur à partir d’ACR, puis le déployer dans le cluster.

1. Dans **l’Explorateur de solutions**, avec le bouton droit sur votre *projet* et choisissez **publier**.

   ![Capture d’écran de publier un élément de menu](media/k8s-tools-publish-project.png)

2. Dans le **publier** écran, choisissez **Registre de conteneurs** en tant que la publication cible et suivez les invites pour sélectionner votre Registre de conteneurs. Si vous ne disposez pas d’un Registre de conteneurs, choisissez **créer une nouveau registre de conteneurs Azure** pour en créer un à partir de Visual Studio. Pour plus d’informations, consultez [publier votre conteneur dans Azure Container Registry](#publish-your-container-to-azure-container-registry).

   ![Capture d’écran de choix d’un écran de cible de publication](media/k8s-tools-publish-to-acr.png)

3. Dans l’Explorateur de solutions, avec le bouton droit, cliquez sur votre *solution* et cliquez sur **publier sur Azure ACS**.

   ![Capture d’écran de publier à l’élément de menu Azure ACS](media/k8s-tools-publish-solution.png)

4. Choisissez votre abonnement et votre cluster AKS, ainsi que de l’ACR le profil que vous venez de créer de publication. Cliquez ensuite sur **OK**.

   ![Capture d’écran de publier sur l’écran AKS](media/k8s-tools-publish-to-aks.png)

   Cela vous amène à la **publier sur Azure ACS** écran.

5. Choisissez le **Helm configurer** lien pour mettre à jour de la ligne de commande utilisée pour installer les graphiques Helm sur le serveur.

   ![Lien de la capture d’écran de configurer Helm](media/k8s-tools-configure-helm.png)

   La mise à jour de la ligne de commande est utile s’il existe des arguments de ligne de commande personnalisée que vous souhaitez spécifier, par exemple un nom de contexte ou un graphique Kubernetes différents.

   ![Écran de configuration de capture d’écran de Helm](media/k8s-tools-helm-configure-screen.png)

6. Lorsque vous êtes prêt à déployer, cliquez sur le **publier** bouton pour publier votre application sur AKS.

   ![Capture d’écran de publier sur l’écran d’Azure ACS](media/k8s-tools-publish-screen.png)

Félicitations ! Vous pouvez maintenant utiliser toute la puissance de Visual Studio pour tout votre développement d’application de Kubernetes.

## <a name="next-steps"></a>Étapes suivantes

En savoir plus sur le développement de Kubernetes sur Azure en lisant le [documentation AKS](/azure/aks).

En savoir plus sur les espaces de développement Azure en lisant le [documentation des espaces de développement Azure](https://aka.ms/get-azds)
