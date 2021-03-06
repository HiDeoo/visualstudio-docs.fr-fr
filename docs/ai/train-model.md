---
title: Soumettre un travail pour l’apprentissage d’un modèle
description: Soumettre un travail pour l’apprentissage d’un modèle à l’aide de Azure Batch AI
ms.custom: SEO-VS-2020
keywords: ai, visual studio, former un modèle, cloud
author: jillre
ms.author: jillfra
manager: jillfra
monikerRange: vs-2017
ms.date: 11/13/2017
ms.topic: how-to
ms.workload:
- azure
ms.openlocfilehash: 110468de264370b22d64dae40cf55e9766804c31
ms.sourcegitcommit: 4ae5e9817ad13edd05425febb322b5be6d3c3425
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/11/2020
ms.locfileid: "90036611"
---
# <a name="train-ai-models-in-azure-batch-ai"></a>Former des modèles IA dans Azure Batch AI

Batch AI est un service géré qui permet aux scientifiques des données et aux chercheurs en IA d’effectuer l’apprentissage de l’IA et d’autres modèles de Machine Learning sur des clusters de machines virtuelles Azure, y compris les machines virtuelles prenant en charge les GPU. Vous décrivez les exigences de votre travail, où trouver les entrées et stocker les sorties, et Batch AI gère le reste. [En savoir plus sur Azure Batch AI](/azure/batch-ai/overview)

Comme il est intégré à Visual Studio Tools pour IA, vous pouvez dynamiquement augmenter la taille des instances des modèles d’apprentissage dans Azure.  Une fois que vous avez [installé Visual Studio Tools pour IA](installation.md), il est facile de créer un projet Python à l’aide de recettes prédéfinies dans la galerie d’exemples Azure Machine Learning.

1. Lancez Visual Studio. Ouvrez **l’Explorateur de serveurs** en ouvrant le menu **AI Tools** (Outils IA) et en choisissant **Sélectionner un cluster**

    ![Sélecteur de cluster](media/train-model/select-cluster.png)

2. Développez **AI Tools** (Outils IA). Toutes les ressources Batch AI dont vous disposez sont détectées automatiquement et apparaissent dans l’Explorateur de serveurs.

    ![Galerie d’exemples](media/train-model/batchai.png)

3. Sélectionnez **Affichage > Team Explorer...** pour ouvrir la fenêtre **Team Explorer**, dans laquelle vous pouvez vous connecter à GitHub ou à Azure DevOps Services, ou bien cloner un dépôt.

    ![Fenêtre Team Explorer montrant Azure DevOps Services, GitHub et le clonage d’un dépôt](media/train-model/team-explorer-devops.png)

4. Dans le champ URL, sous **Dépôts Git locaux**, entrez `https://github.com/Microsoft/samples-for-ai`, entrez un dossier pour les fichiers clonés, puis sélectionnez **Cloner**.

    > [!Tip]
    > Le dossier que vous spécifiez dans Team Explorer est le dossier spécifique pour recevoir les fichiers clonés. Contrairement à la commande `git clone`, la création d’un clone dans Team Explorer ne crée pas automatiquement un sous-dossier avec le nom du dépôt.

5. Une fois le clonage terminé, cliquez sur **Fichier > Ouvrir une solution > Projet/Solution**

    ![Galerie d’exemples](media/train-model/open-solution.png)

6. Ouvrez **samples-for-ai\TensorFlowExamples\TensorFlowExamples.sln** dans le répertoire dans lequel vous avez cloné le dépôt

    ![Galerie d’exemples](media/train-model/tensorflowexamples.png)

7. Définissez le projet MNIST comme **Projet de démarrage**.

    ![Galerie d’exemples](media/train-model/mnist-startup.png)

8. <strong>Cliquez avec le bouton droit sur le **projet MNIST,** **Envoyer la tâche**</strong>.

    ![Galerie d’exemples](media/train-model/submit-job.png)
9. Sélectionnez votre cluster **Azure Batch AI**, puis cliquez sur **Importer**. Sélectionnez le fichier `AzureBatchAI_TF_MNIST.json` pour remplir rapidement quelques valeurs par défaut comme l’image Docker à utiliser. Cliquez ensuite sur **Envoyer**

    ![Galerie d’exemples](media/train-model/submit-batch.png)
