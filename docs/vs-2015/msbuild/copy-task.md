---
title: Tâche Copy | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Copy
- MSBuild.Copy.SourceFileNotFound
- MSBuild.Copy.Retrying
- MSBuild.Copy.ExceededRetries
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Copy task
- Copy task [MSBuild]
ms.assetid: a46ba9da-3e4e-4890-b4ea-09a099b6bc40
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 08442d6044ca978e69f199e76c4668db63c319da
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68196590"
---
# <a name="copy-task"></a>Copy, tâche
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Copie les fichiers à un nouvel emplacement du système de fichiers.  
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres de la tâche `Copy` .  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`CopiedFiles`|Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Contient les éléments qui ont été copiés avec succès.|  
|`DestinationFiles`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Spécifie la liste de fichiers dans laquelle copier les fichiers sources. Cette liste est censée représenter un mappage un-à-un avec la liste spécifiée dans le paramètre `SourceFiles`. Autrement dit, le premier fichier spécifié dans `SourceFiles` est copié au premier emplacement indiqué dans `DestinationFiles`, et ainsi de suite.|  
|`DestinationFolder`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Indique le répertoire dans lequel vous souhaitez copier les fichiers. Il doit s’agir d’un répertoire et non d’un fichier. Si le répertoire n’existe pas, il est créé automatiquement.|  
|`OverwriteReadOnlyFiles`|Paramètre `Boolean` facultatif.<br /><br /> Remplace les fichiers même s’ils sont marqués comme fichiers en lecture seule.|  
|`Retries`|Paramètre `Int32` facultatif.<br /><br /> Spécifie le nombre de tentatives de copie, si toutes les tentatives précédentes ont échoué. La valeur par défaut est zéro.<br /><br /> **Remarque :** l’utilisation des tentatives peut masquer un problème de synchronisation dans votre processus de génération.|  
|`RetryDelayMilliseconds`|Paramètre `Int32` facultatif.<br /><br /> Spécifie le délai entre des tentatives nécessaires. Est défini par défaut sur l’argument RetryDelayMillisecondsDefault, qui est transmis au constructeur CopyTask.|  
|`SkipUnchangedFiles`|Paramètre `Boolean` facultatif.<br /><br /> Si `true`, ignore la copie des fichiers qui sont inchangés entre la source et la destination. La tâche `Copy` considère que les fichiers sont inchangés s’ils ont la même taille et la même heure de dernière modification. **Remarque :** si vous définissez ce paramètre sur `true`, vous ne devez pas utiliser l’analyse des dépendances sur la cible, car cette opération exécute uniquement la tâche si les heures de dernière modification des fichiers sources sont plus récentes que celles des fichiers de destination.|  
|`SourceFiles`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` obligatoire.<br /><br /> Spécifie les fichiers à copier.|  
|`UseHardlinksIfPossible`|Paramètre `Boolean` facultatif.<br /><br /> Si `true`, crée des liens physiques pour les fichiers copiés au lieu de copier les fichiers.|  
  
## <a name="warnings"></a>Avertissements  
 Des avertissements sont enregistrés, notamment ceux-ci :  
  
- `Copy.DestinationIsDirectory`  
  
- `Copy.SourceIsDirectory`  
  
- `Copy.SourceFileNotFound`  
  
- `Copy.CreatesDirectory`  
  
- `Copy.HardLinkComment`  
  
- `Copy.RetryingAsFileCopy`  
  
- `Copy.FileComment`  
  
- `Copy.RemovingReadOnlyAttribute`  
  
## <a name="remarks"></a>Notes  
 Le paramètre `DestinationFolder` ou `DestinationFiles` doit être spécifié, mais pas les deux. Si les deux paramètres sont spécifiés, la tâche échoue, et une erreur est enregistrée.  
  
 En plus des paramètres énumérés ci-dessus, cette tâche hérite des paramètres de la classe <xref:Microsoft.Build.Tasks.TaskExtension> , qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task> . Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant copie les éléments de la collection d’éléments `MySourceFiles` dans le dossier c:\MyProject\Destination.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MySourceFiles Include="a.cs;b.cs;c.cs"/>  
    </ItemGroup>  
  
    <Target Name="CopyFiles">  
        <Copy  
            SourceFiles="@(MySourceFiles)"  
            DestinationFolder="c:\MyProject\Destination"  
        />  
    </Target>  
  
</Project>  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant illustre la procédure à suivre pour effectuer une copie récursive. Ce projet copie tous les fichiers de manière récursive depuis c:\MySourceTree vers c:\MyDestinationTree, tout en conservant la structure de répertoire.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MySourceFiles Include="c:\MySourceTree\**\*.*"/>  
    </ItemGroup>  
  
    <Target Name="CopyFiles">  
        <Copy  
            SourceFiles="@(MySourceFiles)"  
            DestinationFiles="@(MySourceFiles->'c:\MyDestinationTree\%(RecursiveDir)%(Filename)%(Extension)')"  
        />  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Décrites](../msbuild/msbuild-tasks.md)   
 [Référence de tâche](../msbuild/msbuild-task-reference.md)
