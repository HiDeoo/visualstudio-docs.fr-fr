---
title: TemplateGroupID, élément (modèles Visual Studio) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateGroupID
helpviewer_keywords:
- TemplateGroupID element [Visual Studio Templates]
- <TemplateGroupID> element [Visual Studio Templates]
ms.assetid: bce7b49a-90bc-4691-aff3-a87e209f6d83
caps.latest.revision: 19
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 53d1f6628ff9df48879a34417b7d89223d848dd8
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68186433"
---
# <a name="templategroupid-element-visual-studio-templates"></a>TemplateGroupID, élément (modèles Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Spécifie le genre de projet dans lequel les modèles d'élément doivent s'afficher. Cet élément est significatif quand [ShowByDefault (modèles Visual Studio)](../extensibility/showbydefault-visual-studio-templates.md) a la valeur `false` . Quand [ShowByDefault (modèles Visual Studio)](../extensibility/showbydefault-visual-studio-templates.md) a la valeur `true` , un modèle d’élément est disponible dans tous les types de projets.  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<TemplateGroupID>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<TemplateGroupID> ... </TemplateGroupID>  
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
  
 Le texte spécifie un identificateur pour une catégorie de modèles d'élément.  
  
## <a name="remarks"></a>Notes  
 `TemplateGroupID` est un élément.  
  
 La valeur de l' `TemplateGroupID` élément est utilisée avec l’inscription du système de projet (HKEY_LOCAL_MACHINE \Software\microsoft\visualstudio \\ *\<version number>* \projets \\ ) pour filtrer les modèles qui s’affichent dans la boîte de dialogue **Ajouter un nouvel élément** .  
  
|Valeur Visual C++|Signification|  
|------------------------|-------------|  
|VC-Native|Utilisé pour les projets natifs. Correspond également à la valeur par défaut, s'il est impossible de déterminer un type de projet.|  
|VC-Managed|Utilisé pour les projets managés (/clr)|  
|VC-Windows|Utilisé pour tous les projets qui ciblent la plateforme Windows (natifs/managés/Store)|  
|WinRT-Native-UAP|Utilisé pour les projets de Store Windows 10|  
|CodeSharing-Native|Utilisé pour les projets d'éléments partagés|  
|WinRT-Native-6.3|Utilisé pour les projets de Store Windows 8.1|  
|WinRT-Native-Phone-6.3|Utilisé pour les projets Windows Phone 8.1|  
|WinRT-Native|Utilisé pour les projets de Store Windows 8.0|  
|VC-Android|Utilisé pour les projets Android|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du schéma de modèle Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)
