---
title: RegisterAssembly, tâche | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#RegisterAssembly
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, RegisterAssembly task
- RegisterAssembly task [MSBuild]
ms.assetid: ba5f19ac-6764-4d28-9b79-a86de58f8987
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 47fba490edd07c61490760114ca8df91b3e35eb1
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59668221"
---
# <a name="registerassembly-task"></a>RegisterAssembly, tâche
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Lit les métadonnées dans l’assembly spécifié et ajoute les entrées nécessaires au Registre, ce qui permet aux clients COM de créer des classes [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] en toute transparence. Le comportement de cette tâche est similaire, mais pas identique, à celui de [Regasm.exe (outil Assembly Registration Tool)](http://msdn.microsoft.com/library/e190e342-36ef-4651-a0b4-0e8c2c0281cb).  
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres de la tâche `RegisterAssembly` .  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Assemblies`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` obligatoire.<br /><br /> Spécifie les assemblys à inscrire auprès de COM.|  
|`AssemblyListFile`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Contient des informations sur l’état entre la tâche `RegisterAssembly` et la tâche [UnregisterAssembly](../msbuild/unregisterassembly-task.md). Cela empêche la tâche `UnregisterAssembly` d’annuler l’inscription d’un assembly qui n’a pas pu s’inscrire dans la tâche `RegisterAssembly`.|  
|`CreateCodeBase`|Paramètre `Boolean` facultatif.<br /><br /> Si `true`, crée une entrée Codebase dans le Registre, qui spécifie le chemin de fichier d’un assembly qui n’est pas installé dans le Global Assembly Cache. Vous ne devez pas spécifier cette option si vous devez installer par la suite l'assembly que vous inscrivez dans le Global Assembly Cache.|  
|`TypeLibFiles`|Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie la bibliothèque de types à générer à partir de l’assembly spécifié. La bibliothèque de types générée contient des définitions des types accessibles définis dans l’assembly. La bibliothèque de types est générée uniquement si l’une des conditions suivantes est remplie :<br /><br /> -   Il n’existe pas de bibliothèque de types de ce nom à cet emplacement.<br />-   Il existe une bibliothèque de types, mais elle est plus ancienne que l’assembly passé.<br /><br /> Si la bibliothèque de types est plus récente que l’assembly passé, une nouvelle bibliothèque n’est pas créée, mais l’assembly est quand même inscrit.<br /><br /> Si ce paramètre est spécifié, il doit avoir le même nombre d’éléments que le paramètre `Assemblies`, sinon la tâche échoue. Si aucune entrée n’est spécifiée, la tâche utilise par défaut le nom de l’assembly et remplace l’extension de l’élément par .tlb.|  
  
## <a name="remarks"></a>Remarques  
 En plus des paramètres énumérés ci-dessus, cette tâche hérite des paramètres de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant utilise la tâche `RegisterAssembly` pour inscrire l’assembly spécifié par la collection d’éléments `MyAssemblies`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyAssemblies Include="MyAssembly.dll" />  
    <ItemGroup>  
  
    <Target Name="RegisterAssemblies">  
        <RegisterAssembly  
            Assemblies="@(MyAssemblies)" >  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Tâches](../msbuild/msbuild-tasks.md)   
 [Task Reference (Informations de référence sur les tâches MSBuild)](../msbuild/msbuild-task-reference.md)
