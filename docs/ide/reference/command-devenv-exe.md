---
title: -Command (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Devenv, /command switch
- /command Devenv switch
ms.assetid: 13c20cd6-f09d-400a-8b7b-ecc266a32cef
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d6eff1311ac0ae2232d04d8e3fb5c86d711ba179
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53838344"
---
# <a name="command-devenvexe"></a>/Command (devenv.exe)
Exécute la commande spécifiée après le lancement de l’environnement de développement intégré (IDE) [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="syntax"></a>Syntaxe

```cmd
devenv /command CommandName
```

## <a name="arguments"></a>Arguments
 `CommandName` Obligatoire. Nom complet d’une commande [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ou de son alias, entouré de guillemets doubles. Pour plus d’informations sur la syntaxe des commandes et des alias, consultez [Commandes Visual Studio](../../ide/reference/visual-studio-commands.md).

## <a name="remarks"></a>Notes
 Une fois le démarrage terminé, l’IDE exécute la commande nommée. Si vous utilisez ce commutateur, l’IDE n’affiche pas la page de démarrage de [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] lors du démarrage.

 Si un complément expose une commande, vous pouvez utiliser ce commutateur pour lancer le complément à partir de la ligne de commande. Pour plus d'informations, voir [Procédure : Contrôler des compléments avec le Gestionnaire de compléments](https://msdn.microsoft.com/Library/4f60444a-cb48-4cdb-8df4-941f6419aeeb).

## <a name="example"></a>Exemple
 Cet exemple lance [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] et exécute automatiquement la macro Open Favorite Files.

```cmd
devenv /command "Macros.MyMacros.Module1.OpenFavoriteFiles"
```

## <a name="see-also"></a>Voir aussi

- [Commutateurs de ligne de commande Devenv](../../ide/reference/devenv-command-line-switches.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)