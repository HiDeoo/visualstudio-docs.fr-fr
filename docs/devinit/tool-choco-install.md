---
title: choco-install
description: devinit Tool Choco-install pour installer les packages en chocolat.
ms.date: 08/28/2020
ms.topic: reference
author: andysterland
ms.author: andster
manager: jillfra
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.prod: visual-studio-windows
ms.technology: devinit
ms.openlocfilehash: e30db0eea924fcbc9587593266323d81c4ff1b40
ms.sourcegitcommit: 09d1f5cef5360cdc1cdfd4b22a1a426b38079618
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "91006049"
---
# <a name="choco-install"></a>choco-install

L' `choco-install` outil peut être utilisé pour installer et mettre à jour des packages en [chocolat](https://chocolatey.org/) .

## <a name="usage"></a>Usage

Si les `input` Propriétés et `additionalOptions` sont omises ou vides, l’outil ne fait rien.

| Nom                                             | Type   | Obligatoire | Valeur                                                                                                          |
|--------------------------------------------------|--------|----------|----------------------------------------------------------------------------------------------------------------|
| **commentaires**                                     | string | Non       | Propriété de commentaires facultative. Non utilisé.                                                                          |
| [**entrée**](#input)                              | string | Non       | Le package à installer. Pour plus d’informations, consultez l' [entrée](#input) ci-dessous.                                                 |
| [**additionalOptions**](#additional-options)     | string | Non       | Options supplémentaires à passer à l’outil. Pour plus d’informations, consultez les [options supplémentaires](#additional-options) ci-dessous.       |

### <a name="input"></a>Entrée

La `input` propriété est utilisée pour spécifier le nom du package à installer (par exemple, « MongoDB ») ou le chemin d’accès à un fichier de configuration aux formats suivants _packages.config_, _. NuSpec_et _. nupkg_. La valeur de `input` sera ajoutée à une `choco install` commande (par exemple `choco install mongodb` ), ainsi que tous les arguments spécifiques à [`additionalOptions`](#additional-options) et les options intégrées `choco` (définies [ci-dessous](#built-in-options)). Les packages sont disponibles dans la [Galerie](https://chocolatey.org/packages)de packages en chocolat. Lorsque vous utilisez un fichier de configuration, vous pouvez transmettre le chemin d’accès à ce fichier dans la `input` propriété, par exemple `"input":"packages.config"` .

### <a name="additional-options"></a>Options supplémentaires

Des options de configuration supplémentaires peuvent être transmises en tant que valeur de `additionalOptions` . Ces arguments sont directement dirigés vers les arguments utilisés par [`choco install`](https://chocolatey.org/docs/commands-install) et sont définis dans la documentation en chocolat.

### <a name="built-in-options"></a>Options intégrées

L' `choco-install` outil définit un certain nombre d' `choco` arguments de ligne de commande pour s’assurer que `choco` peut s’exécuter sans affichage. Ces arguments sont répertoriés ci-dessous et leur documentation est disponible dans la [documentation en chocolat](https://chocolatey.org/docs/).

| Nom                  | Description                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------|
| **--Oui**             | Confirmer toutes les invites : choisit la réponse affirmative au lieu de vous demander. Entraîne `--accept-license.` |
| **--non-Progress**     | Ne pas afficher la progression-les pourcentages de progression ne s’affichent pas.                                         |
| **--Skip-PowerShell** | Ignorer PowerShell-chocolateyInstall.ps1 ne sera pas exécuté.                                              |

## <a name="example-usage"></a>Exemple d’utilisation

```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-2.0",
    "run": [
        {
            "comments": "Example that will trigger the Default behavior of installing packages listed in a packages.config file.",
            "tool": "choco-install",
            "input": "packages.config",
        },
        {
            "comments": "Example that will install the package 'mongodb'.",
            "tool": "choco-install",
            "input": "mongodb"
        },
        {
            "comments": "Example that will install the '4.2.7' version of 'mongodb'.",
            "tool": "choco-install",
            "input": "mongodb",
            "additionalOptions": "--version 4.2.7"
        }
    ]
}
```
