---
title: Inscription d’une fenêtre outil | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tool windows, registering managed
- tool windows, registering
ms.assetid: 8c8c4a24-3da4-497b-9db2-0ddd7cfbfdd2
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8178938715278bf69fe8f4cc1b336bbd19cec04e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "62535636"
---
# <a name="registering-a-tool-window"></a>Enregistrement d’une fenêtre d’outil
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez inscrire vos fenêtres outil à l’aide <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> de et  <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute>  
  
## <a name="example"></a>Exemple  
  
```csharp  
  
      [ProvideToolWindow(typeof(PersistedWindowPane), Style = MsVsShell.VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")] [ProvideToolWindow(typeof(DynamicWindowPane), PositionX=250, PositionY=250, Width=160, Height=180, Transient=true)] [ProvideToolWindowVisibility(typeof(DynamicWindowPane), /*UICONTEXT_SolutionExists*/"f1536ef8-92ec-443c-9ed7-fdadf150da82")]  
[ProvideMenuResource(1000, 1)]  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")]  
public class PackageToolWindow : Package  
{  
```  
  
 Dans le code ci-dessus, le <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> enregistre les fenêtres de l’outil PersistedWindowPane à et DynamicWindowPane avec Visual Studio. La fenêtre outil rendue persistante est ancrée et avec des onglets **Explorateur de solutions**, et la fenêtre dynamique reçoit une position et une taille de départ par défaut. La fenêtre dynamique est rendue temporaire, ce qui indique qu’elle n’est pas créée au démarrage. Cela écrit une valeur DontForceCreate dans la clé ToolWindows du Registre système. Pour plus d’informations, consultez Configuration de l’affichage de la [fenêtre outil](../extensibility/tool-window-display-configuration.md).
