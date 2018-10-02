---
title: 'Procédure pas à pas : Téléchargement d’assemblys satellites à la demande avec l’API à l’aide du Concepteur de déploiement ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows Forms, globalization
- ClickOnce deployment, globalization
- localization, Windows Forms
- ClickOnce, on-demand download
- Windows Forms, localization
- ClickOnce deployment, localization
- walkthroughs, localization
ms.assetid: 82b85a47-b223-4221-a17c-38a52c3fb6e2
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 8ed393a17c3489e0133a4a6534deb8f2dab1e428
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47508908"
---
# <a name="walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer"></a>Procédure pas à pas : téléchargement d'assemblys satellites à la demande avec l'API du déploiement ClickOnce à l'aide du concepteur
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [procédure pas à pas : téléchargement d’assemblys satellites à la demande avec le ClickOnce déploiement API en utilisant le concepteur](https://docs.microsoft.com/visualstudio/deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer).  
  
Les applications Windows Forms peuvent être configurées pour plusieurs cultures à l’aide d’assemblys satellites. Un *assembly satellite* contient des ressources d’application pour une culture autre que la culture par défaut de l’application.  
  
 Comme indiqué dans [localisation d’Applications ClickOnce](../deployment/localizing-clickonce-applications.md), vous pouvez inclure plusieurs assemblys satellites pour plusieurs cultures au sein du même [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] déploiement. Par défaut, [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] télécharge tous les assemblys satellites de votre déploiement sur l'ordinateur client, même si un seul client n'a probablement besoin que d'un assembly satellite.  
  
 Cette procédure pas à pas explique comment marquer vos assemblys satellites comme étant facultatifs et télécharger uniquement l'assembly dont a besoin un ordinateur client pour ses paramètres de culture actuels.  
  
> [!NOTE]
>  À des fins de test, les exemples de code suivants définissent par programmation la culture avec la valeur `ja-JP`. Consultez la section « Étapes suivantes » plus loin dans cette rubrique pour plus d'informations sur l'adaptation de ce code à un environnement de production.  
  
### <a name="to-mark-satellite-assemblies-as-optional"></a>Pour marquer les assemblys satellites comme étant facultatifs  
  
1.  Générez votre projet. Vous obtenez des assemblys satellites pour toutes les cultures dans lesquelles vous effectuez la localisation.  
  
2.  Avec le bouton droit sur le nom de votre projet dans l’Explorateur de solutions, puis cliquez sur **propriétés**.  
  
3.  Cliquez sur le **publier** onglet, puis cliquez sur **fichiers d’Application**.  
  
4.  Sélectionnez le **afficher tous les fichiers** case à cocher pour afficher les assemblys satellites. Par défaut, tous les assemblys satellites sont inclus dans votre déploiement et sont visibles dans cette boîte de dialogue.  
  
     Un assembly satellite aura un nom sous la forme *isoCode*\ApplicationName.resources.dll, où *isoCode* est un identificateur de langue au format RFC 1766.  
  
5.  Cliquez sur **nouveau...**  dans le **groupe de téléchargement** liste pour chaque identificateur de langue. Quand vous êtes invité à entrer un nom de groupe de téléchargement, indiquez l'identificateur de langue. Par exemple, pour un assembly satellite japonais, spécifiez le nom de groupe de téléchargement `ja-JP`.  
  
6.  Fermer le **fichiers d’Application** boîte de dialogue.  
  
### <a name="to-download-satellite-assemblies-on-demand-in-c"></a>Pour télécharger des assemblys satellites à la demande en C#  
  
1.  Ouvrez le fichier Program.cs. Si vous ne voyez pas ce fichier dans l’Explorateur de solutions, sélectionnez votre projet et sur le **projet** menu, cliquez sur **afficher tous les fichiers**.  
  
2.  Utilisez le code suivant pour télécharger l'assembly satellite approprié et démarrer votre application.  
  
     [!code-csharp[ClickOnce.SatelliteAssemblies#1](../snippets/csharp/VS_Snippets_Winforms/ClickOnce.SatelliteAssemblies/CS/Program.cs#1)]  
  
### <a name="to-download-satellite-assemblies-on-demand-in-visual-basic"></a>Pour télécharger des assemblys satellites à la demande en Visual Basic  
  
1.  Dans le **propriétés** fenêtre de l’application, cliquez sur le **Application** onglet.  
  
2.  En bas de la page d’onglets, cliquez sur **afficher les événements Application**.  
  
3.  Ajoutez les importations suivantes au début du fichier ApplicationEvents.VB.  
  
     [!code-vb[ClickOnce.SatelliteAssembliesVB#1](../snippets/visualbasic/VS_Snippets_Winforms/ClickOnce.SatelliteAssembliesVB/VB/ApplicationEvents.vb#1)]  
  
4.  Ajoutez le code suivant à la classe `MyApplication`.  
  
     [!code-vb[ClickOnce.SatelliteAssembliesVB#2](../snippets/visualbasic/VS_Snippets_Winforms/ClickOnce.SatelliteAssembliesVB/VB/ApplicationEvents.vb#2)]  
  
## <a name="next-steps"></a>Étapes suivantes  
 Dans un environnement de production, vous aurez probablement besoin de supprimer la ligne dans les exemples de code qui définit <xref:System.Threading.Thread.CurrentUICulture%2A> avec une valeur spécifique, car les ordinateurs clients ont la valeur correcte définie par défaut. Quand votre application s’exécute sur un ordinateur client japonais, par exemple, <xref:System.Threading.Thread.CurrentUICulture%2A> aura la valeur `ja-JP` par défaut. La définition par programmation est un bon moyen de tester vos assemblys satellites avant de déployer votre application.  
  
## <a name="see-also"></a>Voir aussi  
 [Procédure pas à pas : Téléchargement d’assemblys satellites à la demande avec l’API du déploiement ClickOnce](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)   
 [Localisation des applications ClickOnce](../deployment/localizing-clickonce-applications.md)



