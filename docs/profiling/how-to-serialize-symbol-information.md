---
title: Sérialiser les informations de symboles | Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
f1_keywords:
- VS.ToolsOptionsPages.Performance.General
helpviewer_keywords:
- profiling tools, serializing symbol information
- performance tools, serializing symbol information
ms.assetid: 9e0da706-6325-4073-83d1-aeab3b7c137a
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: d644960153a8e342f6442f3750420ea68a61b38f
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90851591"
---
# <a name="how-to-serialize-symbol-information"></a>Guide pratique pour sérialiser les informations de symboles
Vous pouvez sérialiser les symboles nécessaires à l’analyse de votre application. La sérialisation de symboles permet d’ajouter des symboles au fichier .*vsp*. L’ajout d’informations de symboles au fichier .*vsp* permet aux autres utilisateurs d’analyser un rapport de performances sans avoir accès aux symboles d’origine. Si les symboles ne sont pas sérialisés, vous devez disposer des fichiers .*exe* et .*pdb* instrumentés d’origine pour analyser le fichier .*vsp*.

### <a name="to-automatically-serialize-symbol-information"></a>Pour sérialiser automatiquement les informations de symboles

1. Dans le menu **Outils** , cliquez sur **Options**.

     La boîte de dialogue **Options** s’affiche.

2. Cliquez sur **Outils d’analyse des performances**.

3. Sous **Paramètres généraux**, sélectionnez **Sérialiser automatiquement les informations de symboles**.

## <a name="see-also"></a>Voir aussi
- [Configurer des sessions de performance](../profiling/configuring-performance-sessions.md)
- [Comment : référencer les informations de symboles Windows](../profiling/how-to-reference-windows-symbol-information.md)
- [Guide pratique pour enregistrer des fichiers de rapports analysés](/previous-versions/visualstudio/visual-studio-2010/bb763106\(v\=vs.100\))
