---
title: -SafeMode (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6df78ec4be1fc94951634b84a98e80dc1403a41b
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948736"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
Démarre [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] en mode sans échec, en chargeant uniquement l’environnement et les services par défaut.

## <a name="syntax"></a>Syntaxe

```cmd
devenv /SafeMode
```

## <a name="remarks"></a>Notes
 Ce commutateur empêche le chargement de tous les packages VS tiers au démarrage de [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], garantissant ainsi la stabilité de l’exécution.

## <a name="description"></a>Description
 L’exemple suivant démarre [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] en mode sans échec.

## <a name="code"></a>Code

```cmd
Devenv.exe /SafeMode
```

## <a name="see-also"></a>Voir aussi

- [Commutateurs de ligne de commande Devenv](../../ide/reference/devenv-command-line-switches.md)