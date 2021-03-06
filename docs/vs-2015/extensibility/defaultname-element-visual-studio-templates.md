---
title: Élément DefaultName (modèles Visual Studio) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#DefaultName
helpviewer_keywords:
- DefaultName element [Visual Studio project templates]
ms.assetid: 0ff056c8-b9d2-4747-9308-92adf1811491
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0bc3a18c47b78a312f3bca3762cc4ff3d658a70e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68185288"
---
# <a name="defaultname-element-visual-studio-templates"></a>DefaultName, élément (modèles Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Spécifie le nom que le système de projet Visual Studio va générer pour le projet ou l’élément lors de sa création.  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<DefaultName>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<DefaultName>  
    Default Project Name  
</DefaultName>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Élément requis.<br /><br /> Définit la catégorie du modèle et comment il s’affiche dans la boîte de dialogue **Nouveau projet** ou **Ajouter un nouvel élément** .|  
  
## <a name="text-value"></a>Valeur texte  
 Une valeur texte est requise.  
  
 Ce texte spécifie le nom par défaut du projet ou de l’élément.  
  
## <a name="remarks"></a>Notes  
 `DefaultName` est un élément facultatif.  
  
 Pour les projets, cet élément spécifie le nom du répertoire qui stocke le projet sur le disque. Pour les éléments, il spécifie le nom de fichier du fichier source.  
  
 Lorsque vous créez un projet ou un élément, vous pouvez modifier le nom par défaut à l’aide de l’option **nom** , disponible dans la boîte de dialogue **nouveau projet** ou **Ajouter un nouvel élément** .  
  
 Si vous ne souhaitez pas que le système de projet génère le nom par défaut du projet ou de l’élément, définissez l’élément [ProvideDefaultName](../extensibility/providedefaultname-element-visual-studio-templates.md) sur `False` .  
  
## <a name="example"></a>Exemple  
 L’exemple suivant illustre les métadonnées pour le modèle d’élément standard d’une [!INCLUDE[csprcs](../includes/csprcs-md.md)] classe.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <DefaultName>MyClass.cs</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem ReplaceParameters="true">MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du schéma de modèle Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)
