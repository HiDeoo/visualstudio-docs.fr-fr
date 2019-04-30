---
title: 'Procédure : Ajouter une méthode de suppression | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], deleting data
- Business Data Connectivity service [SharePoint development in Visual Studio], Deleter
- BDC [SharePoint development in Visual Studio], Deleter
- BDC [SharePoint development in Visual Studio], removing data
- BDC [SharePoint development in Visual Studio], deleting entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], deleting entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], deleting data
- Business Data Connectivity service [SharePoint development in Visual Studio], removing data
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c9d005ef8bade9f83027c216d875d24aad602449
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63418351"
---
# <a name="how-to-add-a-deleter-method"></a>Procédure : Ajouter une méthode de suppression
  Vous pouvez activer un utilisateur final de supprimer un enregistrement de données à partir d’une liste externe sur un site SharePoint en ajoutant une méthode de suppression pour le modèle. Pour plus d’informations, consultez [concevoir un modèle de connectivité de données métiers](../sharepoint/designing-a-business-data-connectivity-model.md).

### <a name="to-create-a-deleter-method"></a>Pour créer une méthode de suppression

1. Sur le **concepteur BDC**, choisir une entité.

2. Dans la barre de menus, choisissez **vue** > **Windows autres** > **détails de méthode BDC**.

    Le **détails de méthode BDC** fenêtre s’ouvre. Pour plus d’informations sur cette fenêtre, consultez [vue d’ensemble des outils de conception du modèle BDC](../sharepoint/bdc-model-design-tools-overview.md).

3. Dans le **ajouter une méthode** , choisissez **créer une méthode de suppression**.

    Visual Studio ajoute les éléments suivants au modèle. Ces éléments apparaissent dans le **détails de méthode BDC** fenêtre.

   - Une méthode nommée **supprimer**.

   - Un paramètre d’entrée pour la méthode.

   - Un descripteur de type pour le paramètre.

   - Une instance de méthode pour la méthode.

     Pour plus d’informations, consultez [concevoir un modèle de connectivité de données métiers](../sharepoint/designing-a-business-data-connectivity-model.md).

4. Dans **l’Explorateur de solutions**, ouvrez le menu contextuel du service du fichier de code qui a été généré pour l’entité, puis choisissez **afficher le Code**.

    Le fichier de code de service entité s’ouvre dans l’éditeur de Code. Pour plus d’informations sur le fichier de code de service entité, consultez [créer un modèle de connectivité de données métiers](../sharepoint/creating-a-business-data-connectivity-model.md).

5. Ajoutez le code à la méthode de suppression pour supprimer un enregistrement. L’exemple suivant supprime un élément de ligne à partir d’une commande client à l’aide de la base de données AdventureWorks pour SQL Server.

   > [!NOTE]
   > La méthode dans cet exemple utilise deux paramètres d’entrée.

   > [!NOTE]
   > Remplacez la valeur de la `ServerName` champ avec le nom de votre serveur.

    [!code-csharp[SP_BDC#6](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/salesorderdetailservice.cs#6)]
    [!code-vb[SP_BDC#6](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/salesorderdetailservice.vb#6)]

## <a name="see-also"></a>Voir aussi
- [Concevoir un modèle de connectivité de données métiers](../sharepoint/designing-a-business-data-connectivity-model.md)
- [Guide pratique pour Ajouter une méthode de recherche](../sharepoint/how-to-add-a-finder-method.md)
- [Guide pratique pour Ajouter une méthode de recherche spécifique](../sharepoint/how-to-add-a-specific-finder-method.md)
- [Guide pratique pour Ajouter une méthode de création](../sharepoint/how-to-add-a-creator-method.md)
- [Guide pratique pour Ajouter une méthode de mise à jour](../sharepoint/how-to-add-an-updater-method.md)
- [Vue d’ensemble des outils de conception de modèle BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Guide pratique pour Ajouter un paramètre à une méthode](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [Guide pratique pour Définir une instance de méthode](../sharepoint/how-to-define-a-method-instance.md)
