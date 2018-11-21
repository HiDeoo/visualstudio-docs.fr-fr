---
title: Afficher les valeurs de Registre dans le débogueur Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.registers
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- registers, debugging
- register contents
- flags, Registers window
- register groups
- debugging [Visual Studio], Registers window
- Registers window
ms.assetid: 2918ffa2-562f-40d6-9053-ef321bbeb767
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5f236bf43d3667cd4263d205c4588593a973824d
ms.sourcegitcommit: a7de99f36e9ead7ea9e9bac23c88d05ddfc38b00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52257167"
---
# <a name="view-register-values-and-use-the-registers-window-in-the-visual-studio-debugger-c-c-visual-basic-f"></a>Afficher les valeurs de s’inscrire et utiliser la fenêtre registres dans le débogueur Visual Studio (C#, C++, Visual Basic, F#)
La fenêtre Registres est disponible uniquement si le débogage au niveau des adresses est activé dans le **Options** boîte de dialogue, **débogage** nœud, **général** catégorie.  
  
 Le **inscrit** fenêtre affiche le contenu du Registre. Si vous conservez le **inscrit** fenêtre à mesure que vous parcourez votre programme, vous pouvez voir valeurs des registres modifier votre code s’exécute. Les valeurs récemment modifiées s'affichent en rouge. Il est possible de modifier les valeurs des registres. Pour plus d’informations, consultez [Comment : modifier une valeur de Registre](../debugger/how-to-edit-a-register-value.md).  
  
 Pour réduire l’encombrement, la **inscrit** fenêtre classe les registres en groupes, lesquels varient en fonction de la plateforme et le processeur de type. Vous pouvez afficher ou masquer des groupes selon vos besoins. Pour plus d’informations, consultez [Comment : afficher et masquer les groupes de registres](../debugger/how-to-display-and-hide-register-groups.md).  
  
 Pour une introduction avancée aux concepts qui sous-tendent les registres et la fenêtre Registres, consultez [principes fondamentaux de débogage : fenêtre Registres](../debugger/debugging-basics-registers-window.md).  
  
> [!NOTE]
>  Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée. Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-display-the-registers-window"></a>Pour afficher la fenêtre Registres  
  
-   Sur le **déboguer** menu, choisissez **Windows**, puis choisissez **inscrit** (ou choisissez **Ctrl** + **Alt**   +  **G**).  
  
     Le débogueur doit être en cours d'exécution ou en mode arrêt.  
  
    > [!NOTE]
    >  Les informations de Registre ne sont pas disponibles aux applications de script ou SQL.  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts de base du débogage : fenêtre Registres](../debugger/debugging-basics-registers-window.md)   
 [Affichage des données dans le débogueur](../debugger/viewing-data-in-the-debugger.md)   
 [Concepts de base du débogage : fenêtre Registres](../debugger/debugging-basics-registers-window.md)