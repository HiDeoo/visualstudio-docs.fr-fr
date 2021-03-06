---
title: 'Nouvelle génération de projet : en coulisses, partie 2 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio], new project dialog
- projects [Visual Studio], new project generation
ms.assetid: 73ce91d8-0ab1-4a1f-bf12-4d3c49c01e13
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6643c52ff8e5801c562524e99c4e3f03c00f74b9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "65687483"
---
# <a name="new-project-generation-under-the-hood-part-two"></a>Nouvelle génération de projet : Rouages du système, seconde partie
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Dans [la génération d’un nouveau projet : sous le capot,](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md) nous avons vu comment la boîte **de dialogue Nouveau projet** est remplie. Supposons que vous avez sélectionné une **application Windows Visual C#**, renseigné les zones de texte **nom** et **emplacement** et cliqué sur OK.  
  
## <a name="generating-the-solution-files"></a>Génération des fichiers solution  
 Le choix d’un modèle d’application indique [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] de décompresser et d’ouvrir le fichier. vstemplate correspondant, et de lancer un modèle pour interpréter les commandes XML dans ce fichier. Ces commandes créent des projets et des éléments de projet dans la solution nouvelle ou existante.  
  
 Le modèle décompresse les fichiers sources, appelés modèles d’élément, à partir du même dossier. zip qui contient le fichier. vstemplate. Le modèle copie ces fichiers dans le nouveau projet, en les personnalisant en conséquence. Pour obtenir une vue d’ensemble des modèles de projet et d’élément, consultez [plume : modèles Visual Studio](https://msdn.microsoft.com/141fccaa-d68f-4155-822b-27f35dd94041).  
  
### <a name="template-parameter-replacement"></a>Remplacement des paramètres de modèle  
 Lorsque le modèle copie un modèle d’élément dans un nouveau projet, il remplace tous les paramètres de modèle par des chaînes pour personnaliser le fichier. Un paramètre de modèle est un jeton spécial qui est précédé et suivi d’un signe dollar, par exemple, $date $.  
  
 Examinons un modèle d’élément de projet standard. Extrayez et examinez Program.cs dans le dossier Program Files\Microsoft Visual Studio 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip  
  
```  
using System;  
using System.Collections.Generic;  
using System.Windows.Forms;  
  
namespace $safeprojectname$  
{  
    static class Program  
    {  
        // source code deleted here for brevity  
    }  
}  
```  
  
 Si vous créez un nouveau projet d’application Windows nommé simple, le modèle remplace le `$safeprojectname$` paramètre par le nom du projet.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Windows.Forms;  
  
namespace Simple  
{  
    static class Program  
    {  
        // source code deleted here for brevity  
    }  
}  
```  
  
 Pour obtenir une liste exhaustive des paramètres de modèle, consultez [Paramètres de modèle](../../ide/template-parameters.md).  
  
## <a name="a-look-inside-a-vstemplate-file"></a>Regarder à l’intérieur d’un. Fichier VSTemplate  
 Un fichier. vstemplate de base a le format suivant :  
  
```  
<VSTemplate Version="2.0.0"     xmlns="http://schemas.microsoft.com/developer/vstemplate/2005"     Type="Project">  
    <TemplateData>  
    </TemplateData>  
    <TemplateContent>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 Nous avons examiné la \<TemplateData> section de la [nouvelle génération de projet : sous le capot, première partie](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md). Les balises de cette section sont utilisées pour contrôler l’apparence de la boîte de dialogue **nouveau projet** .  
  
 Les balises de la \<TemplateContent> section contrôlent la génération de nouveaux projets et éléments de projet. Voici la \<TemplateContent> section du fichier cswindowsapplication. vstemplate dans le dossier \Program Files\Microsoft Visual Studio 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip.  
  
```  
<TemplateContent>  
  <Project File="WindowsApplication.csproj" ReplaceParameters="true">  
    <ProjectItem ReplaceParameters="true"  
      TargetFileName="Properties\AssemblyInfo.cs">  
      AssemblyInfo.cs  
    </ProjectItem>  
    <ProjectItem TargetFileName="Properties\Resources.resx">  
      Resources.resx  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Resources.Designer.cs">  
      Resources.Designer.cs  
    </ProjectItem>  
    <ProjectItem TargetFileName="Properties\Settings.settings">  
      Settings.settings  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Settings.Designer.cs">  
      Settings.Designer.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true" OpenInEditor="true">  
      Form1.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true">  
      Form1.Designer.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true">  
      Program.cs  
    </ProjectItem>  
  </Project>  
</TemplateContent>  
```  
  
 La \<Project> balise contrôle la génération d’un projet, et la \<ProjectItem> balise contrôle la génération d’un élément de projet. Si le paramètre ReplaceParameters a la valeur true, le modèle personnalise tous les paramètres de modèle dans le fichier projet ou l’élément. Dans ce cas, tous les éléments de projet sont personnalisés, à l’exception de Settings. Settings.  
  
 Le paramètre TargetFileName spécifie le nom et le chemin d’accès relatif du fichier projet ou de l’élément résultant. Cela vous permet de créer une structure de dossiers pour votre projet. Si vous ne spécifiez pas cet argument, l’élément de projet porte le même nom que le modèle d’élément de projet.  
  
 La structure des dossiers de l’application Windows obtenue ressemble à ceci :  
  
 ![SimpleSolution](../../extensibility/internals/media/simplesolution.png "SimpleSolution")  
  
 La première et seule \<Project> balise du modèle lit :  
  
```  
<Project File="WindowsApplication.csproj" ReplaceParameters="true">  
```  
  
 Cela indique au nouveau modèle de projet de créer le fichier de projet. csproj simple en copiant et en personnalisant l’élément de modèle fichier WindowsApplication. csproj.  
  
### <a name="designers-and-references"></a>Concepteurs et références  
 Vous pouvez voir dans la Explorateur de solutions que le dossier Propriétés est présent et qu’il contient les fichiers attendus. Mais qu’en est-il des références de projet et des dépendances de fichier de concepteur, comme Resources.Designer.cs à Resources. resx et Form1.Designer.cs à Form1.cs ?  Celles-ci sont configurées dans le fichier. csproj simple lorsqu’elles sont générées.  
  
 Voici le \<ItemGroup> de simple. csproj qui crée les références de projet :  
  
```  
<ItemGroup>  
    <Reference Include="System" />  
    <Reference Include="System.Data" />  
    <Reference Include="System.Deployment" />  
    <Reference Include="System.Drawing" />  
    <Reference Include="System.Windows.Forms" />  
    <Reference Include="System.Xml" />  
</ItemGroup>  
```  
  
 Vous pouvez voir qu’il s’agit des six références de projet qui s’affichent dans la Explorateur de solutions. Voici une section d’une autre \<ItemGroup> . De nombreuses lignes de code ont été supprimées pour plus de clarté. Cette section rend Settings.Designer.cs dépendant des paramètres. Settings :  
  
```  
<ItemGroup>  
    <Compile Include="Properties\Settings.Designer.cs">  
        <DependentUpon>Settings.settings</DependentUpon>  
    </Compile>  
</ItemGroup>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Nouvelle génération de projet : Rouages du système, première partie](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md)  
 [MSBuild](../../msbuild/msbuild.md)
