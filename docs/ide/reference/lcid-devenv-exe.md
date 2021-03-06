---
title: -LCID (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- language default
- locale IDs, setting for IDE
- Devenv, /L switch
- Devenv, /LCID switch
- locale IDs
- L Devenv switch
- /L Devenv switch
- LCID devenv switch
- /LCID Devenv switch
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cabbf36adb5019543b3cfb72b0b0e56976517d2d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "77557937"
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)

Définit la langue utilisée par défaut pour le texte, la devise et d’autres valeurs de l’environnement IDE.

## <a name="syntax"></a>Syntaxe

```shell
devenv {/LCID|/L} LocaleID
```

## <a name="arguments"></a>Arguments

- *LocaleID*

  Obligatoire. Identificateur de paramètres régionaux (LCID) de la langue spécifiée.

## <a name="remarks"></a>Notes

Charge l’IDE et définit le langage naturel par défaut pour l’environnement. Cette modification est conservée entre les sessions, et l’IDE affiche cette modification dans la zone de langue **Outils**  >  **options**  >  **environnement**  >  **paramètres internationaux**  >  **Language** .

Si la langue spécifiée n’est pas disponible sur le système, le commutateur `/LCID` est ignoré.

Le tableau suivant indique les identificateurs LCID des langues prises en charge par Visual Studio.

|Language|LCID|
|--------------|----------|
|Chinois (simplifié)|2052|
|Chinois (traditionnel)|1028|
|Tchèque|1029|
|Anglais|1033|
|Français|1036|
|Allemand|1031|
|Italien|1040|
|Japonais|1041|
|Coréen|1042|
|Polonais|1045|
|Portugais (Brésil)|1046|
|Russe|1049|
|Espagnol|3082|
|Turc|1055

## <a name="example"></a>Exemple

Cet exemple charge l’IDE avec des chaînes de ressources en anglais.

```shell
devenv /LCID 1033
```

## <a name="see-also"></a>Voir aussi

- [Commutateurs de ligne de commande Devenv](../../ide/reference/devenv-command-line-switches.md)
- [Paramètres internationaux, Environnement, boîte de dialogue Options](../../ide/reference/international-settings-environment-options-dialog-box.md)
- [Personnalisation des dispositions de fenêtres](../../ide/customizing-window-layouts-in-visual-studio.md)
