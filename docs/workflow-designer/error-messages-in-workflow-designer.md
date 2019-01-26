---
title: Messages d'erreur dans Workflow Designer
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- WFDErrorMessages.UI
- System.Activities.Presentation.ErrorActivity.UI
- System.Activities.Presentation.View.ErrorView.UI
ms.assetid: 4d8bbc2e-34fc-477f-9140-4adfd70c34a0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a9d5604994476c4f87305d1a9495944809eb8b5f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54998610"
---
# <a name="error-messages-in-workflow-designer"></a>Messages d'erreur dans Workflow Designer

Cette rubrique décrit les types de messages d’erreur qui peuvent être rencontrés lorsque vous travaillez avec le Concepteur de flux de travail.

## <a name="situations-in-which-errors-in-the-workflow-designer-occur"></a>Situations dans lesquelles des erreurs se produisent dans Workflow Designer

Erreurs dans le Concepteur de flux de travail se produisent dans les situations suivantes :

1.  Il existe une erreur dans une expression.

2.  Les contraintes de validation d'une activité n'ont pas été satisfaites.

3.  Le fichier XAML contient des erreurs qui provoquent l'échec du chargement d'une activité.

4.  Le fichier XAML contient des erreurs qui provoquent l'échec du chargement du workflow.

Des expressions non valides et des contraintes de validation non satisfaites n'entraînent pas l'échec de la génération du workflow. La génération de votre workflow réussit, mais une exception <xref:System.Activities.InvalidWorkflowException> est levée pendant l'exécution. Si le fichier XAML contient des erreurs, la génération échoue.

À l’intérieur de Visual Studio, lorsqu’un workflow est chargé, ses erreurs sont affichées dans le **liste d’erreurs**. Pour accéder à l’activité qui est la source de l’erreur, double-cliquez sur l’erreur dans le **liste d’erreurs**.

### <a name="expression-errors"></a>Erreurs d'expression
 Une expression non valide est signalée par un point d'exclamation blanc dans un cercle rouge en regard de l'expression. Le déplacement de la souris au-dessus de cette icône affiche une info-bulle qui décrit la source de l'erreur. À l’intérieur de Visual Studio, cliquez sur l’expression pour afficher la ligne qui souligne la source de l’erreur. Le déplacement de la souris au-dessus du texte souligné affiche une info-bulle qui décrit la source de l'erreur.

### <a name="activity-validation-errors"></a>Erreurs de validation d'activité
 Lorsque les contraintes de validation d'une activité n'ont pas été satisfaites, un point d'exclamation blanc dans un cercle rouge s'affiche dans l'angle supérieur droit de l'activité. Le déplacement de la souris au-dessus de cette icône affiche une info-bulle qui décrit la source de l'erreur.

### <a name="xaml-load-errors"></a>Erreurs de chargement XAML
 Lorsqu’une activité ne parvient pas à charger, une zone rouge avec le texte « Impossible de charger l’activité en raison d’erreurs dans le XAML » s’affiche. Cela se produit généralement lorsque le type de l’activité ne peut pas être résolu. L'activité non valide peut être supprimée dans le concepteur en sélectionnant la zone rouge et en la supprimant.

### <a name="workflow-load-errors"></a>Erreurs de chargement du workflow
 Lorsque le chargement d’un flux de travail échoue, le texte « Workflow Designer a rencontré des problèmes avec votre document » s’affiche sur l’aire du concepteur, ainsi que des informations sur l’exception qui a provoqué l’échec du chargement du flux de travail. Cela se produit généralement lorsque le fichier XAML ne peut pas être analysé.