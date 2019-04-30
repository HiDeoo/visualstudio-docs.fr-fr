---
title: 'Procédure : Créer des règles de Validation de Package et de fonctionnalité personnalisée pour les Solutions SharePoint | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
- SharePoint development in Visual Studio, validation rules
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 061a86ee301378bc8b456d370eddd19d2f91bbb6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62966742"
---
# <a name="how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions"></a>Procédure : Créer des règles de validation pour les solutions SharePoint package et fonctionnalité personnalisée
  Vous pouvez créer des règles de validation personnalisées pour vérifier le package de solution généré par Visual Studio. Vous pouvez effectuer une validation complète sur un ensemble de la fonctionnalité ou un package en sélectionnant **Validate** dans le menu contextuel d’un package ou une fonctionnalité dans le **PackagingExplorer**. Validation partielle est effectuée lorsque vous ajoutez de nouveaux éléments de projet SharePoint ou des fonctionnalités au projet pour déterminer si le Package ou la fonctionnalité serait dans un état valide.

### <a name="to-create-a-custom-package-validation-rule"></a>Pour créer une règle de validation de package personnalisé

1. Créez un projet de bibliothèque de classes.

2. Ajoutez des références aux assemblys suivants :

    - Microsoft.VisualStudio.SharePoint

    - System.ComponentModel.Composition

3. Créer une classe qui implémente l’une des interfaces suivantes :

    - Pour créer une règle de validation de package, implémentez le <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> interface.

    - Pour créer une règle de validation de fonctionnalité, implémentez le <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> interface.

4. Ajouter le <xref:System.ComponentModel.Composition.ExportAttribute> à la classe. Cet attribut permet à Visual Studio détecter et charger votre règle de validation. Passer le <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> ou <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> type au constructeur d’attribut.

## <a name="example"></a>Exemple
 L’exemple de code suivant montre comment créer une règle de validation de fonctionnalité personnalisée.

 [!code-vb[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/VisualBasic/featurevalidation/extension/customvalidationrule.vb#1)]
 [!code-csharp[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/CSharp/featurevalidation/extension/customfeaturevalidationrule.cs#1)]

## <a name="compile-the-code"></a>Compiler le code
 Cet exemple nécessite des références aux assemblys suivants :

- Microsoft.VisualStudio.SharePoint.

- System.ComponentModel.Composition.

## <a name="deploy-the-extension"></a>Déployer l’extension
 Pour déployer l’extension, créez un [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] package d’extension (VSIX) pour l’assembly et tous les autres fichiers que vous souhaitez distribuer avec l’extension. Pour plus d’informations, consultez [des outils de déploiement des Extensions pour SharePoint dans Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Voir aussi
- [Étendre le déploiement et empaquetage de SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)
