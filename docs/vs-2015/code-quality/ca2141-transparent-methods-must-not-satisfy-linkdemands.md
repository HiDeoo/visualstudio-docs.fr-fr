---
title: 'CA2141 : les méthodes transparentes ne doivent pas satisfaire les LinkDemands | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2141
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: bee810ed938d316e92095ad47062ed5ad9cd456f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "85546443"
---
# <a name="ca2141transparent-methods-must-not-satisfy-linkdemands"></a>CA2141 : Les méthodes transparentes ne répondent pas aux LinkDemands
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Élément|Valeur|
|-|-|
|TypeName|TransparentMethodsMustNotSatisfyLinkDemands|
|CheckId|CA2141|
|Category|Microsoft.Security|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause :
 Une méthode transparente de sécurité appelle une méthode dans un assembly qui n’est pas marqué avec l' <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribut (APTCA), ou une méthode transparente de sécurité satisfait un <xref:System.Security.Permissions.SecurityAction> `.LinkDemand` pour un type ou une méthode.

## <a name="rule-description"></a>Description de la règle
 La satisfaction d’un LinkDemand est une opération sensible à la sécurité qui peut entraîner une élévation non intentionnelle des privilèges. Le code transparent de sécurité ne doit pas répondre aux LinkDemands, car il n’est pas soumis aux mêmes exigences d’audit de sécurité que le code critique de sécurité. Les méthodes transparentes dans les assemblys du niveau 1 de l’ensemble de règles de sécurité entraînent la conversion de tous les LinkDemands qu’ils satisfont en demandes complètes au moment de l’exécution, ce qui peut entraîner des problèmes de performances. Dans les assemblys de niveau 2 de l’ensemble de règles de sécurité, les méthodes transparentes ne peuvent pas être compilées dans le compilateur juste-à-temps (JIT) si elles essaient de satisfaire un LinkDemand.

 Dans les assemblys qui useent la sécurité de niveau 2, les tentatives effectuées par une méthode transparente de sécurité pour satisfaire un LinkDemand ou appeler une méthode dans un assembly non APTCA lèvent un <xref:System.MethodAccessException> ; dans les assemblys de niveau 1, le LinkDemand devient une demande complète.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, marquez la méthode d’accès avec <xref:System.Security.SecurityCriticalAttribute> l' <xref:System.Security.SecuritySafeCriticalAttribute> attribut ou, ou supprimez le LinkDemand de la méthode accédée.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 Dans cet exemple, une méthode transparente tente d’appeler une méthode qui a un LinkDemand. Cette règle se déclenche sur ce code.

 [!code-csharp[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2141.transparentmethodsmustnotsatisfylinkdemands/cs/ca2141 - transparentmethodsmustnotsatisfylinkdemands.cs#1)]
