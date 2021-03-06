---
title: CreateInPlace (modèles Visual Studio) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#CreateInPlace
helpviewer_keywords:
- CreateInPlace element [Visual Studio Templates]
- <CreateInPlace> element [Visual Studio Templates]
ms.assetid: 420d46ea-2470-4da9-ad8e-95165588a920
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d722aebef0cbcf589185c36cb481a676280d59ff
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68184238"
---
# <a name="createinplace-visual-studio-templates"></a>CreateInPlace (modèles Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Spécifie s’il faut créer le projet et effectuer le remplacement des paramètres à l’emplacement spécifié, ou effectuer le remplacement des paramètres dans un emplacement temporaire, puis enregistrer le projet à l’emplacement spécifié.  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<CreateInPlace>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<CreateInPlace> true/false </CreateInPlace>  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
 Aucun.  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Définit la catégorie du modèle et comment il s’affiche dans la boîte de dialogue **Nouveau projet** ou **Ajouter un nouvel élément** .|  
  
## <a name="text-value"></a>Valeur texte  
 Une valeur texte est requise.  
  
 Le texte doit être `true` ou `false`. Si `true` , le projet est créé et le remplacement de paramètre est effectué à l’emplacement spécifié dans la boîte de dialogue **nouveau projet** . Si `false` la valeur est, le remplacement des paramètres est effectué dans un emplacement temporaire et le projet est ensuite copié à l’emplacement spécifié.  
  
## <a name="remarks"></a>Notes  
 `CreateInPlace` est un élément facultatif. La valeur par défaut est `true`.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant illustre les métadonnées d'un modèle [!INCLUDE[csprcs](../includes/csprcs-md.md)].  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <CreateInPlace>false</CreateInPlace>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)   
 [Référence du schéma de modèle Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
