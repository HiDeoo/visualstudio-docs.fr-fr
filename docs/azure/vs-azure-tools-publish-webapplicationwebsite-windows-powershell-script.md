---
title: Publier une application Web à l’aide d’un script PowerShell
description: Découvrez comment publier un projet web sur un site web Azure. Ce script crée les ressources requises dans votre abonnement Azure si elles n’existent pas.
ms.custom: vs-azure
author: ghogen
manager: jillfra
assetId: 63cfaa2d-f04d-40dc-8677-345385c278d5
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: e91fed105ce61dfc7e1cd2779ebcca0b33a06c97
ms.sourcegitcommit: 4ae5e9817ad13edd05425febb322b5be6d3c3425
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/11/2020
ms.locfileid: "90036494"
---
# <a name="publish-webapplicationwebsite-windows-powershell-script"></a>Publish-WebApplicationWebSite (script Windows PowerShell)
## <a name="syntax"></a>Syntaxe
Publie un projet web sur un site web Azure. Le script crée les ressources requises dans votre abonnement Azure si elles n’existent pas.

```
Publish-WebApplicationWebSite
–Configuration <configuration>
-SubscriptionName <subscriptionName>
-WebDeployPackage <packageName>
-DatabaseServerPassword @{Name = "name"; Password = "password"}
-SendHostMessagesToOutput
-Verbose
```

## <a name="configuration"></a>Configuration
Le chemin d'accès au fichier de configuration JSON qui décrit les détails du déploiement.

| Paramètre | Valeur par défaut |
| --- | --- |
| Alias |aucun |
| Requis ? |true |
| Position |nommée |
| Valeur par défaut |aucun |
| Accepter l'entrée de pipeline ? |false |
| Accepter les caractères génériques ? |false |

## <a name="subscriptionname"></a>SubscriptionName
Nom de l’abonnement Azure dans lequel vous souhaitez créer le site web.

| Paramètre | Valeur par défaut |
| --- | --- |
| Alias |aucun |
| Requis ? |false |
| Position |nommée |
| Valeur par défaut |aucun |
| Accepter l'entrée de pipeline ? |false |
| Accepter les caractères génériques ? |false |

## <a name="webdeploypackage"></a>WebDeployPackage
Le chemin d'accès au package de déploiement web à publier sur le site web. Vous pouvez créer ce package à l'aide de l'Assistant Publier le site web dans Visual Studio. Pour plus d’informations, consultez [Prise en main des services cloud Azure et d'ASP.NET](vs-azure-tools-publish-webapplicationwebsite-windows-powershell-script.md).

| Paramètre | Valeur par défaut |
| --- | --- |
| Alias |aucun |
| Requis ? |false |
| Position |nommée |
| Valeur par défaut |aucun |
| Accepter l'entrée de pipeline ? |false |
| Accepter les caractères génériques ? |false |

## <a name="databaseserverpassword"></a>DatabaseServerPassword
Le nom d’utilisateur et le mot de passe pour la base de données SQL dans Azure.

| Paramètre | Valeur par défaut |
| --- | --- |
| Alias |aucun |
| Requis ? |false |
| Position |nommée |
| Valeur par défaut |aucun |
| Accepter l'entrée de pipeline ? |false |
| Accepter les caractères génériques ? |false |

## <a name="sendhostmessagestooutput"></a>SendHostMessagesToOutput
Si true, imprime des messages à partir du script dans le flux de sortie.

| Paramètre | Valeur par défaut |
| --- | --- |
| Alias |aucun |
| Requis ? |false |
| Position |nommée |
| Valeur par défaut |false |
| Accepter l'entrée de pipeline ? |false |
| Accepter les caractères génériques ? |false |

## <a name="remarks"></a>Remarques
Pour obtenir une explication complète de la façon d'utiliser le script pour créer des environnements de développement et de test, consultez [Utilisation des scripts Windows PowerShell pour la publication dans des environnements de développement et de test](vs-azure-tools-publishing-using-powershell-scripts.md).

Le fichier de configuration JSON spécifie les détails de ce qui doit être déployé. Il inclut les informations que vous avez spécifiées lorsque vous avez créé le projet, comme le nom et le nom d'utilisateur pour le site web. Il inclut également la base de données à configurer, le cas échéant. Le code suivant montre un exemple de fichier de configuration JSON :

```json
{
    "environmentSettings": {
        "webSite": {
            "name": "WebApplication10554",
            "location": "West US"
        },
        "databases": [
            {
                "connectionStringName": "DefaultConnection",
                "databaseName": "WebApplication10554_db",
                "serverName": "iss00brc88",
                "user": "sqluser2",
                "password": "",
                "edition": "",
                "size": "",
                "collation": "",
                "location": "West US"
            }
        ]
    }
}
```

Vous pouvez modifier le fichier de configuration JSON pour modifier ce qui est déployé. Une section de site web est requise, mais la section de la base de données est facultative.

## <a name="next-steps"></a>Étapes suivantes
Pour plus d’informations, voir [Publish-WebApplicationVM (script Windows PowerShell)](vs-azure-tools-publish-webapplicationvm.md).
