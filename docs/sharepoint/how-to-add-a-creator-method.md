---
title: 'Comment : ajouter une méthode Creator | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], Creator
- BDC [SharePoint development in Visual Studio], adding entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entity instances
- BDC [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Creator
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 962e353b5ae82f6dd3eccc2898385fd4b9ee30ee
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "86017068"
---
# <a name="how-to-add-a-creator-method"></a>Comment : ajouter une méthode Creator
  Une méthode Creator ajoute de nouvelles données à la source de données d’une entité. Le service de connectivité de données métiers (BDC) appelle cette méthode quand les utilisateurs choisissent le bouton **nouvel élément** sur le **ruban** d’une liste basée sur le modèle. Pour plus d’informations, consultez [concevoir un modèle de connectivité de données métiers](../sharepoint/designing-a-business-data-connectivity-model.md).

### <a name="to-add-a-creator-method"></a>Pour ajouter une méthode de création

1. Dans le **concepteur BDC**, choisissez une entité.

2. Dans la barre de menus, choisissez **Afficher**  >  **les autres**détails de la  > **méthode BDC**Windows.

    La fenêtre Détails de la **méthode BDC** s’ouvre. Pour plus d’informations sur cette fenêtre, consultez [vue d’ensemble des outils de conception de modèle BDC](../sharepoint/bdc-model-design-tools-overview.md).

3. Dans la liste **Ajouter une méthode** , choisissez **créer une méthode Creator**.

    Visual Studio ajoute les éléments suivants au modèle, et ces éléments s’affichent dans la fenêtre Détails de la **méthode BDC** .

   - Une méthode nommée **Create**.

   - Paramètre d’entrée pour la méthode.

   - Paramètre de retour de la méthode.

   - Descripteurs de type pour les paramètres.

   - Instance de méthode pour la méthode.

     Pour plus d’informations, consultez [concevoir un modèle de connectivité de données métiers](../sharepoint/designing-a-business-data-connectivity-model.md).

4. Dans **Explorateur de solutions**, ouvrez le menu contextuel du fichier de code de service qui a été généré pour l’entité, puis choisissez **afficher le code**.

    Le fichier de code du service d’entité s’ouvre dans l’éditeur de code. Pour plus d’informations sur le fichier de code du service d’entité, consultez [créer un modèle de connectivité de données métiers](../sharepoint/creating-a-business-data-connectivity-model.md).

5. Ajoutez du code à la méthode Creator qui ajoute des données à la source de données. L’exemple suivant ajoute un contact à l’exemple de base de données AdventureWorks pour SQL Server.

   > [!NOTE]
   > Remplacez la valeur du `ServerName` champ par le nom de votre serveur.

    [!code-csharp[SP_BDC#4](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#4)]
    [!code-vb[SP_BDC#4](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#4)]

## <a name="see-also"></a>Voir aussi
- [Concevoir un modèle de connectivité de données métiers](../sharepoint/designing-a-business-data-connectivity-model.md)
- [Comment : ajouter une méthode de recherche](../sharepoint/how-to-add-a-finder-method.md)
- [Comment : ajouter une méthode de recherche spécifique](../sharepoint/how-to-add-a-specific-finder-method.md)
- [Comment : ajouter une méthode de suppression](../sharepoint/how-to-add-a-deleter-method.md)
- [Comment : ajouter une méthode de mise à jour](../sharepoint/how-to-add-an-updater-method.md)
- [Vue d’ensemble des outils de conception de modèle BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Comment : ajouter un paramètre à une méthode](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [Comment : définir une instance de méthode](../sharepoint/how-to-define-a-method-instance.md)
