---
title: 'Procédure : Spécifier un nom de Menu Démarrer pour une Application ClickOnce | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eeee762f8bf4ce8df9744e6e39d1f0bd4345cb10
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53947814"
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>Procédure : Spécifier un nom de menu Démarrer pour une application ClickOnce
Quand un [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] application est installée pour une utilisation en ligne et hors connexion, une entrée est ajoutée à la **Démarrer** menu et le **Ajout / Suppression de programmes** liste. Par défaut, le nom complet est le même que le nom de l’assembly d’application, mais vous pouvez modifier le nom d’affichage en définissant **Product name** dans le **Options de publication** boîte de dialogue.  
  
 **Nom de produit** s’affichera sur le *publish.htm* page ; pour une application hors ligne installée, il sera le nom de l’entrée dans le **Démarrer** menu et il sera également le nom qui apparaît dans **Ajouter ou supprimer des programmes**.  
  
 **Nom de l’éditeur** apparaîtra sur la *publish.htm* page ci-dessus **Product name**, et pour une application hors ligne installée, il sera également le nom du dossier qui contient l’application icône dans le **Démarrer** menu.  

 La référence le raccourci ou d’application du menu Démarrer est créée dans *%appdata%\Microsoft\Windows\Start Menu\Programs\\< nom de l’éditeur\>*. La référence de raccourci ou l’application a le même nom que le nom du produit.
  
 Vous pouvez définir le **Product name** et **nom de l’éditeur** propriétés dans le **Options de publication** boîte de dialogue, disponible sur le **publier** page de la **Concepteur de projet**.  
  
### <a name="to-specify-a-start-menu-name"></a>Pour spécifier un nom de menu Démarrer  
  
1.  Après avoir sélectionné un projet dans l’ **Explorateur de solutions**, dans le menu **Projet** , cliquez sur **Propriétés**.  
  
2.  Cliquez sur l’onglet **Publier**.  
  
3.  Cliquez sur le **Options** bouton pour ouvrir la **Options de publication** boîte de dialogue.  
  
4.  Cliquez sur **Description**.  
  
5.  Dans le **Options de publication** boîte de dialogue, entrez le nom à afficher dans la zone **Product name**.  
  
6.  Si vous le souhaitez, vous pouvez entrer un nom de serveur de publication dans **nom de l’éditeur**.  
  
## <a name="see-also"></a>Voir aussi  
 [Publier des applications ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Guide pratique pour publier une application ClickOnce à l’aide de l’Assistant Publication](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)