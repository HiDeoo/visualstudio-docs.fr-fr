---
title: 'Comment : ajouter une méthode de mise à jour | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], updating data
- BDC [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating data
- Business Data Connectivity service [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating entity instances
- BDC [SharePoint development in Visual Studio], updating entity instances
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c76373c710908a8ae7edc49c4e26ff7e94336a6d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "86014987"
---
# <a name="how-to-add-an-updater-method"></a>Comment : ajouter une méthode de mise à jour
  Vous pouvez permettre aux utilisateurs de mettre à jour des données d’entreprise dans une liste externe SharePoint en créant une méthode de mise *à jour.* Pour plus d’informations, consultez [concevoir un modèle de connectivité de données métiers](../sharepoint/designing-a-business-data-connectivity-model.md).

### <a name="to-create-an-updater-method"></a>Pour créer une méthode de mise à jour

1. Dans le concepteur BDC, choisissez une entité.

2. Dans la barre de menus, choisissez **Afficher**  >  **les autres**détails de la  >  **méthode BDC**Windows.

    La fenêtre Détails de la méthode BDC s’ouvre. Pour plus d’informations sur cette fenêtre, consultez [vue d’ensemble des outils de conception de modèle BDC](../sharepoint/bdc-model-design-tools-overview.md).

3. Dans la liste **Ajouter une méthode** , choisissez **créer une méthode**de mise à jour.

    Visual Studio ajoute les éléments suivants au modèle. Ces éléments s’affichent dans la fenêtre Détails de la méthode BDC.

   - Une méthode nommée **Update**.

   - Paramètre d’entrée pour la méthode.

   - Descripteur de type pour le paramètre. Par défaut, Visual Studio utilise le descripteur de type d’entité que vous avez défini pour la méthode de recherche (par exemple : contact).

   - Instance de méthode pour la méthode.

     Pour plus d’informations, consultez [concevoir un modèle de connectivité de données métiers](../sharepoint/designing-a-business-data-connectivity-model.md).

   > [!NOTE]
   > Si l’identificateur du type d’entité représente un champ dans une table de base de données qui n’est pas générée automatiquement, affectez la valeur **true**à la propriété de **champ de pré-** mise à jour.

4. Dans **Explorateur de solutions**, ouvrez le menu contextuel du fichier de code de service qui a été généré pour l’entité, puis choisissez **afficher le code**.

    Le fichier de code du service d’entité s’ouvre dans l' **éditeur de code**. Pour plus d’informations sur ce fichier, consultez [créer un modèle de connectivité de données métiers](../sharepoint/creating-a-business-data-connectivity-model.md).

5. Ajoutez du code à la méthode Update pour mettre à jour les données. L’exemple suivant met à jour les informations d’un contact dans l’exemple de base de données AdventureWorks pour SQL Server.

   > [!NOTE]
   > Remplacez la valeur du `ServerName` champ par le nom de votre serveur.

    [!code-csharp[SP_BDC#5](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#5)]
    [!code-vb[SP_BDC#5](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#5)]

## <a name="see-also"></a>Voir aussi
- [Concevoir un modèle de connectivité de données métiers](../sharepoint/designing-a-business-data-connectivity-model.md)
- [Comment : ajouter une méthode de recherche](../sharepoint/how-to-add-a-finder-method.md)
- [Comment : ajouter une méthode de recherche spécifique](../sharepoint/how-to-add-a-specific-finder-method.md)
- [Comment : ajouter une méthode Creator](../sharepoint/how-to-add-a-creator-method.md)
- [Comment : ajouter une méthode de mise à jour](../sharepoint/how-to-add-an-updater-method.md)
- [Comment : ajouter une méthode de suppression](../sharepoint/how-to-add-a-deleter-method.md)
- [Vue d’ensemble des outils de conception de modèle BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Comment : ajouter un paramètre à une méthode](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [Comment : définir une instance de méthode](../sharepoint/how-to-define-a-method-instance.md)
