---
title: Erreurs d’application d’analyse du code
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
helpviewer_keywords:
- errors [Visual Studio ALM], code analysis
- code analysis, errors
- managed code, code analysis errors
- code analysis, policy errors
ms.assetid: d8fd9475-ac9b-4085-b5a3-b0c807922cac
caps.latest.revision: 25
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: ef5ccc0cf432a5c6782b76c4623bfdc55f66a8b5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85538553"
---
# <a name="code-analysis-application-errors"></a>Erreurs d’application d’analyse du code
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
Cette section est une référence des messages d’erreur générés par l’outil d’analyse du code managé. Pour obtenir de l’aide pour un message d’erreur spécifique, tapez le numéro d’erreur dans la zone **Rechercher** de l’index.

## <a name="in-this-section"></a>Dans cette section

|Élément|Valeur|
|-|-|
|[CA0001](ca0001.md)|Une exception a été levée dans l’outil d’analyse du code managé qui n’indique pas une condition d’erreur attendue.|
|[CA0051](ca0051.md)|Aucune règle n’a été sélectionnée.|
|[CA0052](ca0052.md)|Aucune cible n’a été sélectionnée pour l’analyse.|
|[CA0053](ca0053.md)|Impossible de charger l’assembly de règle.|
|[CA0054](ca0054.md)|Un assembly de règle personnalisé a des ressources XML non valides.|
|[CA0055](ca0055.md)|Impossible de charger le fichier :\<path>|
|[CA0056](ca0056.md)|Un fichier projet a une version incorrecte de l’outil d’analyse.|
|[CA0057](ca0057.md)|Les violations ne peuvent pas être mappées à l’ensemble actuel de cibles et de règles.|
|[CA0058](ca0058.md)|Impossible de charger les assemblys référencés.|
|[CA0059](ca0059.md)|Erreur de commutateur de ligne de commande.|
|[CA0060](ca0060.md)|Impossible de charger les assemblys référencés indirectement.|
|[CA0061](ca0061.md)|La règle «*RuleId*» est introuvable.|
|[CA0062](ca0062.md)|La règle «*RuleId*» référencée dans l’ensemble de règles «*RuleSetName*» est introuvable.|
|[CA0063](ca0063.md)|Échec du chargement du fichier d’ensemble de règles ou de l’un de ses fichiers d’ensemble de règles dépendants.|
|[CA0064](ca0064.md)|Aucune analyse n’a été effectuée, car l’ensemble de règles spécifié ne contenait aucune règle FxCop.|
|[CA0065](ca0065.md)|Construction de métadonnées non prise en charge : le type'*TypeName*'contient à la fois une propriété et un champ portant le même nom'*PropertyFieldName*'|
|[CA0066](ca0066.md)|La valeur «*VersionId*» fournie à **/TargetFrameworkVersion n'** n’est pas une version reconnue.|
|[CA0067](ca0067.md)|Répertoire introuvable.|
|[CA0068](ca0068.md)|Les informations de débogage sont introuvables pour l’assembly cible *'AssemblyName'*.|
|[CA0069](ca0069.md)|Utilisation d’une autre plateforme. *FrameworkVersion1* est introuvable. Utilisation de *FrameworkVersion2* à la place. Pour obtenir les meilleurs résultats d’analyse, vérifiez que la .NET Framework correcte est installée.|
|[CA0070](ca0070.md)|Impossible de charger l’assembly ou le type en raison des autorisations de sécurité.|
|[CA0501](ca0501.md)|Impossible de lire le rapport de sortie.|
|[CA0502](ca0502.md)|Langage non pris en charge.|
|[CA0503](ca0503.md)|La propriété est déconseillée. Utiliser la propriété de remplacement|
|[CA0504](ca0504.md)|Le répertoire de la règle a été ignoré, car il n’existe pas|
|[CA0505](ca0505.md)|La propriété est déconseillée. Utiliser la propriété de remplacement|
|[Erreurs FxCopCmd](fxcopcmd-errors.md)|Erreurs d’analyse du code managé.|

## <a name="related-sections"></a>Sections connexes

- [Instructions pour l’écriture de code sécurisé](https://msdn.microsoft.com/9892fd19-45cd-44b6-9fa8-10f1b5cb6ea4)
- [Analyse de la qualité d’un code managé](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)
- [Ressources pour le dépannage des erreurs dans les outils de gestion du cycle de vie des applications](https://msdn.microsoft.com/library/76ca8f76-1e2d-4b55-89e2-bd59e4abe74c)