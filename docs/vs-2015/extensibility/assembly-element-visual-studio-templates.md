---
title: Assembly, élément (modèles Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Assembly
helpviewer_keywords:
- Assembly element [Visual Studio templates]
- <Assembly> element [Visual Studio templates]
ms.assetid: 9242f76a-1273-4b8a-8f26-6606f91829ef
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 987e46810aa8cfe51102d2940bf48d24fd6824cf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47502087"
---
# <a name="assembly-element-visual-studio-templates"></a>Assembly, élément (modèles Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [Assembly, élément (modèles Visual Studio)](https://docs.microsoft.com/visualstudio/extensibility/assembly-element-visual-studio-templates).  
  
Spécifie les informations relatives à un assembly, le modèle utilise pour ajouter une référence de cet assembly aux projets.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Références >  
 \<Référence >  
 \<Assembly >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Assembly> AssemblyName </Assembly>  
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
|[Référence](../extensibility/reference-element-visual-studio-templates.md)|Spécifie la référence d’assembly à ajouter quand l’élément est ajouté à un projet.|  
  
## <a name="text-value"></a>Valeur texte  
 Une valeur texte est requise.  
  
 Ce texte spécifie l’assembly à ajouter à un projet lorsque le modèle d’élément est instancié. Ce nom d’assembly doit être spécifié dans une des manières suivantes :  
  
-   En tant que nom complet de l’assembly. Exemple :  
  
    ```  
    <Assembly>  
        MyAssembly, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom = null.  
    </Assembly>  
    ```  
  
-   En tant que référence de texte simple. Exemple :  
  
    ```  
    <Assembly> System </Assembly>  
    ```  
  
## <a name="remarks"></a>Notes  
 `Assembly` est un élément enfant obligatoire de `Reference`.  
  
 Le `Reference`, `References,` et `Assembly` éléments peuvent uniquement être utilisés dans les fichiers .vstemplate ayant un `Type` valeur d’attribut `Item`.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant illustre la `TemplateContent` élément d’un modèle d’élément. Ce code XML ajoute des références aux assemblys System.dll et System.Data.dll.  
  
```  
<TemplateContent>  
    <References>  
        <Reference>  
            <Assembly>  
                System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
        <Reference>  
            <Assembly>  
                System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
    </References>  
    ...  
</TemplateContent>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du schéma de modèle Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)

