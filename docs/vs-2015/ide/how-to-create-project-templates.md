---
title: Guide pratique pour créer des modèles de projet | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ExportTemplateWizard
helpviewer_keywords:
- Visual Studio templates, creating project templates
- project templates, metadata files
- Visual Studio templates, project templates
- project templates, custom template locations
- project templates, creating
ms.assetid: a1a6999d-a34c-48a8-b1cf-027eb5c76398
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fb68a9902fc3adf9f2643b52e069cf182d9ca75a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49225508"
---
# <a name="how-to-create-project-templates"></a>Guide pratique pour créer des modèles de projet
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette procédure vous permet de créer un modèle à l’aide de l’Assistant **Exportation de modèle**, qui met en package votre modèle dans un fichier .zip. Vous pouvez également créer des modèles au format de fichier VSIX pour améliorer le déploiement en utilisant l’extension de l’Assistant Exportation de modèle, ou avec les modèles inclus dans le [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)], ou vous pouvez créer manuellement des modèles.  
  
### <a name="to-create-a-custom-project-template-with-the-standard-export-template-wizard"></a>Pour créer un modèle de projet personnalisé avec l’Assistant Exportation de modèle standard  
  
1.  Créez un projet.  
  
    > [!NOTE]
    >  Utilisez uniquement des caractères d’identificateur valides lorsque vous nommez un projet qui sera la source d’un modèle. Un modèle exporté à partir d’un projet nommé avec des caractères non valides peut provoquer des erreurs de compilation dans les futurs projets basés sur le modèle. Pour plus d’informations sur les caractères d’identificateur valides, consultez [Noms d’éléments déclarés](http://msdn.microsoft.com/library/09d8843b-c0dc-4afe-9dab-87c439a69e66).  
  
2.  Modifiez le projet jusqu’à ce qu’il soit prêt à être exporté en tant que modèle.  
  
3.  Selon les besoins, modifiez les fichiers de code pour indiquer où le remplacement des paramètres doit avoir lieu. Pour plus d’informations sur le remplacement des paramètres, consultez [Guide pratique pour substituer des paramètres dans un modèle](../ide/how-to-substitute-parameters-in-a-template.md).  
  
4.  Dans le menu **Fichier**, cliquez sur **Exporter le modèle**. L’Assistant **Exportation de modèle** s’ouvre.  
  
5.  Cliquez sur **Modèle de projet**.  
  
6.  Si vous avez plusieurs projets dans votre solution actuelle, sélectionnez les projets que vous souhaitez exporter vers un modèle.  
  
7.  Cliquez sur **Suivant**.  
  
8.  Sélectionnez une icône et une image d’aperçu pour votre modèle. Ces éléments apparaissent dans la boîte de dialogue **Nouveau projet**.  
  
9. Entrez le nom et la description du modèle.  
  
10. Cliquez sur **Terminer**. Votre projet est exporté dans un fichier .zip et placé dans l’emplacement de sortie spécifié et, s’il est sélectionné, il est importé dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
     Si le [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] est installé, vous pouvez inclure dans un wrapper le modèle fini, dans un fichier .vsix, pour le déployer en utilisant le modèle **Projet VSIX**. Pour plus d’informations, consultez [Bien démarrer avec le modèle de projet VSIX](../extensibility/getting-started-with-the-vsix-project-template.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)   
 [Guide pratique pour créer des modèles d’élément](../ide/how-to-create-item-templates.md)



