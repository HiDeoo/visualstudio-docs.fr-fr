---
title: Élément Property (MSBuild) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Property> Element [MSBuild]
- Property Element [MSBuild]
ms.assetid: 69ab08ab-3e76-41dd-a01b-49aa1d2e0cac
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: eefe0160328f1eb6b3fe841742547efe8be50ec1
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68158273"
---
# <a name="property-element-msbuild"></a>Property, élément (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Contient une valeur et un nom de propriété définis par l’utilisateur. Chaque propriété utilisée dans un projet [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] doit être spécifiée en tant qu’enfant d’un élément `PropertyGroup`.  
  
 \<Project>  
 \<PropertyGroup>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Property Condition="'String A' == 'String B'">  
    Property Value  
</Property>  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|`Condition`|Attribut facultatif.<br /><br /> Condition à évaluer. Pour plus d’informations, consultez l’article [Conditions (Conditions MSBuild)](../msbuild/msbuild-conditions.md).|  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|Élément grouping pour des propriétés.|  
  
## <a name="text-value"></a>Valeur texte  
 Une valeur texte est facultative.  
  
 Ce texte spécifie la valeur de propriété et peut contenir du code XML.  
  
## <a name="remarks"></a>Notes  
 Les noms de propriétés sont limités uniquement aux caractères ASCII. Les valeurs de propriété sont référencées dans le projet en plaçant le nom de propriété entre « `$(` » et « `)` ». Par exemple, `$(builddir)\classes` serait résolu en « build\classes » si la propriété `builddir` avait la valeur `build`. Pour plus d’informations sur les propriétés, consultez l’article [Propriétés MSBuild](msbuild-properties1.md).  
  
## <a name="example"></a>Exemple  
 Le code suivant définit la propriété `Optimization` sur `false` et la propriété `DefaultVersion` sur `1.0` si la propriété `Version` est vide.  
  
```  
<PropertyGroup>  
    <Optimization>false</Optimization>  
    <DefaultVersion Condition="'$(Version)' == ''" >1.0</DefaultVersion>  
</PropertyGroup>  
```  
  
## <a name="see-also"></a>Voir aussi
[Propriétés MSBuild](msbuild-properties1.md)  
 [Référence de schéma de fichier de projet](../msbuild/msbuild-project-file-schema-reference.md)
