---
title: 'Procédure : créer un ensemble de règles PolicyActivity (hérité) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- PolicyActivity activity, creating rule sets
- Rule Set Editor dialog box
- PolicyActivity activity, selecting rule sets
- Select Rule Set dialog box
- rule sets, creating for PolicyActivity
ms.assetid: f272489d-3342-4511-8b59-6a0fd7a42d70
caps.latest.revision: 4
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0f8599348d204d149f3e28d17d681941ddf476b8
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75849315"
---
# <a name="how-to-create-a-policyactivity-rule-set-legacy"></a>Procédure : créer un ensemble de règles PolicyActivity (héritée)
Cette rubrique décrit comment créer un ensemble de règles d'activité de stratégie à l'aide du [!INCLUDE[wfd1](../includes/wfd1-md.md)] hérité qui cible le [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] ou le [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].

 Après avoir fait glisser un élément d’activité **stratégie** de la **boîte à outils** vers l’aire de conception de workflow, vous pouvez sélectionner une règle existante ou créer un nouvel ensemble de règles pour l’activité [PolicyActivity](https://msdn2.microsoft.com/library/system.workflow.activities.policyactivity.aspx) . Vous sélectionnez un ensemble de règles existant à l’aide de la boîte de [dialogue Sélectionner l’ensemble de règles (hérité)](../workflow-designer/select-rule-set-dialog-box-legacy.md) et vous créez des ensembles de règles à l’aide de la [boîte de dialogue Éditeur d’ensemble de règles (hérité)](../workflow-designer/rule-set-editor-dialog-box-legacy.md).

> [!NOTE]
> Vous pouvez ouvrir la boîte de dialogue [éditeur d’ensemble de règles (hérité)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) directement en double-cliquant sur une activité [PolicyActivity](https://msdn2.microsoft.com/library/system.workflow.activities.policyactivity.aspx) qui se trouve sur l’aire de conception de Workflow.

### <a name="to-select-or-create-a-rule-set-for-a-policyactivity-activity"></a>Pour sélectionner ou créer un ensemble de règles pour une activité PolicyActivity

1. Cliquez avec le bouton droit sur [PolicyActivity](https://msdn2.microsoft.com/library/system.workflow.activities.policyactivity.aspx), puis cliquez sur **Propriétés** pour ouvrir la fenêtre **Propriétés** .

2. Cliquez sur la propriété **RuleSetReference** .

3. Effectuez l’une des actions suivantes :

    - Cliquez sur le **RuleSetReference** ellipses **[...]**, puis sélectionnez un ensemble de règles existant dans la [boîte de dialogue Sélectionner l’ensemble de règles (hérité)](../workflow-designer/select-rule-set-dialog-box-legacy.md). Passez à l'étape 10.

         -ou-

    - Tapez un nom d'ensemble de règles. Cliquez sur le **RuleSetReference** ellipses **[...]**, puis sélectionnez **modifier** dans la [boîte de dialogue Sélectionner l’ensemble de règles (hérité)](../workflow-designer/select-rule-set-dialog-box-legacy.md).

         -ou-

    - Tapez un nom d'ensemble de règles. Développez la propriété **RuleSetReference** et sélectionnez les ellipses **[...]** dans la propriété **RuleSet Definition** .

         La [boîte de dialogue Éditeur d’ensemble de règles (hérité)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) s’ouvre.

4. Dans la [boîte de dialogue Éditeur d’ensemble de règles (hérité)](../workflow-designer/rule-set-editor-dialog-box-legacy.md), cliquez sur **Ajouter une règle** pour ajouter une nouvelle règle à l’ensemble de règles.

5. Entrez le **nom**, la **priorité**et les propriétés de **réévaluation** , ou conservez les valeurs par défaut.

6. Entrez le texte de la **condition**.

7. Entrez le texte des actions **Then** et **else**.

8. Cliquez à nouveau sur **Ajouter une règle** pour ajouter une autre règle.

9. Quand vous avez terminé, cliquez sur **OK**.

## <a name="see-also"></a>Voir aussi
 [PolicyActivity](https://msdn2.microsoft.com/library/system.workflow.activities.policyactivity.aspx) boîte de [dialogue Sélectionner l’ensemble de règles (hérité)](../workflow-designer/select-rule-set-dialog-box-legacy.md) [éditeur d’ensemble de règles, boîte de dialogue (héritée)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) [à l’aide de l’activité de stratégie activités de](https://msdn2.microsoft.com/library/bb675229.aspx) [flux de travail héritées](../workflow-designer/legacy-workflow-activities.md)
