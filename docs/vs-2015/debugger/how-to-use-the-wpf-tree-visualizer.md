---
title: 'Comment : utiliser le visualiseur de l’arborescence WPF | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- WPF, debugging
- debugging, WPF
ms.assetid: 2a1bf1cd-90f9-4d06-9fb4-1bfc925afef3
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 381dc45351ae03e615afbdd31239869e3dba8e4e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "67825436"
---
# <a name="how-to-use-the-wpf-tree-visualizer"></a>Comment : utiliser le visualiseur de l’arborescence WPF
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez utiliser le visualiseur de l'arborescence WPF pour explorer l'arborescence d'éléments visuels d'un objet WPF et visualiser les propriétés de dépendance WPF pour les objets contenus dans cette arborescence. Pour plus d’informations sur les arborescences d’éléments visuels, consultez [arborescences dans WPF](https://msdn.microsoft.com/library/e83f25e5-d66b-4fc7-92d2-50130c9a6649). Pour plus d’informations sur les propriétés de dépendance, consultez [vue d’ensemble des propriétés de dépendance](https://msdn.microsoft.com/library/d119d00c-3afb-48d6-87a0-c4da4f83dee5).  
  
 Lorsque vous ouvrez le visualiseur de l’arborescence WPF, deux volets s’affichent : l' **arborescence visuelle** à gauche et les **Propriétés du** volet _nom_**:**_type_ à droite. Sélectionnez un objet dans le **volet arborescence** d’éléments visuels, et les **Propriétés du** volet _nom_**:**_type_ sont automatiquement mises à jour pour afficher les propriétés de cet objet.  
  
### <a name="to-open-the-wpf-tree-visualizer"></a>Pour ouvrir le visualiseur de l’arborescence WPF  
  
1. Dans la fenêtre **Espion**, **Automatique** ou **Variables locales** d’un DataTip, cliquez sur la flèche à côté de l’icône de loupe située en regard d’un nom d’objet WPF.  
  
     Une liste de visualiseurs s'affiche.  
  
2. Cliquez sur **Visualiseur de l’arborescence WPF**.  
  
### <a name="to-search-the-visual-tree"></a>Pour effectuer une recherche sur l'arborescence d'éléments visuels  
  
- Dans le volet **Arborescence d’éléments visuels**, tapez la chaîne que vous souhaitez rechercher dans la zone **Recherche**.  
  
  Le visualiseur de l’arborescence WPF recherche immédiatement le premier objet de l’arborescence d’éléments visuels qui correspond à la chaîne que vous avez tapée. Tapez plus de caractères pour rechercher une correspondance plus pertinente.  

  - Cliquez sur **Suivant** pour accéder à la correspondance suivante de l’arborescence d’éléments visuels.  

  - Cliquez sur **Préc.** pour revenir à la correspondance précédente.  

  - Cliquez sur **Effacer** pour effacer les critères de recherche.  

### <a name="to-search-the-properties-list"></a>Pour effectuer une recherche sur la liste des propriétés  
  
- Dans le volet **Propriétés du** _nom_**:**_, tapez la_ chaîne que vous souhaitez rechercher dans la zone de **filtre** .  
  
  Le visualiseur de l'arborescence WPF recherche immédiatement les propriétés qui correspondent à la chaîne que vous avez tapée. À présent, la liste n'affiche que les propriétés correspondant à la chaîne que vous avez tapée. Tapez plus de caractères pour rechercher une correspondance plus pertinente.  

  - Cliquez sur **Effacer** pour effacer les critères de recherche.  
  
### <a name="to-close-the-visualizer"></a>Pour fermer le visualiseur  
  
- Cliquez sur l’icône **Fermer** située dans le coin supérieur droit de la boîte de dialogue.  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : utiliser un visualiseur](../misc/how-to-use-a-visualizer.md)   
 [Créer des visualiseurs personnalisés](../debugger/create-custom-visualizers-of-data.md)   
 [Arborescences dans WPF](https://msdn.microsoft.com/library/e83f25e5-d66b-4fc7-92d2-50130c9a6649)   
 [Vue d’ensemble des propriétés de dépendance](https://msdn.microsoft.com/library/d119d00c-3afb-48d6-87a0-c4da4f83dee5)
