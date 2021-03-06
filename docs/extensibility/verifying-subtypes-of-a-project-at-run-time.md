---
title: Vérification des sous-types d’un projet au moment de l’exécution | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project subtypes
- check subtypes
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f0d739a9f8734dd8941e3254d03364cbf4c77350
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80698183"
---
# <a name="verify-subtypes-of-a-project-at-run-time"></a>Vérifier les sous-types d’un projet au moment de l’exécution
Un VSPackage qui dépend d’un sous-type de projet personnalisé doit inclure une logique pour rechercher ce sous-type afin qu’il puisse échouer correctement si le sous-type n’est pas présent. La procédure suivante montre comment vérifier la présence d’un sous-type spécifié.

### <a name="to-verify-the-presence-of-a-subtype"></a>Pour vérifier la présence d’un sous-type

1. Obtenir la hiérarchie de projet à partir des objets projet et solution en tant qu' <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objet en ajoutant le code suivant à votre VSPackage.

    ```csharp
    EnvDTE.DTE dte;
    dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));

    EnvDTE.Project project;
    project = dte.Solution.Projects.Item(1);

    IVsSolution solution;
    solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));

    IVsHierarchy hierarchy;
    hierarchy = solution.GetProjectOfUniqueName(project.UniqueName);

    ```

2. Effectuez un cast de la hiérarchie en <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected> interface.

    ```csharp
    IVsAggregatableProjectCorrected AP;
    AP = hierarchy as IVsAggregatableProjectCorrected;

    ```

3. Obtient la liste des GUID de type de projet en appelant <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected.GetAggregateProjectTypeGuids%2A> .

    ```csharp
    string projTypeGuids = AP.GetAggregateProjectTypeGuids().ToUpper();

    ```

4. Vérifiez la liste du GUID du sous-type spécifié.

    ```csharp
    // Replace the string "MyGUID" with the GUID of the subtype.
    string guidMySubtype = "MyGUID";
    if (projTypeGuids.IndexOf(guidMySubtype) > 0)
    {
        // The specified subtype is present.
    }
    ```

## <a name="see-also"></a>Voir aussi
- [Sous-types de projet](../extensibility/internals/project-subtypes.md)
- [Conception de sous-types de projet](../extensibility/internals/project-subtypes-design.md)
- [Propriétés et méthodes étendues par les sous-types de projet](../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)
