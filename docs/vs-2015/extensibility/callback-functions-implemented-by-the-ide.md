---
title: Fonctions de rappel implémentées par l’IDE | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, callback functions
- callback functions, source control plug-ins
ms.assetid: 4a8833f0-6ac0-4ea7-9400-8275aa991468
caps.latest.revision: 25
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: df2daef11303e85d5fe2d0bf33e3df038081db64
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68184532"
---
# <a name="callback-functions-implemented-by-the-ide"></a>Fonctions de rappel implémentées par l’IDE
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour rendre l’intégration de l’environnement de développement intégré (IDE) aussi fluide que possible et offrir une expérience d’utilisateur final unifiée, le plug-in de contrôle de code source peut utiliser des fonctions de rappel implémentées par l’IDE. Le plug-in peut appeler ces fonctions aux moments opportuns pendant une opération de contrôle de code source pour passer des informations à l’IDE ; l’IDE peut ensuite afficher ces informations sous la forme d’éléments incorporés dans son interface utilisateur native. L’utilisateur a une expérience moins fragmentée dans ce scénario que si le plug-in utilisait sa propre interface utilisateur.  
  
 Le fichier d’en-tête requis est SCC. h. L’emplacement par défaut est \Program Files\VSIP 8.0 \ EnvSDK\common\inc \\ . Il se trouve également dans le dossier VSIP qui contient l’exemple de plug-in de contrôle de code source dans \Program Files\VSIP 8.0 \ MSSCCI \\ .  
  
## <a name="in-this-section"></a>Dans cette section  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 Décrit la fonction de rappel utilisée par [SccOpenProject](../extensibility/sccopenproject-function.md) pour afficher les messages du plug-in de contrôle de code source via l’IDE.  
  
 [POPLISTFUNC](../extensibility/poplistfunc.md)  
 Décrit la fonction de rappel utilisée par [SccPopulateList](../extensibility/sccpopulatelist-function.md) lorsque l’IDE ne dispose pas d’un accès complet aux informations qui sont uniquement disponibles pour le plug-in de contrôle de code source, comme une liste complète des fichiers sous contrôle de version.  
  
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)  
 Décrit la fonction de rappel utilisée par l’opération [SccQueryChanges](../extensibility/sccquerychanges-function.md) .  
  
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)  
 Décrit la fonction de rappel utilisée par l’opération [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) .  
  
 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)  
 Décrit la fonction de rappel définie par un appel à [SccSetOption](../extensibility/sccsetoption-function.md) qui permet au plug-in de contrôle de code source de communiquer les modifications de nom à l’IDE.  
  
## <a name="related-sections"></a>Sections connexes  
 [SccOpenProject](../extensibility/sccopenproject-function.md)  
 Ouvre un projet.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 Examine la liste des fichiers pour connaître leur état actuel. En outre, utilise la `pfnPopulate` fonction pour notifier l’appelant lorsqu’un fichier ne correspond pas aux critères de `nCommand` .  
  
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)  
 Examine une liste de répertoires et de fichiers dans un projet ou des projets qui sont sous contrôle de code source. Chaque nom de répertoire et de fichier trouvé est passé à une fonction de rappel.  
  
 [SccQueryChanges](../extensibility/sccquerychanges-function.md)  
 Examine les modifications apportées au nom d’une liste de fichiers. Chaque nom de fichier est passé à une fonction de rappel avec son état de modification.  
  
 [SccSetOption](../extensibility/sccsetoption-function.md)  
 Définit un large éventail d’options. Chaque option commence par `SCC_OPT_xxx` et possède son propre ensemble de valeurs défini.  
  
 [Plug-ins de contrôle de code source](../extensibility/source-control-plug-ins.md)  
 Décrit le contenu de la section de référence du kit de développement logiciel (SDK) du plug-in de contrôle de code source.
