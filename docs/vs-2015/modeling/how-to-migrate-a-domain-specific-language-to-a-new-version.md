---
title: 'Procédure : migrer un langage spécifique à un domaine vers une nouvelle version | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 6a1ae073-443e-45ca-8bc9-9b944362b449
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 45f7b38f7dbb6ea470b2d9e186dc8e6bf4b33b1e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72657325"
---
# <a name="how-to-migrate-a-domain-specific-language-to-a-new-version"></a>Comment : migrer un langage spécifique à un domaine vers une nouvelle version
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez migrer des projets qui définissent et utilisent le langage spécifique à un domaine à [!INCLUDE[vs2010](../includes/vs2010-md.md)] partir de la version de [!INCLUDE[dsl](../includes/dsl-md.md)] qui a été distribuée avec [!INCLUDE[vs_orcas_long](../includes/vs-orcas-long-md.md)] .

 Un outil de migration est fourni dans le cadre de [!INCLUDE[vssdk_current_long](../includes/vssdk-current-long-md.md)] . L’outil convertit [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] des projets et des solutions qui utilisent ou définissent des outils DSL.

 Vous devez exécuter l’outil de migration explicitement : il n’est pas lancé automatiquement lorsque vous ouvrez une solution dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] . L’outil et le document d’aide détaillé se trouvent dans ce chemin d’accès :

 **% Program Files%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**

## <a name="before-you-migrate-your-dsl-projects"></a>Avant de migrer vos projets DSL
 L’outil de migration modifie les [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] fichiers projet (**. csproj**) et les fichiers solution (**. sln**).

#### <a name="to-prepare-projects-for-migration"></a>Pour préparer des projets pour la migration.

- Vérifiez que les fichiers **. csproj** et **. sln** peuvent être écrits. S’ils sont sous contrôle de code source, assurez-vous qu’ils sont extraits.

- Effectuez une copie des dossiers que vous souhaitez migrer.

## <a name="migrating-a-collection-of-projects"></a>Migration d’une collection de projets

#### <a name="to-migrate-dsl-projects-and-solutions-to-visual-studio-2010"></a>Pour migrer des projets et des solutions DSL vers Visual Studio 2010

1. Démarrez l’outil de migration DSL.

   - Vous pouvez double-cliquer sur l’outil dans l’Explorateur Windows (ou l’Explorateur de fichiers) ou démarrer l’outil à partir d’une invite de commandes. L’outil se trouve à cet emplacement :

        **%ProgramFiles%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**

2. Choisissez un dossier qui contient les solutions et les projets que vous souhaitez convertir.

   - Entrez le chemin d’accès dans la zone située en haut de l’outil, ou cliquez sur **Parcourir**.

     L’outil de migration affiche une arborescence de projets qui définissent ou utilisent DSL. L’arborescence comprend tous les projets qui utilisent les assemblys **Microsoft. VisualStudio. Modeling. SDK** ou **TextTemplating** .

3. Examinez l’arborescence des projets et décochez les projets que vous ne souhaitez pas convertir.

   - Sélectionnez un projet ou une solution pour afficher la liste des modifications apportées par l’outil.

       > [!NOTE]
       > Les cases à cocher qui s’affichent en regard des noms de dossiers n’ont aucun effet. Vous devez développer les dossiers pour inspecter les projets et les solutions.

4. Convertissez les projets.

   1. Cliquez sur **convertir**.

        Avant la conversion de chaque fichier projet, une copie de _Project_**. csproj** est enregistrée en tant que _projet_**. VS2008. csproj**

        Une copie de chaque _solution_**. sln** est enregistrée en tant que _solution_**. VS2008. sln**

   2. Examinez toutes les conversions ayant échoué signalées.

        Les erreurs sont signalées dans la fenêtre texte. En outre, l’arborescence affiche un indicateur rouge sur chaque nœud qui n’a pas pu être converti. Vous pouvez cliquer sur le nœud pour obtenir plus d’informations sur cet échec.

5. **Transformez tous les modèles** dans des solutions contenant des projets convertis avec succès.

   1. Ouvrez la solution.

   2. Cliquez sur le bouton **transformer tous les modèles** dans l’en-tête de Explorateur de solutions.

       > [!NOTE]
       > Vous pouvez faire en sorte que cette étape soit inutile. Pour plus d’informations, consultez [automatisation de la transformation de tous les modèles](https://msdn.microsoft.com/b63cfe20-fe5e-47cc-9506-59b29bca768a).

6. Mettez à jour votre code personnalisé dans les projets convertis.

   - Essayez de générer les projets, puis examinez les échecs.

   - Testez votre concepteur.

## <a name="see-also"></a>Voir aussi
 [Nouveautés de la visualisation et de la modélisation dans le SDK](../misc/what-s-new-in-visualization-and-modeling-sdk.md)
