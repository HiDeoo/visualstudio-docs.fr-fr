---
title: Guide pratique pour spécifier une page de publication pour une application ClickOnce | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], specifying publish page
- Publish Page property
- publishing, ClickOnce
- ClickOnce deployment, specifying publish page
ms.assetid: 9d70eebb-bdee-4b42-8e7e-7a07e199bdf7
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 63356c6eb423ddead54290cc11c865a5102f55f2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68202163"
---
# <a name="how-to-specify-a-publish-page-for-a-clickonce-application"></a>Comment : spécifier une page de publication pour une application ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Lors de la publication d’une [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] application, une page Web par défaut (publish.htm) est générée et publiée avec l’application. Cette page contient le nom de l’application, un lien pour installer l’application et/ou les composants requis, ainsi qu’un lien vers une rubrique d’aide décrivant [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] . La propriété **page de publication** de votre projet vous permet de spécifier un nom pour la page Web de votre [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] application.  
  
 Une fois la page de publication spécifiée, la prochaine fois que vous publiez, elle sera copiée dans l’emplacement de publication. elle ne sera pas remplacée si vous publiez à nouveau. Si vous souhaitez personnaliser l’apparence de la page, vous pouvez le faire sans vous soucier de perdre vos modifications. Pour plus d’informations, consultez [Comment : personnaliser la page Web par défaut de ClickOnce](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md).  
  
 La propriété **page de publication** peut être définie dans la boîte de dialogue Options de **publication** , accessible à partir du volet **publier** du **Concepteur de projet**.  
  
### <a name="to-specify-a-custom-web-page-for-a-clickonce-application"></a>Pour spécifier une page Web personnalisée pour une application ClickOnce  
  
1. Quand un projet est sélectionné dans **Explorateur de solutions**, dans le menu **projet** , cliquez sur **Propriétés**.  
  
2. Sélectionnez le volet **publier** .  
  
3. Cliquez sur le bouton **options** pour ouvrir la boîte de dialogue **options de publication** .  
  
4. Cliquez sur **Déploiement**.  
  
5. Dans la boîte de dialogue **options de publication** , assurez-vous que la case à cocher **ouvrir la page Web de déploiement après la publication** est activée (elle doit être sélectionnée par défaut).  
  
6. Dans la zone **page Web de déploiement :** , entrez le nom de votre page Web, puis cliquez sur **OK**.  
  
### <a name="to-prevent-the-publish-page-from-launching-each-time-you-publish"></a>Pour empêcher le lancement de la page de publication chaque fois que vous publiez  
  
1. Quand un projet est sélectionné dans **Explorateur de solutions**, dans le menu **projet** , cliquez sur **Propriétés**.  
  
2. Sélectionnez le volet **publier** .  
  
3. Cliquez sur le bouton **options** pour ouvrir la boîte de dialogue **options de publication** .  
  
4. Cliquez sur **Déploiement**.  
  
5. Dans la boîte de dialogue **options de publication** , désactivez la case à cocher **ouvrir la page Web de déploiement après la publication** .  
  
## <a name="see-also"></a>Voir aussi  
 [Publication d’applications ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Comment : publier une application ClickOnce à l’aide de l’Assistant Publication](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Comment : personnaliser la page Web par défaut de ClickOnce](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)
