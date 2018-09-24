---
title: Protection de mot de passe des documents Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- passwords [Office development in Visual Studio], document protections
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 02deaccdd615bae0c948d50abdd41758dc701704
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35670801"
---
# <a name="password-protection-on-office-documents"></a>Protection de mot de passe des documents Office
  Il est possible de définir un mot de passe sur vos documents Microsoft Office Word et les classeurs Microsoft Office Excel afin qu’ils ne peuvent pas être ouverts par une personne ne connaît pas le mot de passe. Cette option est appelée **mot de passe à l’ouverture**.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Vous pouvez créer des projets au niveau du document à l’aide de documents existants et les classeurs qui ont **mot de passe à l’ouverture** activé. Le comportement dans Visual Studio est différent pour les documents Word et Excel qui ont **mot de passe à l’ouverture** activé.  
  
 Pour plus d’informations sur l’activation de **mot de passe à l’ouverture**, consultez l’aide dans Word ou Excel.  
  
## <a name="behavior-of-excel-and-word"></a>Comportement d’Excel et Word  
 Chaque fois que vous ouvrez un classeur Excel dans Visual Studio a **mot de passe à l’ouverture** activée, Excel vous demande le mot de passe. Lorsque vous générez votre solution vous demandera le mot de passe à nouveau, car le document est ouvert pendant la génération.  
  
 La première fois que vous ouvrez un document Word dans Visual Studio a **mot de passe à l’ouverture** activé, Word vous propose le mot de passe. Après avoir entré correctement le mot de passe, **mot de passe à l’ouverture** est supprimé du document et de l’ouverture du document n’aura plus besoin un mot de passe. Si vous souhaitez que le document dans votre solution pour exiger un mot de passe avant qu’il peut être ouvert, vous devez activer **mot de passe à l’ouverture** après la génération finale et avant de déployer la solution.  
  
## <a name="see-also"></a>Voir aussi  
 [Protection des documents dans les solutions au niveau du document](../vsto/document-protection-in-document-level-solutions.md)   
 [Information rights management et vue d’ensemble des extensions de code managé](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Comment : permettre au code à exécuter derrière des documents avec des autorisations restreintes](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Concevoir et créer des solutions Office](../vsto/designing-and-creating-office-solutions.md)  
  
  