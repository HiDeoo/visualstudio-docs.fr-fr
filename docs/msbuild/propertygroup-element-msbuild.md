---
title: Élément PropertyGroup (MSBuild) | Microsoft Docs
ms.date: 03/13/2017
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#PropertyGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <PropertyGroup> element [MSBuild]
- PropertyGroup element [MSBuild]
ms.assetid: ff1e6c68-b9a1-4263-a1ce-dc3b829a64d4
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f7497578b977b66c83a8b5f9f37f03743f864bcd
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75597371"
---
# <a name="propertygroup-element-msbuild"></a>Élément PropertyGroup (MSBuild)
Contient un ensemble d’éléments [Property](../msbuild/property-element-msbuild.md) définis par l’utilisateur. Chaque élément `Property` utilisé dans un projet [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] doit être un enfant d’un élément `PropertyGroup`.

 \<Project> \<PropertyGroup>

## <a name="syntax"></a>Syntaxe

```xml
<PropertyGroup Condition="'String A' == 'String B'">
    <Property1>...</Property1>
    <Property2>...</Property2>
</PropertyGroup>
```

## <a name="attributes-and-elements"></a>Attributs et éléments
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.

### <a name="attributes"></a>Attributs

|Attribute|Description|
|---------------|-----------------|
|Condition|Attribut facultatif.<br /><br /> Condition à évaluer. Pour plus d’informations, consultez l’article [Conditions (Conditions MSBuild)](../msbuild/msbuild-conditions.md).|

### <a name="child-elements"></a>Éléments enfants

|Élément|Description|
|-------------|-----------------|
|[Property](../msbuild/property-element-msbuild.md)|Élément facultatif.<br /><br /> Nom de propriété défini par l’utilisateur, qui contient la valeur de propriété. Un élément `PropertyGroup` peut ne contenir aucun élément *Property* ou en contenir plusieurs.|

### <a name="parent-elements"></a>Éléments parents

| Élément | Description |
| - | - |
| [Project](../msbuild/project-element-msbuild.md) | Élément racine requis d'un fichier projet [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] . |

## <a name="example"></a>Exemple
 L’exemple de code suivant montre comment définir des propriétés en fonction d’une condition. Dans cet exemple, si la valeur de la propriété `CompileConfig` est `DEBUG`, les propriétés `Optimization`, `Obfuscate` et `OutputPath` contenues dans l’élément `PropertyGroup` sont définies.

```xml
<PropertyGroup Condition="'$(CompileConfig)' == 'DEBUG'" >
    <Optimization>false</Optimization>
    <Obfuscate>false</Obfuscate>
    <OutputPath>$(OutputPath)\debug</OutputPath>
</PropertyGroup>
```

## <a name="see-also"></a>Voir aussi
- [Informations de référence sur le schéma de fichier projet](../msbuild/msbuild-project-file-schema-reference.md)
- [Propriétés MSBuild](../msbuild/msbuild-properties.md)
