---
title: -Clean (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- builds [Team System], cleaning files
- clean Devenv switch
- /clean Devenv switch
- Devenv, /clean switch
ms.assetid: 79929dfd-22c9-4cec-a0d0-a16f15b8f7e4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 051485646b7ff19ddae40518215c410d05fa4849
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53906889"
---
# <a name="clean-devenvexe"></a>/Clean (devenv.exe)
Nettoie tous les fichiers et répertoires de sortie intermédiaires.

## <a name="syntax"></a>Syntaxe

```
devenv FileName /Clean [ /project projectnameorfile [/projectconfig name ] ]
```

## <a name="arguments"></a>Arguments
 `FileName`

 Obligatoire. Chemin complet et nom du fichier solution ou fichier projet.

 /project `ProjName`

 Optionnel. Chemin et nom d’un fichier projet dans la solution. Vous pouvez entrer un chemin relatif du dossier `SolutionName` vers le fichier projet, le nom d’affichage du projet ou encore le chemin complet et le nom du fichier projet.

 /projectconfig `ProjConfigName`

 Optionnel. Nom d’une configuration de build de projet à utiliser lors du nettoyage du `/project` nommé.

## <a name="remarks"></a>Notes
 Ce commutateur exécute la même fonction que la commande de menu **Nettoyer la solution** dans l’environnement de développement intégré (IDE).

 Placez entre guillemets doubles les chaînes contenant des espaces.

 Les informations résumées pour les nettoyages et les builds, notamment les erreurs, peuvent être affichées dans la fenêtre **Commande**, ou dans tout fichier journal spécifié avec le commutateur `/out`.

## <a name="example"></a>Exemple
 Le premier exemple nettoie la solution `MySolution` à l’aide de la configuration par défaut spécifiée dans le fichier solution.

 Le deuxième exemple nettoie le projet `CSharpConsoleApp` en utilisant la configuration de build de projet `Debug` présente dans la configuration de solution `Debug` de `MySolution`.

```
Devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /Clean

devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /Clean /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig "Debug"
```

## <a name="see-also"></a>Voir aussi

- [Commutateurs de ligne de commande Devenv](../../ide/reference/devenv-command-line-switches.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)