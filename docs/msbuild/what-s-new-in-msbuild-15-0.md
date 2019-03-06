---
title: Nouveautés de MSBuild 15 | Microsoft Docs
ms.date: 03/01/2017
ms.topic: conceptual
ms.assetid: 9976b6fd-d052-4017-b848-35b5bf4b2f66
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 07d97707034946f4711ac7df92c6a0f0743d13fe
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56612658"
---
# <a name="whats-new-in-msbuild-15"></a>Nouveautés de MSBuild 15

MSBuild fait désormais partie intégrante du [Kit de développement logiciel (SDK) .NET Core](https://www.microsoft.com/net/download/core) et peut générer des projets .NET Core sur Windows, macOS et Linux.

## <a name="changed-path"></a>Chemin d’accès modifié

 MSBuild est à présent installé dans un dossier situé sous chaque version de Visual Studio. Par exemple, *C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\MSBuild*. Vous pouvez également localiser MSBuild à l’aide du module PowerShell suivant : [vssetup.powershell](https://github.com/Microsoft/vssetup.powershell).

 MSBuild n’est plus installé dans le Global Assembly Cache. Pour référencer MSBuild par programme, utilisez les packages NuGet.

## <a name="changed-properties"></a>Propriétés modifiées

 Les propriétés MSBuild ci-après ont été mises à jour afin de correspondre au nouveau numéro de version.

- `MSBuildToolsVersion` pour cette version des outils présente la valeur 15.0. La version de l’assembly est 15.1.0.0.

- `MSBuildToolsPath` n’a plus d’emplacement fixe. Par défaut, il se trouve dans le dossier *MSBuild\15.0\Bin* relatif à l’emplacement d’installation de Visual Studio, mais cet emplacement est modifiable pendant l’installation.

- Les valeurs `ToolsVersion` ne sont plus définies dans le Registre.

- Les propriétés `SDK35ToolsPath` et `SDK40ToolsPath` pointent vers le Kit de développement logiciel (SDK) .NET Framework, qui est fourni avec cette version de Visual Studio (par exemple, 10.0A pour les outils 4.X).

## <a name="updates"></a>Mises à jour
- [L’élément Project](../msbuild/project-element-msbuild.md) comporte un nouvel attribut `SDK`. Par ailleurs, l’attribut `Xmlns` est désormais facultatif. Pour plus d’informations sur l’attribut `SDK`, consultez [Guide pratique pour utiliser les kits SDK de projet MSBuild](../msbuild/how-to-use-project-sdk.md), [Packages, métapaquets et frameworks](/dotnet/core/packages) et [Ajouts au format csproj pour .NET Core](/dotnet/core/tools/csproj).
- [L’élément Item](../msbuild/item-element-msbuild.md) à l’extérieur des cibles comporte un nouvel attribut `Update`. En outre, la restriction sur l’attribut `Remove` a été supprimée.
- *Directory.Build.props* est un fichier défini par l’utilisateur qui fournit des personnalisations aux projets situés dans un répertoire. Ce fichier est importé automatiquement à partir de *Microsoft.Common.props*, sauf si la propriété `ImportDirectoryBuildTargets` est définie sur **false**. *Directory.Build.targets* est importé par *Microsoft.Common.targets*.
- Toutes les métadonnées dont le nom n’entre pas en conflit avec la liste d’attributs actuelle peuvent être exprimées en option sous la forme d’un attribut. Pour plus d’informations, voir [Élément Item](../msbuild/item-element-msbuild.md).

## <a name="new-property-functions"></a>Nouvelles fonctions de propriété

- `EnsureTrailingSlash` ajoute une barre oblique finale à un chemin d’accès si cette barre n’est pas déjà présente.
- `NormalizePath` combine les éléments du chemin d’accès et garantit que la chaîne de sortie présente les caractères de séparation de répertoire corrects pour le système d’exploitation actuel.
- `NormalizeDirectory` combine les éléments du chemin d’accès, vérifie l’existence d’une barre oblique finale et garantit que la chaîne de sortie présente les caractères de séparation de répertoire corrects pour le système d’exploitation actuel.
- `GetPathOfFileAbove` renvoie le chemin d’accès du fichier précédant immédiatement celui indiqué. Sur le plan fonctionnel, cette opération revient à appeler `<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), dir.props))\dir.props" />`

## <a name="see-also"></a>Voir aussi
- [MSBuild](../msbuild/msbuild.md)
