---
title: 'Comment : modifier une valeur de Registre | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.register.edit
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Registers window, editing register values
- register values
ms.assetid: e27b6bd8-e6d4-4f1d-8a86-9f4047bb1167
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d0337f7c77d1ed601c7a6c13c702f4758cbfdbd
ms.sourcegitcommit: a7de99f36e9ead7ea9e9bac23c88d05ddfc38b00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52257077"
---
# <a name="how-to-edit-a-register-value-c-c-visual-basic-f"></a>Comment : modifier une valeur de Registre (C#, C++, Visual Basic, F#)

La fenêtre Registres est disponible uniquement si le débogage au niveau des adresses est activé dans le **Options** boîte de dialogue, **débogage** nœud.  
  
### <a name="to-change-the-value-of-a-register"></a>Pour modifier la valeur d'un Registre  
  
1.  Dans le **inscrit** fenêtre, utilisez la touche TAB ou la souris pour déplacer l’insertion de point à la valeur que vous souhaitez modifier. Quand vous commencez à taper, le curseur doit se trouver en face de la valeur à remplacer.  
  
2.  Tapez la nouvelle valeur.  
  
    > [!CAUTION]
    >  Modifier des valeurs de registres (principalement des registres EIP et EBP) peut affecter l'exécution du programme.  
  
    > [!CAUTION]
    >  Modifier des valeurs à virgule flottante risque d'entraîner quelques légères imprécisions, dues à la conversion en binaire de la partie décimale des composants fractionnaires. Dans un Registre en virgule flottante, même une modification apparemment anodine risque d'entraîner des changements de certains bits de poids faible.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide pratique pour utiliser la fenêtre Registres](../debugger/how-to-use-the-registers-window.md)