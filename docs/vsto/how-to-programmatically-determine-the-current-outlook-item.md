---
title: 'Comment : déterminer l’élément Outlook actuel par programmation'
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], current
- e-mail [Office development in Visual Studio], current item
- SelectionChange event
- Outlook [Office development in Visual Studio], current item
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 428dccf09235e2feea528bcdaef0a447e02ef58d
ms.sourcegitcommit: 9d2829dc30b6917e89762d602022915f1ca49089
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91585234"
---
# <a name="how-to-programmatically-determine-the-current-outlook-item"></a>Comment : déterminer l’élément Outlook actuel par programmation
  Cet exemple utilise l' `Explorer.SelectionChange` événement pour afficher le nom du dossier actif et des informations sur l’élément sélectionné. Le code affiche ensuite l’élément sélectionné.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a> Exemple
 [!code-vb[Trin_OL_CurrentItem#1](../vsto/codesnippet/VisualBasic/Trin_OL_CurrentItem/thisaddin.vb#1)]
 [!code-csharp[Trin_OL_CurrentItem#1](../vsto/codesnippet/CSharp/Trin_OL_CurrentItem/thisaddin.cs#1)]

## <a name="compile-the-code"></a>Compiler le code
 Cet exemple nécessite :

- Éléments de rendez-vous, de contact et de courrier électronique dans Microsoft Office Outlook.

## <a name="see-also"></a>Voir aussi
- [Vue d’ensemble du modèle objet Outlook](../vsto/outlook-object-model-overview.md)
- [Comment : récupérer un dossier par nom par programmation](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)
- [Comment : Rechercher un contact spécifique par programmation](../vsto/how-to-programmatically-search-for-a-specific-contact.md)
