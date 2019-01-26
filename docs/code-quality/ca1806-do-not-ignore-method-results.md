---
title: "CA1806 : N'ignorez pas les résultats des méthodes"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1806
- DoNotIgnoreMethodResults
helpviewer_keywords:
- CA1806
- DoNotIgnoreMethodResults
ms.assetid: fd805687-0817-481e-804e-b62cfb3b1076
author: gewarren
ms.author: gewarren
dev_langs:
- CPP
- CSharp
- VB
manager: jillfra
ms.openlocfilehash: 4ac122534a42cb78b80d1a12004a8db3d1b5b203
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55043633"
---
# <a name="ca1806-do-not-ignore-method-results"></a>CA1806 : N'ignorez pas les résultats des méthodes

|||
|-|-|
|TypeName|DoNotIgnoreMethodResults|
|CheckId|CA1806|
|Category|Microsoft.Usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause

Il existe plusieurs raisons possibles à cet avertissement :

- Un nouvel objet est créé mais jamais utilisé.

- Une méthode qui crée et retourne une nouvelle chaîne est appelée et la nouvelle chaîne n’est jamais utilisée.

- Une méthode COM ou P/Invoke qui retourne un HRESULT ou code d’erreur qui n’est jamais utilisée. Description de la règle

Création d’un objet inutile et le garbage collection associé de l’objet inutilisé dégrader les performances.

Les chaînes sont immuables et les méthodes telles que String.ToUpper retourne une nouvelle instance d’une chaîne au lieu de modifier l’instance de la chaîne dans la méthode d’appel.

Ignorer les HRESULT ou code d’erreur peut entraîner un comportement inattendu dans les conditions d’erreur ou à des conditions de ressources insuffisantes.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Si la méthode A crée une nouvelle instance de l’objet B qui n’est jamais utilisée, passez l’instance comme argument à une autre méthode ou assignez l’instance à une variable. Si la création de l’objet n’est pas nécessaire, supprimez-la.- ou -

 Si la méthode A appelle la méthode B, mais n’utilise pas la nouvelle instance de chaîne retournée par la méthode B. Passez l’instance comme argument à une autre méthode, assignez l’instance à une variable. Ou supprimez l’appel s’il n’est pas nécessaire.

 ou

 Si la méthode A appelle la méthode B, mais n’utilise pas le HRESULT ou code d’erreur que la méthode retourne. Utiliser le résultat dans une instruction conditionnelle, assignez le résultat à une variable ou passez-le en tant qu’argument à une autre méthode.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez pas un avertissement de cette règle, sauf si l’opération de création de l’objet sert un but quelconque.

## <a name="example"></a>Exemple
 L’exemple suivant montre une classe qui ignore le résultat de l’appel de String.Trim.

 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_1.cs)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_1.vb)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_1.cpp)]

## <a name="example"></a>Exemple
 L’exemple suivant résout la violation précédente en assignant le résultat de String.Trim à la variable que qui l’a appelé.

 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_2.cs)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_2.vb)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_2.cpp)]

## <a name="example"></a>Exemple
 L’exemple suivant montre une méthode qui n’utilise pas un objet qu’il crée.

> [!NOTE]
> Cette violation ne peut pas être reproduite dans Visual Basic.

 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_3.cpp)]
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_3.cs)]

## <a name="example"></a>Exemple
 L’exemple suivant résout la violation précédente en supprimant la création inutile d’un objet.

 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_4.cs)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_4.cpp)]

<!-- Examples don't exist for the below... -->
<!--
## Example
 The following example shows a method that ignores the error code that the native method GetShortPathName returns.

## Example
 The following example fixes the previous violation by checking the error code and throwing an exception when the call fails.
-->