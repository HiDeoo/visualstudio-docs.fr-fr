---
title: Génération parallèle de plusieurs projets avec MSBuild | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- parallel project builds
- building multiple projects in parallel
- msbuild, building projects in parallel
ms.assetid: c8c9aadc-33ad-4aa1-b07d-b879e9eabda0
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f80f0898167de133d78d27d26f97d0ab8ced0b31
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75843955"
---
# <a name="building-multiple-projects-in-parallel-with-msbuild"></a>Génération parallèle de plusieurs projets avec MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez utiliser MSBuild pour générer plus rapidement plusieurs projets en les exécutant en parallèle. Pour exécuter des builds en parallèle, vous utilisez les paramètres suivants sur un ordinateur multicœur ou multiprocesseur :  
  
- Le commutateur `/maxcpucount` à une invite de commande.  
  
- Le paramètre de tâche <xref:Microsoft.Build.Tasks.MSBuild.BuildInParallel%2A> sur une tâche MSBuild.  
  
> [!NOTE]
> Le commutateur **/verbosity** (**/v**) dans une ligne de commande peut également affecter les performances de génération. Les performances de génération risquent de diminuer si le niveau de détail de vos informations de journal de génération est défini sur « détaillé » ou « diagnostic ». Ces niveaux sont utilisés pour le dépannage. Pour plus d’informations, consultez [obtention de journaux de génération](../msbuild/obtaining-build-logs-with-msbuild.md) et [référence de ligne de commande](../msbuild/msbuild-command-line-reference.md).  
  
## <a name="maxcpucount-switch"></a>Commutateur /maxcpucount  
 Si vous utilisez le commutateur `/maxcpucount`, ou `/m` pour faire court, MSBuild peut créer le nombre spécifié de processus MSBuild.exe qui peuvent être exécutés en parallèle. Ces processus sont également appelés « processus de travail ». Chaque processus de travail utilise un processeur ou cœur distinct, sous réserve de disponibilité, pour générer un projet pendant que d’autres processeurs disponibles génèrent d’autres projets. Par exemple, si vous affectez la valeur « 4 » à ce commutateur, MSBuild crée quatre processus de travail pour générer le projet.  
  
 Si vous incluez le commutateur `/maxcpucount` sans spécifier de valeur, MSBuild utilise le nombre de processeurs dont est équipé l’ordinateur.  
  
 Pour plus d’informations sur ce commutateur, qui a été introduit dans MSBuild 3,5, consultez Référence de la [ligne de commande](../msbuild/msbuild-command-line-reference.md).  
  
 L’exemple suivant fait en sorte que MSBuild utilise trois processus de travail. Si vous utilisez cette configuration, MSBuild peut générer trois projets en même temps.  
  
```  
msbuild.exe myproj.proj /maxcpucount:3  
```  
  
## <a name="buildinparallel-task-parameter"></a>Paramètre de tâche BuildInParallel  
 `BuildInParallel` est un paramètre booléen facultatif sur une tâche [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]. Quand `BuildInParallel` a la valeur `true` (valeur par défaut), plusieurs processus de travail sont générés pour générer simultanément le plus de projets possible. Pour que cela fonctionne correctement, vous devez affecter une valeur supérieure à 1 au commutateur `/maxcpucount`, et le système doit avoir au moins deux cœurs ou deux processeurs.  
  
 Voici un exemple tiré de microsoft.common.targets qui décrit comment définir le paramètre `BuildInParallel`.  
  
```  
<PropertyGroup>  
    <BuildInParallel Condition="'$(BuildInParallel)' ==   
        ''">true</BuildInParallel>  
</PropertyGroup>  
<MSBuild  
    Projects="@(_MSBuildProjectReferenceExistent)"  
    Targets="GetTargetPath"  
    BuildInParallel="$(BuildInParallel)"  
    Properties="%(_MSBuildProjectReferenceExistent.SetConfiguration);   
        %(_MSBuildProjectReferenceExistent.SetPlatform)"  
    Condition="'@(NonVCProjectReference)'!='' and   
        ('$(BuildingSolutionFile)' == 'true' or   
        '$(BuildingInsideVisualStudio)' == 'true' or   
        '$(BuildProjectReferences)' != 'true') and     
        '@(_MSBuildProjectReferenceExistent)' != ''"  
    ContinueOnError="!$(BuildingProject)">  
    <Output TaskParameter="TargetOutputs"   
        ItemName="_ResolvedProjectReferencePaths"/>  
</MSBuild>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de plusieurs processeurs pour générer des projets](../msbuild/using-multiple-processors-to-build-projects.md)   
 [Écriture d’enregistreurs d’événements prenant en charge plusieurs processeurs](../msbuild/writing-multi-processor-aware-loggers.md)   
 [Blog sur le paramétrage du parallélisme des builds C++](https://blogs.msdn.com/b/visualstudio/archive/2010/03/08/tuning-c-build-parallelism-in-vs2010.aspx)
