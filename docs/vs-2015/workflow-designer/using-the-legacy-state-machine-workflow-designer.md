---
title: Utilisation de l’ordinateur d’État hérité Concepteur de flux de travail | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- StateFinalizationActivity activity
- StateActivity activity
- SetStateActivity activity
- EventDrivenActivity activity
- state machine workflow designer
- state machine workflows, designer
- state machine workflows, activities
- StateInitializationActivity activity
ms.assetid: 2cd21123-35c2-4eaf-82f6-86fce7a8f04d
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 77bb2c7abb49dbf6fe973ebc80f8340000e4afbd
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75846007"
---
# <a name="using-the-legacy-state-machine-workflow-designer"></a>Utilisation du Concepteur de Workflow d'ordinateur d'état hérité
Lorsque vous créez un nouveau projet de workflow d’ordinateur d’État dans [!INCLUDE[vs2010](../includes/vs2010-md.md)] qui cible le [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] ou le [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] , vous pouvez choisir d’utiliser l' **application console de workflow** de l’ordinateur d’État ou le modèle de projet hérité de la bibliothèque de **workflows** de l’ordinateur d’État. Si vous choisissez l'un de ces modèles de projet d'ordinateur d'état, le concepteur d'ordinateurs d'état est présenté comme interface utilisateur de concepteur de workflow hérité. Pour plus d’informations sur les modèles de projet d’ordinateur d’État hérités, consultez [Comment : créer des applications console de workflow d’ordinateur d’État (hérité)](../workflow-designer/how-to-create-state-machine-workflow-console-applications-legacy.md) et [Comment : créer une bibliothèque de workflows d’ordinateur d’État (héritée)](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md).

 Un workflow d'ordinateur d'état se compose d'un ensemble d'états. Un état représente un état initial. Chaque état peut recevoir certains événements spécifiques. En fonction d'un événement, une transition peut s'effectuer vers un autre état. Le workflow d'ordinateur d'état peut porter un état final. Lorsqu'une transition est effectuée vers l'état final, l'exécution de workflow prend fin.

## <a name="state-machine-designer-views"></a>Vues du concepteur de workflow de l'ordinateur d'état
 Le concepteur de l'ordinateur d'état est un concepteur de formes libres, ce qui signifie que les activités peuvent être déplacées librement sur l'aire de conception. Le concepteur de l’ordinateur d’État comporte deux vues : affichage des *États* et vue *pilotée par les événements* .

 La vue d'état affiche les activités d'état et les activités pilotées par événements qui peuvent être contenues dans une activité d'état. Dans cette vue, les transitions d'un état à un autre sont représentées par des lignes qui relient l'activité pilotée par événements portant un état spécifique et l'activité portant un autre état. Vous pouvez également créer des transitions en dessinant vous-même cette ligne. Pour dessiner la transition, sélectionnez l'activité pilotée par événements, puis sélectionnez l'une des poignées de l'activité et faites-la glisser. Cette action permet de dessiner une ligne. Cette ligne est ensuite reliée à l'état cible, indiquant une transition entre les états.

 Pour accéder à la vue des activités pilotées par événements, double-cliquez sur une activité pilotée par événements. Le concepteur qui apparaît s'apparente au concepteur de workflow séquentiel. Dans sa partie supérieure, une barre de navigation affiche la hiérarchie des activités jusqu'à l'activité pilotée par événements. Vous pouvez naviguer jusqu'à la vue d'état en cliquant sur un élément de la hiérarchie affichée. Si vous avez dessiné une transition d'un état vers un autre état dans la vue d'état, et si vous affichez la vue de l'activité pilotée par événements, une activité d'état définie est ajoutée à l'activité pilotée par événements. Si vous modifiez les propriétés de l'activité d'état définie, ces modifications sont répercutées dans la vue d'état.

## <a name="state-machine-workflow-activities"></a>Activités de workflow de l'ordinateur d'état
 Le tableau suivant décrit les activités clés utilisées dans un concepteur de workflow d'ordinateur d'état.

