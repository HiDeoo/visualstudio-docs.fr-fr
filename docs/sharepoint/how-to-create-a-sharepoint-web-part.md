---
title: 'Comment : créer un composant WebPart SharePoint | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Web Parts [SharePoint development in Visual Studio], adding
- Web Parts [SharePoint development in Visual Studio], creating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2a8c02cce2f55374b4d62ba5663e8b3fe85b55b5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "86016444"
---
# <a name="how-to-create-a-sharepoint-web-part"></a>Comment : créer un composant WebPart SharePoint
  Vous pouvez créer et personnaliser un composant WebPart en ajoutant un élément **WebPart** à un projet SharePoint, puis en modifiant le fichier de code du composant WebPart ou à l’aide d’un concepteur. Pour plus d’informations, consultez [Comment : créer un composant WebPart SharePoint à l’aide d’un concepteur](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md).

### <a name="to-create-a-sharepoint-web-part"></a>Pour créer un composant WebPart SharePoint

1. Créez ou ouvrez un projet SharePoint.

     Pour plus d’informations, consultez [modèles de projet et d’élément de projet SharePoint](../sharepoint/sharepoint-project-and-project-item-templates.md).

2. Sélectionnez le nœud de projet SharePoint dans **Explorateur de solutions** puis choisissez **projet**  >  **Ajouter un nouvel élément**.

3. Dans la boîte de dialogue **Ajouter un nouvel élément** , développez le nœud **SharePoint** , puis choisissez le nœud **2010** .

4. Dans la liste des modèles SharePoint, choisissez **composant WebPart**.

5. Dans la zone **nom** , spécifiez un nom pour le composant WebPart, puis cliquez sur le bouton **Ajouter** .

     Le composant WebPart s’affiche dans **Explorateur de solutions**. Pour plus d’informations sur les fichiers inclus dans un composant WebPart, consultez [créer des composants WebPart pour SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md).

6. Dans **Explorateur de solutions**, ouvrez le fichier de code du composant WebPart que vous venez de créer.

     Par exemple, si le nom de votre composant WebPart est *WebPart1*, ouvrez *WebPart1. vb* (dans Visual Basic) ou *WebPart1.cs* (en C#).

7. Dans le fichier de code, ajoutez des contrôles à la <xref:System.Web.UI.Control.CreateChildControls%2A> méthode.

     Pour obtenir un exemple, consultez [procédure pas à pas : créer un composant WebPart pour SharePoint](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md).

## <a name="see-also"></a>Voir aussi
- [Créer des composants WebPart pour SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)
- [Comment : créer un composant WebPart SharePoint à l’aide d’un concepteur](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)
- [Procédure pas à pas : créer un composant WebPart pour SharePoint](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)
- [Procédure pas à pas : créer un composant WebPart pour SharePoint à l’aide d’un concepteur](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)
