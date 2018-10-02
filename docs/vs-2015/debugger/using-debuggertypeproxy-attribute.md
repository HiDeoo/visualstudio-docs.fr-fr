---
title: À l’aide de l’attribut DebuggerTypeProxy | Microsoft Docs
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
- attributes [C#], debugger
- DebuggerTypeProxyAttribute class
- DebuggerTypeProxy attribute
ms.assetid: 943f3bb1-993e-4800-a47e-0af78b063014
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa4b5d363366f61b9001a3ac7f476804c0c2de19
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47494721"
---
# <a name="using-debuggertypeproxy-attribute"></a>Utilisation de l'attribut DebuggerTypeProxy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [à l’aide de l’attribut DebuggerTypeProxy](https://docs.microsoft.com/visualstudio/debugger/using-debuggertypeproxy-attribute).  
  
DebuggerTypeProxyAttribute] (assetId:///T:System.Diagnostics.DebuggerTypeProxyAttribute?qualifyHint=False & autoUpgrade = True) spécifie un proxy, ou en remplaçant, pour un type et modifie la façon dont le type est affiché dans les fenêtres du débogueur. Lorsque vous visualisez une variable possédant un proxy, ce dernier remplace le type d’origine dans le **afficher**. La fenêtre de variables du débogueur   n'affiche que les membres publics du type du proxy. Les membres privés ne sont pas affichés.  
  
 Cet attribut peut s'appliquer aux éléments suivants :  
  
-   Structures  
  
-   Classes  
  
-   Assemblys  
  
 Une classe proxy de type doit avoir un constructeur pouvant prendre un argument du type que le proxy remplacera. Le débogueur crée une nouvelle instance de la classe proxy de type chaque fois qu'il doit afficher une variable du type cible. Cela peut avoir des conséquences sur les performances. Par conséquent, vous ne devez pas effectuer d'autres tâches dans le constructeur que celles qui sont absolument nécessaires.  
  
 Pour éviter de trop handicaper les performances, l'évaluateur d'expression n'examine pas les attributs sur le proxy d'affichage du type à moins que le type ne soit développé par l'utilisateur en cliquant sur le symbole + dans la fenêtre de débogage, ou par l'utilisation de <xref:System.Diagnostics.DebuggerBrowsableAttribute>. Vous ne devez donc pas placer d'attributs sur le type d'affichage lui-même. Les attributs peuvent et doivent être utilisés dans le corps du type d'affichage.  
  
 Il sera judicieux de faire du proxy de type une classe privée imbriquée dans la classe ciblée par l'attribut. Cela lui permettra d'accéder facilement aux membres internes.  
  
 Si <xref:System.Diagnostics.DebuggerTypeProxyAttribute> est utilisé au niveau de l'assembly, le paramètre `Target` spécifie le type que le proxy remplacera.  
  
 Pour obtenir un exemple montrant comment utiliser cet attribut avec <xref:System.Diagnostics.DebuggerDisplayAttribute> et <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, consultez[à l’aide de l’attribut DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md).  
  
## <a name="using-generics-with-debuggertypeproxy"></a>Utilisation de génériques avec DebuggerTypeProxy  
 La prise en charge des génériques est limitée. Pour C#, `DebuggerTypeProxy` prend en charge uniquement les types ouverts. Un type ouvert, également appelé type non construit, est un type générique qui n’a pas été instancié avec des arguments pour ses paramètres de type. Les types fermés, également appelés types construits, ne sont pas pris en charge.  
  
 La syntaxe pour un type ouvert a l'aspect suivant :  
  
 `Namespace.TypeName<,>`  
  
 Si vous utilisez un type générique comme cible dans `DebuggerTypeProxy`, vous devez utiliser cette syntaxe. Le mécanisme `DebuggerTypeProxy` déduit les paramètres de type.  
  
 Pour plus d’informations sur les types ouverts et fermés en c#, consultez le [spécification du langage c#](http://msdn.microsoft.com/library/e5d5a5cc-636b-4bff-b9c8-a8edc6207c22), section 20.5.2 Open et fermé de types.  
  
 Visual Basic n'ayant pas de syntaxe de type ouvert, vous ne pouvez pas faire la même chose en Visual Basic. À la place, vous devez utiliser une représentation sous forme de chaîne du nom de type ouvert.  
  
 `"Namespace.TypeName'2"`  
  
## <a name="see-also"></a>Voir aussi  
 [À l’aide de l’attribut DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)   
  [Amélioration du débogage avec les attributs d’affichage de débogueur](http://msdn.microsoft.com/library/72bb7aa9-459b-42c4-9163-9312fab4c410)



