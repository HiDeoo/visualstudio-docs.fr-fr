---
title: Description, élément (modèles Visual Studio) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Description element [Visual Studio project templates]
ms.assetid: 6e12be73-081f-4c7d-898f-027c307a9fe1
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d60244ea827433678afbd09dd1e8cf1c972595cd
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68162114"
---
# <a name="description-element-visual-studio-templates"></a>Description, élément (modèles Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Spécifie la description du modèle telle qu’elle apparaît dans la boîte de dialogue **nouveau projet** ou **Ajouter un nouvel élément** .  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<Description>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Description>  
    Template Description  
</Description>  
```  
  
```  
<Description Package="{PackageID}" ID="ResourceID" />  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|`Package`|Attribut facultatif, pour les scénarios utilisateur avancés.<br /><br /> Un GUID qui spécifie l’ID du package Visual Studio.|  
|`ID`|Attribut facultatif, pour les scénarios utilisateur avancés.<br /><br /> Spécifie l’ID de la ressource Visual Studio.|  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Élément requis.<br /><br /> Définit la catégorie du modèle et comment il s’affiche dans la boîte de dialogue **Nouveau projet** ou **Ajouter un nouvel élément** .|  
  
## <a name="text-value"></a>Valeur texte  
 Une valeur texte est requise, sauf si les attributs `Package` et `ID` sont utilisés.  
  
 Le texte fournit une description du modèle.  
  
## <a name="remarks"></a>Notes  
 `Description` est un élément enfant obligatoire de l' `TemplateData` élément.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre les métadonnées d’un modèle de projet pour une [!INCLUDE[csprcs](../includes/csprcs-md.md)] application.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyStarterKit.csproj">  
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
 [Référence du schéma de modèle Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)
