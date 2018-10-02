---
title: Considérations sur la sécurité visualiseur | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- visualizers, security
- security [Visual Studio], visualizers
ms.assetid: cdd86bd5-b729-409b-a7c6-374efa091eb1
caps.latest.revision: 25
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f041aa4506906291f429e8825ca42b7ea30f14c4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47508517"
---
# <a name="visualizer-security-considerations"></a>Considérations sur la sécurité du visualiseur
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [considérations de sécurité visualiseur](https://docs.microsoft.com/visualstudio/debugger/visualizer-security-considerations).  
  
L'écriture d'un visualiseur implique d'éventuelles menaces pour la sécurité. Aucune attaque connue n'a été répertoriée concernant ces menaces potentielles, mais les développeurs doivent en être informés et prendre les précautions de sécurité appropriées, tel qu'indiqué ici, pour se protéger contre de futures attaques.  
  
 Les visualiseurs de débogueur requièrent des privilèges plus importants que ceux octroyés par une application de confiance partielle. Les visualiseurs ne se chargent pas lorsque vous êtes arrêté dans du code à confiance partielle. Pour déboguer à l'aide d'un visualiseur, vous devez exécuter le code avec la confiance totale.  
  
## <a name="possible-malicious-debuggee-component"></a>Composant de programme débogué potentiellement malveillant  
 Les visualiseurs sont composés d'au moins deux classes : une du côté débogueur et l'autre du côté du programme débogué. Les visualiseurs sont souvent déployés dans des assemblys séparés placés dans des répertoires spéciaux, mais ils peuvent également être chargés hors de l’élément débogué. Dans ce cas, le débogueur sort le code du programme débogué et l'exécute à l'intérieur du débogueur avec un niveau de confiance totale.  
  
 L'exécution du code côté programme débogué avec la confiance totale devient problématique lorsque le programme débogué n'est pas d'un niveau de confiance suffisant. Si un visualiseur essaie de charger un assembly de confiance partielle à partir de l’élément débogué dans le débogueur, Visual Studio arrête le visualiseur.  
  
 Toutefois, il existe encore une vulnérabilité mineure. Le côté élément débogué peut s’associer à un côté débogueur qui a été chargé à partir d’une autre source (pas l’élément débogué). Le côté programme débogué peut alors indiquer au côté débogueur de confiance qu'il doit exécuter des actions de sa part. Si la classe côté débogueur de confiance expose un mécanisme "supprimer ce fichier", par exemple, l’élément débogué de confiance partielle pourrait appeler ce mécanisme lorsque l’utilisateur appelle son visualiseur.  
  
 Afin d'atténuer cette vulnérabilité, faites attention aux interfaces exposées par votre visualiseur.  
  
## <a name="see-also"></a>Voir aussi  
 [Architecture d’un visualiseur](../debugger/visualizer-architecture.md)   
 [Comment : écrire un visualiseur](../debugger/how-to-write-a-visualizer.md)   
 [Créer des visualiseurs personnalisés](../debugger/create-custom-visualizers-of-data.md)   
 [Affichage des données dans le débogueur](../debugger/viewing-data-in-the-debugger.md)



