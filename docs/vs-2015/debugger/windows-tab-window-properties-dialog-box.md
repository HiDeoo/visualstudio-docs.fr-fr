---
title: Onglet fenêtres de la boîte de dialogue Propriétés de la fenêtre | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Window Properties dialog box, Windows Tab
ms.assetid: 9001342a-09a8-4f5e-b6ed-881a3b9d7246
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c474a85499b221a3ee1d5dfd6befb872f6710f63
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68159692"
---
# <a name="windows-tab-window-properties-dialog-box"></a>Onglet Fenêtres de la boîte de dialogue Propriétés de la fenêtre
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Utilisez l’onglet **fenêtres** pour afficher des informations sur les fenêtres associées à la fenêtre sélectionnée. Pour afficher la [boîte de dialogue Propriétés](../debugger/window-properties-dialog-box.md)de la fenêtre, déplacez le focus vers la fenêtre [vue Windows](../debugger/windows-view.md) . Sélectionnez un nœud de fenêtre dans l’arborescence, puis choisissez **Propriétés** dans le menu **affichage** .  
  
 Les paramètres suivants sont disponibles sous l’onglet **Windows** :  
  
|Entrée|Description|  
|-----------|-----------------|  
|**Fenêtre suivante**|Handle de la fenêtre sœur suivante dans la même séquence (ordre de plan) qui apparaît dans la vue de l’arborescence de la fenêtre (« aucun » s’il n’y a aucune fenêtre suivante). Choisissez cette entrée pour afficher les propriétés de la fenêtre suivante.|  
|**Fenêtre précédente**|Handle de la fenêtre sœur précédente dans la même séquence (ordre de plan) qui apparaît dans la vue de l’arborescence de la fenêtre (« None » s’il n’y a aucune fenêtre précédente). Choisissez cette entrée pour afficher les propriétés de la fenêtre précédente.|  
|**Fenêtre parente**|Handle de la fenêtre parente de cette fenêtre ("none" s’il n’y a aucun parent). Choisissez cette entrée pour afficher les propriétés de la fenêtre parente.|  
|**First Child**|Handle de la première fenêtre enfant de la fenêtre, dans la séquence (ordre de plan) affichée dans la vue de l’arborescence de la fenêtre (« aucun » s’il n’y a aucune fenêtre enfant). Choisissez cette valeur pour afficher les propriétés de la première fenêtre enfant.|  
|**Fenêtre propriétaire**|Handle de la fenêtre propriétaire de cette fenêtre. La fenêtre principale d’une application est généralement propriétaire des fenêtres de boîte de dialogue modale du système, par exemple (« aucun » s’il n’y a aucun propriétaire). Choisissez cette entrée pour afficher les propriétés de la fenêtre propriétaire.|
