---
title: Personnalisation des contrôles natifs à l’exécution | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.crt
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- runtime_checks pragma
- debugger, native run-time checks
- /RTC compiler option [C++], native run-time checks
- customizing CRT error checking
- native run-time checks, customizing
ms.assetid: 76a365fe-6439-49db-8603-34058b78e5a8
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 434f2425b1eeefd82b954e47a8ced55491a7ec11
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "65697818"
---
# <a name="native-run-time-checks-customization"></a>Personnalisation des contrôles natifs à l'exécution
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Quand vous compilez avec **/RTC** (vérifications au moment de l’exécution) ou utilisez le `runtime_checks` pragma, la bibliothèque Runtime C fournit des contrôles natifs à l’exécution. Dans certains cas, il est utile de personnaliser le contrôle à l'exécution :  
  
- Pour acheminer des messages de contrôle à l'exécution vers d'autres emplacements que le fichier ou la destination par défaut.  
  
- Pour spécifier une destination de sortie en cas de messages de contrôle à l'exécution venant d'un débogueur tiers.  
  
- Pour rapporter des messages de contrôle à l’exécution en provenance d’un programme compilé avec une version Release de la bibliothèque Runtime C. Les versions finales de la bibliothèque n'utilisent pas `_CrtDbgReportW` pour rapporter les erreurs d'exécution. Elles affichent à la place une boîte de dialogue **Assert** par erreur d’exécution.  
  
  Pour personnaliser le contrôle des erreurs d'exécution, vous pouvez :  
  
- Écrire une fonction permettant d'obtenir un rapport sur les erreurs d'exécution. Pour plus d’informations, consultez [Comment : écrire une fonction de création de rapports d’erreurs au moment de l’exécution](../debugger/how-to-write-a-run-time-error-reporting-function.md).  
  
- Personnaliser la destination des messages d'erreur.  
  
- Demander des informations sur les erreurs de contrôle à l'exécution.  
  
## <a name="customize-the-error-message-destination"></a>Personnaliser la destination des messages d'erreur  
 Si vous utilisez `_CrtDbgReportW` pour rapporter des erreurs, vous pouvez utiliser `_CrtSetReportMode` pour spécifier la destination des messages d'erreur.  
  
 Si vous utilisez une fonction personnalisée pour obtenir vos rapports, associez une erreur à un type de rapport à l'aide de `_RTC_SetErrorType`.  
  
## <a name="query-for-information-about-run-time-checks"></a>Demander des informations sur les contrôles à l'exécution  
 `_RTC_NumErrors` retourne le nombre de types d’erreurs détectés par les vérifications des erreurs au moment de l’exécution. Pour obtenir une brève description de chaque erreur, faites une boucle allant de 0 à la valeur de retour `_RTC_NumErrors`, en transmettant, à chaque boucle, la valeur de l'itération à `_RTC_GetErrDesc`. Pour plus d’informations, consultez [_RTC_NumErrors](https://msdn.microsoft.com/library/7e82adae-38e2-4f8b-bc0b-37bda8109fd1) et [_RTC_GetErrDesc](https://msdn.microsoft.com/library/7994ec2b-5488-4fd4-806d-a166c9a9f927).  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : utiliser les contrôles natifs au moment de l’exécution](../debugger/how-to-use-native-run-time-checks.md)   
 [runtime_checks](https://msdn.microsoft.com/library/ae50b43f-f88d-47ad-a2db-3389e9e7df5b)   
 [_CrtDbgReport, _CrtDbgReportW](https://msdn.microsoft.com/library/6e581fb6-f7fb-4716-9432-f0145d639ecc)
