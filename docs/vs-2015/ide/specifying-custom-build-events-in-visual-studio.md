---
title: Spécification d’événements de build personnalisés
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- build events, customizing
ms.assetid: 69e935a5-e208-4bcd-865c-3e5f9b047ca8
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: fabbd4dc42ac4f66c7f53b639c6e7ed1f432878c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72667124"
---
# <a name="specifying-custom-build-events-in-visual-studio"></a>Spécification d'événements de build personnalisés dans Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

En spécifiant un événement de build personnalisé, vous pouvez automatiquement exécuter des commandes avant le démarrage d'une build ou quand elle est terminée. Par exemple, vous pouvez exécuter un fichier .bat avant qu'une build ne démarre ou copier de nouveaux fichiers dans un dossier une fois la build terminée. Les événements de build ne s'exécutent que si la build atteint ces étapes du processus de génération.

 Pour obtenir des informations spécifiques sur le langage de programmation que vous utilisez, consultez les rubriques suivantes :

- Visual Basic--[Comment : spécifier des événements de build (Visual Basic)](../ide/how-to-specify-build-events-visual-basic.md).

- Visual C# et F#--[Guide pratique pour spécifier des événements de build (C#)](../ide/how-to-specify-build-events-csharp.md).

- Visual C++--[Spécifications d’événements de build](https://msdn.microsoft.com/library/788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc).

## <a name="syntax"></a>Syntaxe
 Les événements de build suivent la même syntaxe que les commandes DOS, mais vous pouvez utiliser des macros pour créer plus facilement des événements de build. Pour obtenir la liste des macros disponibles, consultez boîte de [dialogue ligne de commande de l’événement pré-build/après génération](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).

 Pour de meilleurs résultats, suivez ces conseils de mise en forme :

- Ajouter une instruction `call` avant tous les événements de build qui exécutent des fichiers .bat.

     Exemple : `call C:\MyFile.bat`

     Exemple : `call C:\MyFile.bat call C:\MyFile2.bat`

- Placez les chemins d'accès de fichier entre guillemets.

     Exemple (pour [!INCLUDE[win8](../includes/win8-md.md)]) : "%ProgramFiles(x86)%\Microsoft SDKs\Windows\v8.0A\Bin\NETFX 4.0 Tools\gacutil.exe" -if "$(TargetPath)"

- Séparez les commandes à l'aide de sauts de ligne.

- Incluez des caractères génériques si nécessaire.

     Exemple : `for %I in (*.txt *.doc *.html) do copy %I c:\` *mydirectory*`\`

    > [!NOTE]
    > `%I` dans le code ci-dessus doit être `%%I` dans les scripts de commandes.

## <a name="see-also"></a>Voir aussi
 [Compilation et génération](../ide/compiling-and-building-in-visual-studio.md) [boîte de dialogue ligne de commande/Post-build événement pré-build](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md) [caractères spéciaux MSBuild](../msbuild/msbuild-special-characters.md) [procédure pas à pas : Génération d’une application](../ide/walkthrough-building-an-application.md)
