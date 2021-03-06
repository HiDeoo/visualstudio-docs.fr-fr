---
title: require-vscomponent
description: l’outil devinit requiert-vscomponent.
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
ms.openlocfilehash: 7c47c219fa0c0ef32946d6e0500bc37ce9aec0ff
ms.sourcegitcommit: 09d1f5cef5360cdc1cdfd4b22a1a426b38079618
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "91005036"
---
# <a name="require-vscomponent"></a>require-vscomponent

L' `require-vscomponent` outil est utilisé pour importer des configurations Visual Studio dans Visual Studio existant. En savoir plus à `.vsconfig` [ce](https://docs.microsoft.com/visualstudio/install/import-export-installation-configurations)sujet.

## <a name="usage"></a>Usage

Si les `input` Propriétés et `additionalOptions` sont omises ou vides, l’outil suivra le comportement [par défaut](#default-behavior) détaillé ci-dessous.

| Nom                                     | Type   | Obligatoire | Valeur                                                                |
|------------------------------------------|--------|----------|----------------------------------------------------------------------|
| **commentaires**                             | string | Non       | Propriété de commentaires facultative. Non utilisé.                                |
| [**entrée**](#input)                      | string | Non       | Chemin d’accès complet de `.vsconfig` . Pour plus d’informations, consultez l' [entrée](#input) ci-dessous. |
| [additionalOptions](#additional-options) | string | Non       | Pour plus d’informations, consultez les [options supplémentaires](#additional-options) ci-dessous.     |

### <a name="input"></a>Entrée

La `input` propriété est utilisée pour spécifier le chemin d’accès complet du `.vsconfig` fichier. Si ce n’est pas mentionné, l’outil recherche un `.vsconfig` dans le répertoire actif et transmet la valeur au Visual Studio installer.

### <a name="additional-options"></a>Options supplémentaires

Non utilisé.

### <a name="default-behavior"></a>Comportement par défaut

Le comportement par défaut de l' `require-vscomponent` outil consiste à rechercher un `.vsconfig` fichier dans le répertoire actif et à exécuter le Visual Studio installer avec ces détails en mode silencieux. `require-vscomponent` prend uniquement en charge la modification d’une installation existante de Visual Studio.

## <a name="example-usage"></a>Exemple d’utilisation

```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-2.0",
    "comments": "A sample dot-devinit file.",
    "run": [
        {
            "tool": "require-vscomponent",
            "comments": "Imports .vsconfig file which is passed as input to Visual Studio.",
            "input": "C:\\.vsconfig"
        }
    ]
}
```
