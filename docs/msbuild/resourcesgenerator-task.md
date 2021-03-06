---
title: ResourcesGenerator, tâche | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- embedding resources into a .resources file [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild], parameters
ms.assetid: e782bbac-9ee6-472b-8171-3ee008c77b4e
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2b5aba45292aaa55a719eb19d6f0f6f115e8b477
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "77632509"
---
# <a name="resourcesgenerator-task"></a>ResourcesGenerator, tâche

La <xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> tâche incorpore une ou plusieurs ressources (*. jpg*, *. ico*, *. bmp*, XAML au format binaire et d’autres types d’extensions) dans un fichier *. Resources* .

## <a name="task-parameters"></a>Paramètres de tâche

|Paramètre|Description|
|---------------|-----------------|
|`OutputPath`|Paramètre de **chaîne** obligatoire.<br /><br /> Spécifie le chemin du répertoire de sortie. Si le chemin n’est pas absolu, il est traité comme un chemin relatif au répertoire racine du projet.|
|`OutputResourcesFile`|Paramètre de sortie **ITaskItem[]** obligatoire.<br /><br /> Spécifie le chemin d’accès et le nom du fichier *. Resources* généré. Si le chemin n’est pas absolu, le fichier *.resources* est généré par rapport au répertoire racine du projet.|
|`ResourcesFiles`|Paramètre **ITaskItem []** obligatoire.<br /><br /> Spécifie une ou plusieurs ressources à incorporer dans le fichier *. Resources* généré.|

## <a name="example"></a>Exemple

 L’exemple suivant génère un fichier *. Resources* avec une seule ressource *. bmp* . La ressource *. bmp* est générée dans un répertoire relatif au répertoire racine du projet.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <UsingTask
    TaskName="Microsoft.Build.Tasks.Windows.ResourcesGenerator"
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />
  <Target Name="ResourcesGeneratorTask">
    <ResourcesGenerator
      ResourceFiles="Resource1.bmp"
      OutputPath="myresources"
      OutputResourcesFile="myresources\my.resources" />
  </Target>
</Project>
```

## <a name="see-also"></a>Voir aussi

- [Informations de référence sur MSBuild WPF](../msbuild/wpf-msbuild-reference.md)
- [Informations de référence sur les tâches](../msbuild/wpf-msbuild-task-reference.md)
- [Informations de référence sur MSBuild](../msbuild/msbuild-reference.md)
- [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)
- [Générer une application WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)