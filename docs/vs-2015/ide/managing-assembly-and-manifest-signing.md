---
title: Gestion d’assembly et signature de manifeste | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- manifests [Visual Studio]
- signing manifests [Visual Studio]
- application manifests [Visual Studio]
- assemblies [Visual Studio], signing
ms.assetid: 6c1ef36b-25f7-4ad0-b29a-51801b7a5420
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 63a2e1b98baa61ef0a83c1de65653dd2e57a8b2c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54755462"
---
# <a name="managing-assembly-and-manifest-signing"></a>Gestion d'assembly et signature de manifeste
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La signature avec un nom fort fournit à un composant logiciel une identité globalement unique. L’utilisation de noms forts garantit que l’assembly ne peut pas être usurpé et que les dépendances de composants et les instructions de configuration correspondent aux composant et version de composant appropriés.  
  
 Un nom fort est constitué de l’identité de l’assembly (simple nom textuel, numéro de version et informations de culture), ainsi que d’un jeton de clé publique et d’une signature numérique.  
  
 Pour plus d’informations sur la signature d’assemblys dans les projets Visual Basic et C#, consultez [Création et utilisation d’assemblys avec nom fort](http://msdn.microsoft.com/library/ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9).  
  
 Pour plus d’informations sur la signature d’assemblys dans les projets Visual C++, consultez [Assemblys de nom fort (signature d’assembly) (C++/CLI)](http://msdn.microsoft.com/library/c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc).  
  
## <a name="asset-types-and-signing"></a>Types de composants et signature  
 Vous pouvez signer les manifestes d’application et les assemblys .NET. Notamment :  
  
- Exécutables (.exe)  
  
- Manifestes d’application (.exe.manifest)  
  
- Manifestes de déploiement (.application)  
  
- Assemblys de composants partagés (.dll)  
  
  Vous devez signer les types de composants suivants :  
  
1. Assemblys, si vous souhaitez les déployer dans le Global Assembly Cache (GAC).  
  
2. Manifestes d’application et de déploiement [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]. Visual Studio permet la signature par défaut pour ces applications.  
  
3. Assemblys PIA (Primary Interop Assembly), qui sont utilisés pour l’interopérabilité COM. L’utilitaire TLBIMP applique des noms forts pendant la création d’un assembly PIA à partir d’une bibliothèque de types COM.  
  
   En général, vous ne devez pas signer les exécutables. Un composant de nom fort ne peut pas référencer un composant sans nom fort qui est déployé avec l’application. Visual Studio ne signe pas les exécutables d’application. En revanche, il signe le manifeste d’application, qui pointe vers l’exécutable portant un nom faible. Vous devez généralement éviter de signer les composants qui appartiennent à votre application, car la signature peut rendre les dépendances plus difficiles à gérer.  
  
## <a name="how-to-sign-an-assembly-in-visual-studio"></a>Comment signer un assembly dans Visual Studio  
 Vous signez une application ou un composant à l’aide de l’onglet **Signature** de la fenêtre des propriétés du projet (cliquez avec le bouton droit sur le nœud de projet dans l’**Explorateur de solutions** et sélectionnez **Propriétés** ou tapez **propriétés de projet** dans la fenêtre **Lancement rapide**, ou appuyez sur Alt+Entrée dans la fenêtre de l’**Explorateur de solutions**). Sélectionnez l’onglet **Signature**, puis cochez la case **Signer l’assembly**.  
  
 Spécifiez un fichier de clé. Si vous choisissez de créer un fichier de clé, notez que les fichiers de clés sont toujours créés au format .pfx. Vous avez besoin d’un nom et d’un mot de passe pour le nouveau fichier.  
  
> [!WARNING]
>  Vous devez toujours protéger votre fichier de clé avec un mot de passe pour empêcher son utilisation par un tiers. Vous pouvez également sécuriser vos clés à l’aide des fournisseurs ou des magasins de certificats.  
  
 Vous pouvez également pointer vers une clé que vous avez déjà créée. Pour plus d’informations sur la création de clés, consultez [Comment : créer une paire de clés publique/privée](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114).  
  
 Si vous avez accès uniquement à une clé publique, vous pouvez utiliser la signature différée pour reporter l’assignation de la clé. Vous activez la signature différée en cochant la case **Différer la signature uniquement**. Un projet à signature différée ne s’exécute pas, et vous ne pouvez pas le déboguer. Toutefois, vous pouvez ignorer la vérification pendant le développement à l’aide de l’option `-Vr` de l’[outil Strong Name Tool (Sn.exe)](http://msdn.microsoft.com/library/c1d2b532-1b8e-4c7a-8ac5-53b801135ec6).  
  
 Pour plus d’informations sur la signature des manifestes, consultez [Guide pratique pour signer des manifestes d’application et de déploiement](../ide/how-to-sign-application-and-deployment-manifests.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Assemblys avec nom fort](http://msdn.microsoft.com/library/d4a80263-f3e0-4d81-9b61-f0cbeae3797b)   
 [Assemblys de nom fort (signature d’assembly) (C++/CLI)](http://msdn.microsoft.com/library/c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc)
