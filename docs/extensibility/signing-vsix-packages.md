---
title: Signature des packages VSIX | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- signature
- signing
- authenticode
- vsix
- packages
ms.assetid: e34cfc2c-361c-44f8-9cfe-9f2be229d248
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 17179c35496fc19322c5bb951f4d04bc28e5d7bc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80700090"
---
# <a name="signing-vsix-packages"></a>Signature de packages VSIX
Les assemblys d’extension n’ont pas besoin d’être signés pour pouvoir s’exécuter dans Visual Studio, mais il est conseillé de le faire.

 Si vous souhaitez sécuriser votre extension et vérifier qu’elle n’a pas été falsifiée, vous pouvez ajouter une signature numérique à un package VSIX. Lorsqu’un VSIX est signé, le programme d’installation VSIX affiche un message indiquant qu’il est signé, ainsi que des informations supplémentaires sur la signature elle-même. Si le contenu de l’extension VSIX a été modifié et que le VSIX n’a pas été signé à nouveau, le programme d’installation VSIX indique que la signature n’est pas valide. L’installation n’est pas arrêtée, mais l’utilisateur reçoit un avertissement.

> [!IMPORTANT]
> À compter de Visual Studio 2015, les packages VSIX signés à l’aide de tout autre que le chiffrement SHA256 seront identifiés comme ayant une signature non valide. L’installation de VSIX n’est pas bloquée, mais l’utilisateur reçoit un avertissement.

## <a name="signing-a-vsix-with-vsixsigntool"></a>Signature d’un VSIX avec VSIXSignTool
 Un outil de signature de chiffrement SHA256 est disponible à partir de [VisualStudioExtensibility](https://www.nuget.org/profiles/VisualStudioExtensibility) sur NuGet.org sur [VsixSignTool](https://www.nuget.org/packages/Microsoft.VSSDK.Vsixsigntool).

#### <a name="to-use-the-vsixsigntool"></a>Pour utiliser VSIXSignTool

1. Ajoutez votre extension VSIX à un projet.

2. Cliquez avec le bouton droit sur le nœud du projet dans Explorateur de solutions, en sélectionnant **ajouter &#124; gérer les packages NuGet**.  Pour plus d’informations sur NuGet et l’ajout de packages NuGet, consultez la [documentation NuGet](/NuGet) et les rubriques de l' [interface utilisateur du gestionnaire de package](/NuGet/Tools/Package-Manager-UI) .

3. Recherchez VSIXSignTool à partir de VisualStudioExtensibility et installez le package NuGet.

4. Vous pouvez maintenant exécuter le VSIXSignTool à partir de l’emplacement des packages locaux du projet. Consultez l’aide de la ligne de commande de l’outil pour votre scénario de signature (VSIXSignTool.exe/ ?).

   Par exemple, pour vous connecter avec un fichier de certificat protégé par mot de passe :

   VSIXSignTool.exe la signature/f \<certfile> /p \<password>\<VSIXfile>

## <a name="see-also"></a>Voir aussi
- [Publication d’extensions Visual Studio](../extensibility/shipping-visual-studio-extensions.md)
