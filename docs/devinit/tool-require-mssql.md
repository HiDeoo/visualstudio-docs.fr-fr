---
title: require-mssql
description: l’outil devinit requiert-MSSQL.
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
ms.openlocfilehash: 2ad02a29b8ea8b59abd4f246c5cc1d206451d3fc
ms.sourcegitcommit: 09d1f5cef5360cdc1cdfd4b22a1a426b38079618
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "91005189"
---
# <a name="require-mssql"></a>require-mssql

L' `require-mssql` outil est utilisé pour installer [Microsoft SQL Server édition développeur 2019](https://www.microsoft.com/sql-server/application-development) à partir de l’aide de l’ISO de MS SQL Server. SQL Server sera disponible sur `localhost` l’authentification Windows intégrée. SQL Server sera accessible avec la chaîne de connexion `"Server=localhost;Integrated Security=true;"` .

## <a name="usage"></a>Usage

Si les `input` Propriétés et `additionalOptions` sont omises ou vides, l’outil suivra le comportement [par défaut](#default-behavior) détaillé ci-dessous.

| Nom                                             | Type   | Obligatoire | Valeur                                                                                   |
|--------------------------------------------------|--------|----------|-----------------------------------------------------------------------------------------|
| **commentaires**                                     | string | Non       | Propriété de commentaires facultative. Non utilisé.                                                   |
| [**entrée**](#input)                              | string | Non       | Pour plus d’informations, consultez l' [entrée](#input) ci-dessous.                                                  |
| [**additionalOptions**](#additional-options)     | string | Non       | Non utilisé. Pour plus d’informations, consultez les [options supplémentaires](#additional-options) ci-dessous.              |

### <a name="input"></a>Entrée

La `input` propriété peut être une chaîne avec l’une des deux valeurs suivantes :

| Valeur     | Description                              |
|-----------|------------------------------------------|
| installer   | Installe SQL Server.                     |
| uninstall | Désinstalle toutes les installations de SQL Server. |

### <a name="additional-options"></a>Options supplémentaires

Non utilisé.

### <a name="default-behavior"></a>Comportement par défaut

Le comportement par défaut de l' `require-mssql` outil consiste à installer SQL Server.

### <a name="builtin-options"></a>Options builtin

L' `require-mssql` outil définit un certain nombre d’arguments de ligne de commande du programme d’installation pour s’assurer que le programme d’installation peut s’exécuter sans écran. Ces arguments sont répertoriés ci-dessous et leur documentation est disponible dans la [documentation d’installation de SQL](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-command-prompt?view=sql-server-ver15&preserve-view=true).

| Nom                                                               | Description |
|--------------------------------------------------------------------|-------------|
| /q                                                                 |             |
| /ACTION = installation                                                    |             |
| /FEATURES = SQLEngine, base de données locale                                       |             |
| /UpdateEnabled                                                     |             |
| /UpdateSource = MU                                                   |             |
| /X86 = false                                                         |             |
| /INSTANCENAME = MSSQLSERVER                                          |             |
| /INSTALLSHAREDDIR = "C:\Program Files\Microsoft SQL Server"          |             |
| /INSTALLSHAREDWOWDIR = "C:\Program Files (x86) \Microsoft SQL Server" |             |
| /SQLSVCINSTANTFILEINIT = true                                        |             |
| /INSTANCEDIR = "C:\Program Files\Microsoft SQL Server"               |             |
| /AGTSVCACCOUNT = "NT Service\SQLSERVERAGENT"                         |             |
| /AGTSVCSTARTUPTYPE = manuel                                          |             |
| /SQLSVCSTARTUPTYPE = automatique                                       |             |
| /SQLCOLLATION = "SQL_Latin1_General_CP1_CI_AS"                       |             |
| /SQLSVCACCOUNT = "NT Service\MSSQLSERVER"                            |             |
| /SQLSYSADMINACCOUNTS = administrateurs                                |             |
| /IACCEPTSQLSERVERLICENSETERMS                                      |             |

## <a name="example-usage"></a>Exemple d’utilisation

```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-2.0",
    "run": [
        {
            "comments": "Installs MSSQL.",
            "tool": "require-mssql",
            "input": "install",
        }
    ]
}
```
