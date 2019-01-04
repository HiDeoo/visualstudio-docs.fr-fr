---
title: 'CA1725 : Les noms de paramètre doivent correspondre à la déclaration de base'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- ParameterNamesShouldMatchBaseDeclaration
- CA1725
helpviewer_keywords:
- CA1725
- ParameterNamesShouldMatchBaseDeclaration
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9135ab768d3439cc996478da31343553902706fa
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53860598"
---
# <a name="ca1725-parameter-names-should-match-base-declaration"></a>CA1725 : Les noms de paramètre doivent correspondre à la déclaration de base

|||
|-|-|
|TypeName|ParameterNamesShouldMatchBaseDeclaration|
|CheckId|CA1725|
|Category|Microsoft.Naming|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Le nom d’un paramètre dans une substitution de méthode visible de l’extérieur ne correspond pas au nom du paramètre dans la déclaration de base de la méthode ou le nom du paramètre dans la déclaration d’interface de la méthode.

## <a name="rule-description"></a>Description de la règle
 La désignation cohérente des paramètres dans une hiérarchie de substitution augmente la facilité d'utilisation des substitutions de méthode. Un nom de paramètre dans une méthode dérivée qui diffère du nom dans la déclaration de base peut créer une confusion pour déterminer si la méthode est une substitution de la méthode de base ou une nouvelle surcharge de la méthode.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, renommez le paramètre pour correspondre à la déclaration de base. Le correctif est une modification avec rupture pour les méthodes visibles par COM.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez pas un avertissement de cette règle à l’exception des méthodes visibles par COM dans les bibliothèques fournies antérieurement.