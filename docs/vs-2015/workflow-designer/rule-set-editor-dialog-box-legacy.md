---
title: Ensemble de règles éditeur boîte de dialogue (hérité) | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Workflow.Activities.Rules.Design.RuleSetDialog.UI
helpviewer_keywords:
- Rule Set Editor dialog box
ms.assetid: 7cfd5df1-1115-4e5c-9b72-121f39419e83
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 3469e395ee50e63f8ac76e4181d02b777ccbd4ba
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942398"
---
# <a name="rule-set-editor-dialog-box-legacy"></a>Éditeur d'ensemble de règles, boîte de dialogue (héritée)
Cette rubrique décrit comment utiliser le **Éditeur d’ensemble de règles** boîte de dialogue dans les anciennes [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Utilisez le [!INCLUDE[wfd2](../includes/wfd2-md.md)] hérité lorsque vous devez cibler le [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] ou le [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 Le **Éditeur d’ensemble de règles** boîte de dialogue est utilisée pour créer et modifier [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019) sérialisés dans un fichier .rules ensembles de règles.  
  
> [!NOTE]
>  Si vous souhaitez ouvrir le fichier .rules avec le **XML-éditeur avec encodage**, vous devez d’abord fermer la fenêtre du concepteur associée pour l’activité ou le flux de travail.  
  
 Pour plus d’informations sur l’accès à la **Éditeur d’ensemble de règles** boîte de dialogue, consultez [Comment : créer un ensemble de le règles PolicyActivity (hérité)](../workflow-designer/how-to-create-a-policyactivity-rule-set-legacy.md).  
  
> [!WARNING]
>  L'éditeur de règles du [!INCLUDE[wfd2](../includes/wfd2-md.md)] hérité utilisé pour cibler le [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] ou le [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] ne prend pas en charge le multi-ciblage.  
  
 Le tableau suivant décrit les éléments d’interface utilisateur utilisateur de la **Éditeur d’ensemble de règles** boîte de dialogue.  
  
|Élément d'interface utilisateur|Description|  
|----------------|-----------------|  
|**Ajouter une règle**|Ajoute une nouvelle définition de règle à l'ensemble de règles.|  
|**Supprimer**|Supprime la règle sélectionnée de l'ensemble de règles.|  
|**Le chaînage**|Spécifie le type de chaînage avant à utiliser avec l'ensemble de règles. Les options disponibles sont les suivantes :<br /><br /> -   **Chaînage complet**, qui spécifie l’utilisation des mécanismes de chaînage avant tout : implicite, attribution de méthode et explicite avec un **mise à jour** (fonction).<br />-   **Séquentiel**, qui spécifie de ne pas utiliser de chaînage avant.<br />-   **Mise à jour explicite uniquement**, qui spécifie d’exécuter uniquement le chaînage avant sur **mise à jour** actions.<br /><br /> Pour plus d’informations sur le chaînage avant, consultez [à l’aide de l’activité PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004).|  
|**Name**|En-tête de colonne de la liste des ensembles de règles. Cliquez pour trier la liste de règles par nom.|  
|**Priorité**|En-tête de colonne de la liste des ensembles de règles. Cliquez pour trier la liste de règles par priorité.|  
|**Réévaluation**|En-tête de colonne de la liste des ensembles de règles. Cliquez pour trier la liste de règles par type de réévaluation.|  
|**Aperçu de la règle**|En-tête de colonne de la liste des ensembles de règles. Cliquez pour trier la liste de règles par l'aperçu de la condition d'une règle et actions.|  
|**Nom :**|Entrez le nom de la règle.|  
|**Priorité :**|Entrez une priorité pour la règle. La priorité par défaut est 0.|  
|**Réévaluation :**|Spécifie le type de réévaluation de règle à utiliser avec la règle. Les options disponibles sont les suivantes :<br /><br /> -   **Toujours**, ce qui entraîne la règle être réévaluée en fonction des besoins.<br />-   **Jamais**, ce qui entraîne la règle doit jamais être réévaluée. Dans ce cas, la règle est exécutée une seule fois.|  
|**Active**|Cochez pour rendre la règle active.|  
|**Condition :**|Entrez une expression pour la condition de règle. Pour plus d'informations sur la syntaxe d'expression, consultez la section consacrée à l'entrée de conditions et d'expressions d'actions dans cette page.|  
|**Actions Then :**|Entrez une expression applicable aux actions THEN. Pour plus d'informations sur la syntaxe d'expression, consultez la section consacrée à l'entrée de conditions et d'expressions d'actions dans cette page.|  
|**Actions Else :**|Entrez une expression applicable aux actions ELSE. Pour plus d'informations sur la syntaxe d'expression, consultez la section consacrée à l'entrée de conditions et d'expressions d'actions dans cette page.|  
|**OK**|Cliquez pour enregistrer l'ensemble de règles dans un fichier .rules.|  
  
 Pour plus d’informations sur les ensembles de règles, consultez [à l’aide de l’activité PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004).  
  
## <a name="entering-condition-and-action-expressions"></a>Entrée de conditions et d'expressions d'actions  
 Vous entrez des expressions pour la Condition, le puis et d’autre actions sous forme de texte dans leur texte respective boîtes de la **Éditeur d’ensemble de règles** boîte de dialogue. Vous pouvez taper **cela.** dans l’éditeur pour référencer des champs, propriétés et méthodes utilisées dans le flux de travail, à l’aide un type de menu IntelliSense. Vous pouvez également taper directement un nom de membre de workflow. Vous pouvez appeler des méthodes statiques appartenant aux types référencés ; pour cela, tapez le nom de la classe suivi du nom de la méthode.  
  
 Vous pouvez ajouter des opérateurs logiques à la condition, tels que les opérateurs AND, OR ou NOT. Vous pouvez également ajouter des prédicats. Un prédicat se compose d’un opérateur binaire et de deux opérandes. Les opérateurs binaires pris en charge sont ==, >, \<, > =, et < =. Les opérandes pris en charge sont à valeur de constante, à fonction arithmétique et à portée publique.  
  
 Vous pouvez spécifier le type de comparaison, et vous pouvez comparer aux **null** ou une chaîne vide. Vous pouvez imbriquer des appels à des membres sur une variable qui contient un type complexe, par exemple `this.Address.State == "WA"`.  
  
 Les expressions prennent en charge les opérateurs suivants :  
  
- Opérateurs relationnels: ==, =, !=  
  
- Opérateurs de comparaison : <, \<=, >, > =  
  
- Opérateurs arithmétiques: +, - , *, /, MOD  
  
- Opérateurs logiques : et, & &, OR, &#124; &#124;, NOT, !  
  
- Opérateurs au niveau du bit : &,&#124;  
  
  La priorité des opérateurs d'expression suit les règles de priorité des opérateurs C#.  
  
  Pour plus d’informations sur les conditions, consultez [à l’aide de Conditions dans les Workflows](http://msdn.microsoft.com/en-us/541211f5-d382-4810-894f-71f00b34fa77).  
  
### <a name="halt-and-update-functions"></a>Fonctions d'arrêt et de mise à jour  
 **Actions Then :** et **Actions Else :** expressions prennent en charge **Halt** et **mise à jour** fonctions. À utiliser le **Halt** de fonction, tapez **Halt** dans un **puis Action :** ou **Action Else :** zone de texte. Le **Halt** entraîne l’exécution de jeu de règles arrêter immédiatement, et le contrôle retourne au code appelant. Vous utilisez le **mise à jour** fonction avec le chaînage avant.  
  
 Un **mise à jour** instruction peut être exprimée dans l’éditeur de l’une des deux formes ; les deux formulaires sont illustrés dans l’exemple suivant :  
  
```  
Update(this.Address.State)  
Update("this/Address/State")  
```  
  
 Pour plus d’informations sur l’utilisation de **mise à jour** avec le chaînage avant, consultez [à l’aide de l’activité PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004).  
  
## <a name="see-also"></a>Voir aussi  
 [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)   
 [Sélectionnez la règle ensemble, boîte de dialogue (hérité)](../workflow-designer/select-rule-set-dialog-box-legacy.md)   
 [À l’aide de l’activité PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004)   
 [Utilisation de Conditions dans les Workflows](http://go.microsoft.com/fwlink?LinkID=65009)