---
title: Informations de référence sur les schémas de modèles Visual Studio | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- VSTEMPLATE files
- Visual Studio templates, schema
- .vstemplate files
ms.assetid: 6f74a2d5-3811-43d6-8b10-eb5823ad8995
caps.latest.revision: 25
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a15a08dc674940897bf465946efd2ec350cc7c42
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "62422121"
---
# <a name="visual-studio-template-schema-reference"></a>Référence du schéma de modèle Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette section contient des informations sur les éléments XML dans des fichiers .vstemplate, qui stockent les métadonnées des modèles de projet, d'élément et des Starter Kits.  
  
 Vous pouvez utiliser vstemplate.xsd pour valider des fichiers .vstemplate personnalisés. Ce fichier est disponible à l’adresse.. \\ *Dossier d’installation de Visual Studio*\Xml\Schemas\1033\vstemplate.xsd.  
  
|Élément|Éléments enfants|Attributs|  
|-------------|--------------------|----------------|  
|[AppliesTo](../extensibility/appliesto-element-visual-studio-templates.md)|Aucune|Aucune|  
|[Assembly (modèle)](../extensibility/assembly-element-visual-studio-templates.md)|--|--|  
|[Assembly (Extension Assistant)](../extensibility/assembly-element-visual-studio-template-wizard-extension.md)|--|--|  
|[BuildProjectOnload](../extensibility/buildprojectonload-element-visual-studio-templates.md)|--|--|  
|[CreateInPlace](../extensibility/createinplace-visual-studio-templates.md)|--|--|  
|[CreateNewFolder](../extensibility/createnewfolder-element-visual-studio-templates.md)|--|--|  
|[CustomDataSignature](../extensibility/customdatasignature-element-visual-studio-templates.md)|--|--|  
|[CustomParameter](../extensibility/customparameter-element-visual-studio-templates.md)|--|Nom<br /><br /> Valeur|  
|[CustomParameters](../extensibility/customparameters-element-visual-studio-templates.md)|CustomParameter|--|  
|[DefaultName](../extensibility/defaultname-element-visual-studio-templates.md)|--|--|  
|[Description](../extensibility/description-element-visual-studio-templates.md)|--|Paquet<br /><br /> ID|  
|[EnableEditOfLocationField](../extensibility/enableeditoflocationfield-element-visual-studio-templates.md)|--|--|  
|[EnableLocationBrowseButton](../extensibility/enablelocationbrowsebutton-element-visual-studio-templates.md)|--|--|  
|[Folder](../extensibility/folder-element-visual-studio-project-templates.md)|ProjectItem<br /><br /> Dossier|Nom|  
||[deprecated]|--|  
|[FullClassName](../extensibility/fullclassname-element-visual-studio-template-wizard-extension.md)|--|--|  
|[Hidden](../extensibility/hidden-element-visual-studio-templates.md)|--|--|  
|[Située](../extensibility/icon-element-visual-studio-templates.md)|--|Paquet<br /><br /> ID|  
|[LocationField](../extensibility/locationfield-element-visual-studio-project-templates.md)|--|--|  
|[LocationFieldMRUPrefix](../extensibility/locationfieldmruprefix-element-visual-studio-templates.md)|--|--|  
|[MaxFrameworkVersion](../extensibility/maxframeworkversion-element-visual-studio-templates.md)|--|--|  
|[Name](../extensibility/name-element-visual-studio-templates.md)|--|Paquet<br /><br /> ID|  
|[NumberOfParentCategoriesToRollUp](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)|--|--|  
|[PreviewImage](../extensibility/previewimage-element-visual-studio-templates.md)|--|--|  
|[Projet](../extensibility/project-element-visual-studio-templates.md)|Dossier<br /><br /> ProjectItem|Fichier<br /><br /> TargetFileName<br /><br /> ReplaceParameters|  
|[ProjectCollection](../extensibility/projectcollection-element-visual-studio-templates.md)|ProjectTemplateLink<br /><br /> SolutionFolder|--|  
|[ProjectItem (Modèles d'élément)](../extensibility/projectitem-element-visual-studio-item-templates.md)|--|Subtype<br /><br /> CustomTool<br /><br /> itemType<br /><br /> ReplaceParameters<br /><br /> TargetFileName|  
|[ProjectItem (modèles de projet)](../extensibility/projectitem-element-visual-studio-project-templates.md)|--|TargetFileName<br /><br /> ReplaceParameters<br /><br /> OpenInEditor<br /><br /> OpenOrder<br /><br /> OpenInWebBrowser<br /><br /> OpenInHelpBrowser|  
|[ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md)|--|--|  
|[ProjectTemplateLink](../extensibility/projecttemplatelink-element-visual-studio-templates.md)|--|ProjectName|  
|[ProjectType](../extensibility/projecttype-element-visual-studio-templates.md)|--|--|  
|[PromptForSaveOnCreation](../extensibility/promptforsaveoncreation-element-visual-studio-templates.md)|--|--|  
|[ProvideDefaultName](../extensibility/providedefaultname-element-visual-studio-templates.md)|--|--|  
|[Référence](../extensibility/reference-element-visual-studio-templates.md)|Assembly|--|  
|[Informations de référence](../extensibility/references-element-visual-studio-templates.md)|Référence|--|  
|[RequiredFrameworkVersion](../extensibility/requiredframeworkversion-element-visual-studio-templates.md)|--|--|  
|[RequiredPlatformVersion](../extensibility/requiredplatformversion-element-visual-studio-templates.md)|--|Version|  
|[SDKReference](../extensibility/sdkreference-element-visual-studio-templates.md)|--|Paquet|  
|[ShowByDefault](../extensibility/showbydefault-visual-studio-templates.md)|--|--|  
|[SolutionFolder](../extensibility/solutionfolder-element-visual-studio-templates.md)|ProjectTemplateLink<br /><br /> SolutionFolder|Nom|  
|[SortOrder](../extensibility/sortorder-element-visual-studio-templates.md)|--|--|  
|[SupportsCodeSeparation](../extensibility/supportscodeseparation-element-visual-studio-templates.md)|--|--|  
|[SupportsLanguageDropDown](../extensibility/supportslanguagedropdown-element-visual-studio-templates.md)|--|--|  
|[SupportsMasterPage](../extensibility/supportsmasterpage-element-visual-studio-templates.md)|--|--|  
|[TargetPlatformName](../extensibility/targetplatformname-element-visual-studio-templates.md)|RequiredPlatformVersion|--|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|ProjectCollection<br /><br /> Project<br /><br /> Références<br /><br /> ProjectItem<br /><br /> CustomParameters|[BuildOnLoad](../extensibility/buildprojectonload-visual-studio-templates.md)|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Nom<br /><br /> Description<br /><br /> Icône<br /><br /> PreviewImage<br /><br /> ProjectType<br /><br /> ProjectSubType<br /><br /> TemplateID<br /><br /> TemplateGroupID<br /><br /> SortOrder<br /><br /> CreateNewFolder<br /><br /> DefaultName<br /><br /> ProvideDefaultName<br /><br /> PromptForSaveOnCreation<br /><br /> EnableLocationBrowseButton<br /><br /> EnableEditOfLocationField<br /><br /> Hidden<br /><br /> DisplayInParentCategories<br /><br /> LocationFieldMRUPrefix<br /><br /> NumberOfParentCategoriesToRollUp<br /><br /> CreateInPlace<br /><br /> BuildOnLoad<br /><br /> BuildProjectOnload<br /><br /> ShowByDefault<br /><br /> LocationField<br /><br /> SupportsMasterPage<br /><br /> SupportsCodeSeparation<br /><br /> SupportsLanguageDropDown<br /><br /> RequiredFrameworkVersion<br /><br /> FrameworkVersion<br /><br /> MaxFrameworkVersion<br /><br /> CustomDataSignature<br /><br /> TargetPlatformName|--|  
|[TemplateGroupID](../extensibility/templategroupid-element-visual-studio-templates.md)|--|--|  
|[TemplateID](../extensibility/templateid-element-visual-studio-templates.md)|--|--|  
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|TemplateData<br /><br /> TemplateContent<br /><br /> WizardExtension<br /><br /> WizardData|Type<br /><br /> Version|  
|[WizardData](../extensibility/wizarddata-element-visual-studio-templates.md)|--|Nom|  
|[WizardExtension](../extensibility/wizardextension-element-visual-studio-templates.md)|Assembly<br /><br /> FullClassName|--|  
  
## <a name="see-also"></a>Voir aussi  
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)   
 [Guide pratique pour créer des Starter Kits](../ide/how-to-create-starter-kits.md)