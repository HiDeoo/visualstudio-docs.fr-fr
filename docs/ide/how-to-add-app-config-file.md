---
title: Guide pratique pour ajouter un fichier app.config à un projet
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
helpviewer_keywords:
- app.config files, adding to C# projects
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 48e6516b48b524c3da4d80bc5171608ac1aea03d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654264"
---
# <a name="how-to-add-an-application-configuration-file-to-a-c-project"></a>Guide pratique pour ajouter un fichier de configuration d’application à un projet C#

En ajoutant un fichier de configuration d’application (un fichier *app.config*) à un projet C#, vous pouvez personnaliser la façon dont le CLR (Common Language Runtime) localise et charge les fichiers d’assembly. Pour plus d’informations sur les fichiers de configuration d’application, consultez [Méthode de localisation des assemblys par le runtime (.NET Framework)](/dotnet/framework/deployment/how-the-runtime-locates-assemblies).

> [!NOTE]
> Les applications UWP ne contiennent pas de fichier *app.config*.

Quand vous générez votre projet, l’environnement de développement copie automatiquement votre fichier *app.config*, modifie le nom de fichier de la copie pour qu’il corresponde à votre fichier exécutable, puis déplace la copie dans le répertoire **bin**.

## <a name="to-add-an-application-configuration-file-to-a-c-project"></a>Pour ajouter un fichier de configuration d’application à un projet C#

1. Dans la barre de menus, choisissez **Projet** > **Ajouter un nouvel élément**.

     La boîte de dialogue **Ajouter un nouvel élément** s’affiche.

1. Développez **Installé** > **Éléments Visual C#** , puis choisissez le modèle **Fichier de configuration de l’application**.

1. Dans la zone de texte **Nom**, entrez un nom, puis choisissez le bouton **Ajouter**.

     Un fichier nommé *app.config* est ajouté à votre projet.

## <a name="see-also"></a>Voir aussi

- [Gérer les paramètres d’application (.NET)](../ide/managing-application-settings-dotnet.md)
- [Schéma des fichiers de configuration (.NET Framework)](/dotnet/framework/configure-apps/file-schema/index)
- [Configurer les applications (.NET Framework)](/dotnet/framework/configure-apps/index)