|Nom de boîte à outils|Activité|Description|
|------------------|--------------|-----------------|
|**State**|[StateActivity](https://msdn2.microsoft.com/library/system.workflow.activities.stateactivity.aspx)|Représente un État dans une machine à États. peut contenir des activités **StateActivity** supplémentaires. Pour plus d’informations, consultez [utilisation de l’activité StateActivity](https://msdn2.microsoft.com/library/bb628612.aspx).|
|**SetState**|[SetStateActivity](https://msdn2.microsoft.com/library/system.workflow.activities.setstateactivity.aspx)|Spécifie une transition vers un nouvel état. Pour plus d’informations, consultez [utilisation de l’activité SetStateActivity](https://msdn2.microsoft.com/library/bb628469.aspx).|
|**StateInitialization**|[StateInitializationActivity](https://msdn2.microsoft.com/library/system.workflow.activities.stateinitializationactivity.aspx)|Elle est exécutée lorsqu'un état est entré ; elle peut contenir d'autres activités. Pour plus d’informations, consultez [utilisation de l’activité StateInitialization](https://msdn2.microsoft.com/library/bb675253.aspx).|
|**StateFinalization**|[StateFinalizationActivity](https://msdn2.microsoft.com/library/system.workflow.activities.statefinalizationactivity.aspx)|Exécute les activités contenues lors de la sortie d’une activité [StateActivity](https://msdn2.microsoft.com/library/system.workflow.activities.stateactivity.aspx) . Pour plus d’informations, consultez [utilisation de l’activité StateFinalizationActivity](https://msdn2.microsoft.com/library/bb675278.aspx).|
|**EventDriven**|[EventDrivenActivity](https://msdn2.microsoft.com/library/system.workflow.activities.eventdrivenactivity.aspx)|Utilisée pour des états pour lesquels un événement externe déclenche l'exécution. L’activité **EventDrivenActivity** doit avoir une activité qui implémente l’interface [IEventActivity](https://msdn2.microsoft.com/library/system.workflow.activities.ieventactivity.aspx) en tant que première activité enfant. Pour plus d’informations, consultez [utilisation de l’activité EventDrivenActivity](https://msdn2.microsoft.com/library/bb628466.aspx).|

 Le composant principal d’un workflow d’ordinateur d’État est l’activité [StateActivity](https://msdn2.microsoft.com/library/system.workflow.activities.stateactivity.aspx) . Puisque les événements sont capturés à différents points d'un workflow d'ordinateur d'état, des états différents sont entrés pour gérer les tâches associées aux événements. Pendant la durée de vie du workflow, ce dernier peut porter plusieurs états différents. Ces États se connectent l’un à l’autre à l’aide de l’activité [SetStateActivity](https://msdn2.microsoft.com/library/system.workflow.activities.setstateactivity.aspx) .

 Quand vous faites glisser un **nouveau StateActivity** sur l’aire de conception de workflow, vous [pouvez ajouter des](https://msdn2.microsoft.com/library/system.workflow.activities.eventdrivenactivity.aspx)activités **StateActivity** , [StateInitializationActivity](https://msdn2.microsoft.com/library/system.workflow.activities.stateinitializationactivity.aspx), [StateFinalizationActivity](https://msdn2.microsoft.com/library/system.workflow.activities.statefinalizationactivity.aspx)ou supplémentaires en tant qu’activités enfants.

> [!CAUTION]
> Lorsque vous utilisez le concepteur de workflow d’ordinateur d’État pour créer des flux de travail, vous devez surveiller la structure du flux de travail que vous concevez à l’aide de la fenêtre **structure du document** . La vue de la structure du flux de travail de l’ordinateur d’État dans la fenêtre structure du **document** reflète la disposition logique des activités dans le fichier de balisage du Workflow. La disposition physique des activités de workflow, telles qu'elles apparaissent dans l'aire de conception, peut ne pas refléter la disposition logique des activités dans le fichier de balisage du workflow.
>
> Pour ouvrir la **fenêtre structure du document** , dans le menu **affichage** , pointez sur **autres fenêtres**, puis sélectionnez **structure du document**.

## <a name="see-also"></a>Voir aussi
 [Comment : créer des applications console de workflow d’ordinateur d’État (hérité)](../workflow-designer/how-to-create-state-machine-workflow-console-applications-legacy.md) Comment : créer des [flux de travail d’ordinateur d’État](https://msdn2.microsoft.com/library/bb628601.aspx) de [bibliothèque de workflows d’ordinateur d’État (hérité)](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md) [à l’aide de l’activité StateActivity](https://msdn2.microsoft.com/library/bb628612.aspx) [à](https://msdn2.microsoft.com/library/bb675253.aspx) l’aide de l’activité StateInitializationActivity à l’aide de l’activité [StateFinalizationActivity](https://msdn2.microsoft.com/library/bb675278.aspx) [à](https://msdn2.microsoft.com/library/bb628469.aspx) l’aide de l’activité SetStateActivity [à l’aide de l’activité EventDrivenActivity](https://msdn2.microsoft.com/library/bb628466.aspx)
