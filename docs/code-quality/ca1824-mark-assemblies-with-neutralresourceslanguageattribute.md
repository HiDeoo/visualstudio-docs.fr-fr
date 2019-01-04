---
title: 'CA1824 : Marquer les assemblys avec NeutralResourcesLanguageAttribute'
ms.date: 03/29/2018
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: db780257c83c42f97500a83f1843332cae0ecea3
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53825174"
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824 : Marquer les assemblys avec NeutralResourcesLanguageAttribute

|||
|-|-|
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|
|CheckId|CA1824|
|Category|Microsoft.Performance|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause

Un assembly contient un **ResX**-en fonction des ressources, mais n’a pas le <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> appliqué.

## <a name="rule-description"></a>Description de la règle

Le <xref:System.Resources.NeutralResourcesLanguageAttribute> attribut informe le Gestionnaire de ressources de culture par défaut de l’application. Si les ressources de la culture par défaut sont incorporés dans l’assembly principal de l’application, et <xref:System.Resources.ResourceManager> a récupérer des ressources qui appartiennent à la même culture que la culture par défaut, le <xref:System.Resources.ResourceManager> utilise automatiquement les ressources situées dans l’assembly principal au lieu de rechercher un assembly satellite. Cela contourne la sonde de l’assembly habituel, améliore les performances de recherche pour la première ressource que vous chargez et réduisez votre jeu de travail.

> [!TIP]
> Consultez [empaquetage et déploiement de ressources](/dotnet/framework/resources/packaging-and-deploying-resources-in-desktop-apps) pour le processus qui <xref:System.Resources.ResourceManager> utilise pour détecter les fichiers de ressources.

## <a name="fix-violations"></a>Corriger les violations

Pour corriger une violation de cette règle, ajoutez l’attribut à l’assembly et spécifier la langue des ressources de la culture neutre.

### <a name="to-specify-the-neutral-language-for-resources"></a>Pour spécifier la langue neutre pour les ressources

1. Dans **l’Explorateur de solutions**, cliquez sur votre projet, puis sélectionnez **propriétés**.

2. Sélectionnez le **Application** onglet, puis sélectionnez **informations de l’Assembly**.

   > [!NOTE]
   > Si votre projet est un projet .NET Standard ou .NET Core, sélectionnez le **Package** onglet.

3. Sélectionnez la langue à partir de la **langue neutre** ou **langue neutre Assembly** liste déroulante.

4. Sélectionnez **OK**.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements

Il est permis de supprimer un avertissement de cette règle. Toutefois, peut dégrader les performances de démarrage.

## <a name="see-also"></a>Voir aussi

- <xref:System.Resources.NeutralResourcesLanguageAttribute>
- [Ressources dans les applications de bureau (.NET)](/dotnet/framework/resources/)
- [CA1703 - chaînes de ressources doivent être correcte](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1701 - chaîne de ressource des mots composés doivent être correcte](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)