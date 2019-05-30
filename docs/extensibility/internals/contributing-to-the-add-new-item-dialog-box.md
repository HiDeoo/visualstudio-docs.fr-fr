---
title: Contribuer à la boîte de dialogue Nouvel élément Ajouter | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, contributing to
ms.assetid: b2e53175-9372-4d17-8c2b-9264c9e51e9c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 443f52edda5f3bedb2e3f8c8dbbe748254fd7be7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66335569"
---
# <a name="contribute-to-the-add-new-item-dialog-box"></a>Contribuer à la boîte de dialogue Ajouter un nouvel élément
Un sous-type de projet peut fournir un nouveau répertoire complète d’éléments pour le **ajouter un nouvel élément** boîte de dialogue en vous inscrivant **ajouter un élément** modèles sous le **projets** sous-clé de Registre.

## <a name="register-add-new-item-templates"></a>Inscrire les modèles Ajouter un nouvel élément
 Cette section se trouve sous **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects** dans le Registre. Les entrées de Registre ci-dessous supposent un [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projet agrégé par un sous-type de projet hypothétique. Les entrées pour le [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projet sont répertoriés ci-dessous.

```
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}]
@="#2143"
"DefaultProjectExtension"="vbproj"
"PossibleProjectExtensions"="vbproj;vbp"
"ProjectTemplatesDir"="visualStudioInstallPath\\Vb\\.\\VBProjects"

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}\AddItemTemplates\TemplateDirs\{12345678-1234-1234-1122334455667788}\/1]
@="#100"
"TemplatesDir"="projectSubTypeTemplatesDir\\VBProjectItems"
```

 Le **AddItemTemplates\TemplateDirs** sous-clé contient des entrées de Registre avec le chemin d’accès au répertoire dans lequel les éléments mis à disposition dans le **ajouter un nouvel élément** boîte de dialogue sont placés.

 L’environnement charge automatiquement tous les **AddItemTemplates** données sous le **projets** sous-clé de Registre. Ces données peuvent inclure les données pour les implémentations de projet de base, ainsi que les données de types de sous-type de projet spécifique. Chaque sous-type de projet est identifiée par un type de projet **GUID**. Le sous-type de projet peut spécifier qu’un autre ensemble de **ajouter un élément** modèles doivent être utilisés pour une instance de projet versionné particulier en prenant en charge la `VSHPROPID_ AddItemTemplatesGuid` énumération à partir de <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> dans <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> mise en œuvre pour retourner la valeur GUID du sous-type de projet. Si le `VSHPROPID_AddItemTemplatesGuid` propriété n’est pas spécifiée, le projet de base GUID est utilisé.

 Vous pouvez filtrer les éléments dans le **ajouter un nouvel élément** boîte de dialogue en implémentant le <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg> interface sur l’objet d’agrégateur de sous-type de projet. Par exemple, un sous-type de projet qui implémente un projet de base de données en agrégeant un [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projet d’équipe, pouvez filtrer la [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] des éléments spécifiques à partir de la **ajouter un nouvel élément** boîte de dialogue par l’implémentation du filtrage et activer, pouvez ajouter les éléments spécifiques au projet de base de données en prenant en charge `VSHPROPID_ AddItemTemplatesGuid` dans <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>. Pour plus d’informations sur le filtrage et l’ajout d’éléments à la **ajouter un nouvel élément** boîte de dialogue, consultez [ajouter des éléments à la boîte de dialogue Ajouter un nouvel élément](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md).

## <a name="see-also"></a>Voir aussi
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>
- [CATID des objets qui sont généralement utilisés pour étendre des projets](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)