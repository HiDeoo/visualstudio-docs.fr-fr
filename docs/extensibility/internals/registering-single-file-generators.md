---
title: Inscription de générateurs de fichiers uniques | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- registration, custom tools
- custom tools, defining registry settings
ms.assetid: db7592c0-1273-4843-9617-6e2ddabb6ca8
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 185e60daac2aef2c8aeeb4f087547984e6fcf510
ms.sourcegitcommit: 4b29efeb3a5f05888422417c4ee236e07197fb94
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/11/2020
ms.locfileid: "90012033"
---
# <a name="registering-single-file-generators"></a>Inscription de générateurs de fichier unique
Pour rendre un outil personnalisé disponible dans [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , vous devez l’inscrire afin qu’il [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] puisse l’instancier et l’associe à un type de projet particulier.

### <a name="to-register-a-custom-tool"></a>Pour inscrire un outil personnalisé

1. Inscrivez la DLL de l’outil personnalisé dans le [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Registre local ou dans le registre système, sous HKEY_CLASSES_ROOT.

    Par exemple, Voici les informations d’inscription de l’outil personnalisé MSDataSetGenerator géré, qui est fourni avec [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] :

   ```
   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\CLSID\{E76D53CC-3D4F-40A2-BD4D-4F3419755476}]
   @="COM+ class: Microsoft.VSDesigner.CodeGenerator.TypedDataSourceGenerator.DataSourceGeneratorWrapper"
   "InprocServer32"="C:\\WINDOWS\\system32\\mscoree.dll"
   "ThreadingModel"="Both"
   "Class"="Microsoft.VSDesigner.CodeGenerator.TypedDataSourceGenerator.DataSourceGeneratorWrapper"
   "Assembly"="Microsoft.VSDesigner, Version=14.0.0.0, Culture=Neutral, PublicKeyToken=b03f5f7f11d50a3a"
   ```

2. Créez une clé de Registre dans la [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ruche souhaitée sous GUID des générateurs, \\ *GUID* où *GUID* est le GUID défini par le service ou le système de projet du langage spécifique. Le nom de la clé devient le nom de programmation de votre outil personnalisé. La clé de l’outil personnalisé a les valeurs suivantes :

   - (Par défaut)

        facultatif. Fournit une description conviviale de l’outil personnalisé. Ce paramètre est facultatif, mais recommandé.

   - CLSID

        Obligatoire. Spécifie l’identificateur de la bibliothèque de classes du composant COM qui implémente <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> .

   - GeneratesDesignTimeSource

        Obligatoire. Indique si les types des fichiers produits par cet outil personnalisé sont mis à la disposition des concepteurs visuels. La valeur de ce paramètre doit être (zéro) 0 pour les types qui ne sont pas disponibles pour les concepteurs visuels ou (un) 1 pour les types disponibles pour les concepteurs visuels.

   > [!NOTE]
   > Vous devez inscrire l’outil personnalisé séparément pour chaque langue pour laquelle vous souhaitez que l’outil personnalisé soit disponible.

    Par exemple, le MSDataSetGenerator s’inscrit pour chaque langue :

   ```
   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{164b10b9-b200-11d0-8c61-00a0c91e29d5}\MSDataSetGenerator]
   @="Microsoft VB Code Generator for XSD"
   "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"
   "GeneratesDesignTimeSource"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{fae04ec1-301f-11d3-bf4b-00c04f79efbc}\MSDataSetGenerator]
   @="Microsoft C# Code Generator for XSD"
   "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"
   "GeneratesDesignTimeSource"=dword:00000001
   ```

## <a name="see-also"></a>Voir aussi
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>
- [Implémentation de générateurs de fichier unique](../../extensibility/internals/implementing-single-file-generators.md)
- [Exposition des types aux concepteurs visuels](../../extensibility/internals/exposing-types-to-visual-designers.md)
- [Introduction à l'objet BuildManager](/previous-versions/8f9kffa8(v=vs.140))