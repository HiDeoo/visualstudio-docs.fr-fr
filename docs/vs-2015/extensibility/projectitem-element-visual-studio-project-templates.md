---
title: ProjectItem, élément (modèles de projet Visual Studio) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem
helpviewer_keywords:
- ProjectItem element [Visual Studio project templates]
- <ProjectItem> element [Visual Studio project templates]
ms.assetid: 82879fbe-7756-42cd-9a07-c10edf5b4673
caps.latest.revision: 19
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 84fb371460bc697660e176ca9df4c984d2b234bf
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "90839589"
---
# <a name="projectitem-element-visual-studio-project-templates"></a>ProjectItem, élément (modèles de projet Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Spécifie un fichier inclus dans le modèle de projet.  
  
> [!NOTE]
> L' `ProjectItem` élément accepte des attributs différents selon que le modèle est destiné à un projet ou à un élément. Cette rubrique explique l' `ProjectItem` élément pour les modèles de projet. Pour obtenir une explication de l' `ProjectItem` élément pour les modèles d’élément, consultez [ProjectItem, élément (modèles d’élément Visual Studio)](../extensibility/projectitem-element-visual-studio-item-templates.md).  
  
 \<VSTemplate>  
 \<TemplateContent>  
 \<Project>  
 \<ProjectItem>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProjectItem  
    TargetFileName="TargetFileName.ext"  
    ReplaceParameters="true/false"  
    OpenInEditor="true/false"  
    OpenInWebBrowser="true/false"  
    OpenInHelpBrowser="true/false"  
    OpenOrder="Value">  
        FileName.ext  
</ProjectItem>  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|`TargetFileName`|Attribut facultatif.<br /><br /> Spécifie le nom et le chemin d’accès de l’élément de projet lorsqu’un projet est créé à partir du modèle. Cet attribut est utile pour créer une structure de répertoires différente de la structure de répertoires dans le fichier. zip du modèle, ou pour l’utilisation du remplacement de paramètre pour créer un nom d’élément.|  
|`ReplaceParameters`|Attribut facultatif.<br /><br /> Valeur booléenne qui spécifie si l’élément a des valeurs de paramètres qui doivent être remplacées lors de la création d’un projet à partir du modèle. La valeur par défaut est `false`.|  
|`OpenInEditor`|Attribut facultatif.<br /><br /> Valeur booléenne qui spécifie si l’élément doit être ouvert dans son éditeur respectif dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] lorsqu’un projet est créé à partir du modèle.<br /><br /> Les `OpenInWebBrowser` `OpenInHelpBrowser` attributs et sont ignorés sur un élément dont la `OpenInEditor` valeur est `true` .<br /><br /> La valeur par défaut est `false`.|  
|`OpenInWebBrowser`|Attribut facultatif.<br /><br /> Valeur booléenne qui spécifie si l’élément doit être ouvert dans le navigateur Web lorsqu’un projet est créé à partir du modèle.<br /><br /> Seuls les fichiers HTML et les fichiers texte qui sont locaux au projet peuvent être ouverts dans le navigateur Web. Impossible d’ouvrir les URL externes avec cet attribut.<br /><br /> La valeur par défaut est `false`.|  
|`OpenInHelpBrowser`|Attribut facultatif.<br /><br /> Valeur booléenne qui spécifie si l’élément doit être ouvert dans la visionneuse d’aide lorsqu’un projet est créé à partir du modèle.<br /><br /> Seuls les fichiers HTML et les fichiers texte qui sont locaux au projet peuvent être ouverts dans le navigateur d’aide. Impossible d’ouvrir les URL externes avec cet attribut.<br /><br /> La valeur par défaut est `false`.|  
|`OpenOrder`|Attribut facultatif.<br /><br /> Spécifie une valeur numérique qui représente l’ordre dans lequel les éléments sont ouverts dans leurs éditeurs respectifs. Toutes les valeurs doivent être des multiples de 10. Les éléments avec des valeurs plus élevées `OpenOrder` sont ouverts en premier.|  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[Projet](../extensibility/project-element-visual-studio-templates.md)|Spécifie les fichiers ou répertoires à ajouter au projet.|  
  
## <a name="text-value"></a>Valeur texte  
 Une valeur texte est requise.  
  
 `string`Qui représente le nom ou le chemin d’accès à un fichier dans le fichier. zip du modèle.  
  
## <a name="remarks"></a>Remarques  
 `ProjectItem` est un enfant facultatif de `Project` .  
  
 L' `TargetFileName` attribut peut être utilisé pour créer une structure de répertoires différente de la structure de répertoires dans le fichier. zip du modèle. Par exemple, si le fichier `MyFile.vb` existe à la racine du fichier. zip du modèle, mais que vous souhaitez placer le fichier dans un répertoire nommé `CustomFiles` dans tous les projets créés à partir du modèle, vous devez utiliser le code XML suivant :  
  
```  
<ProjectItem TargetFileName="CustomFiles\MyFile.vb">MyFile.vb</ProjectItem>  
```  
  
 L' `TargetFileName` attribut peut également être utilisé pour renommer des fichiers qui contiennent des caractères internationaux dans leurs noms de fichiers. Par exemple, un fichier. zip de modèle ne peut pas contenir de noms de fichiers avec des caractères Unicode. par conséquent, le fichier doit être renommé pour pouvoir être compressé dans un fichier. zip. L' `TargetFileName` attribut peut être utilisé pour rétablir le nom de fichier Unicode d’origine.  
  
 L' `TargetFileName` attribut peut également être utilisé pour renommer des fichiers avec des paramètres. La procédure suivante explique comment renommer le fichier `MyFile.vb` , qui existe dans le répertoire racine du fichier. zip du modèle, en un nom de fichier basé sur le nom du projet.  
  
### <a name="to-rename-files-with-parameters"></a>Pour renommer des fichiers avec des paramètres  
  
1. Utilisez le code XML suivant dans le fichier. vstemplate :  
  
    ```  
    <ProjectItem TargetFileName="$safeprojectname$.vb">MyFile.vb</ProjectItem>  
    ```  
  
2. Ouvrez le fichier projet (. vbproj pour un [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] projet) dans un éditeur de texte ou [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] .  
  
3. Localisez la ligne dans le fichier projet qui ressemble au code XML suivant :  
  
    ```  
    <Compile Include="MyFile.vb">  
    ```  
  
4. Remplacez la ligne de code par le code XML suivant :  
  
    ```  
    <Compile Include="$safeprojectname$.vb">  
    ```  
  
     Quand un projet est créé à partir de ce modèle, le nom de fichier est basé sur le nom que l’utilisateur a entré dans la boîte de dialogue **nouveau projet** , avec tous les caractères et espaces non sécurisés supprimés. Pour plus d’informations, consultez [paramètres de modèle](../ide/template-parameters.md).  
  
## <a name="example"></a> Exemple  
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
            <ProjectItem ReplaceParameters="true">Form1.cs<ProjectItem>  
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
 [Paramètres de modèle](../ide/template-parameters.md)   
 [Élément ProjectItem (modèles d'élément Visual Studio)](../extensibility/projectitem-element-visual-studio-item-templates.md)
