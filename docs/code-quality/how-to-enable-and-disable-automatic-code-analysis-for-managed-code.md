---
title: Désactiver l’analyse du code hérité
ms.date: 10/04/2019
ms.topic: how-to
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: eb4422a12620d7650b4fe150313b10fe59835064
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "88801020"
---
# <a name="how-to-enable-and-disable-binary-code-analysis-for-managed-code"></a>Comment : activer et désactiver l’analyse du code binaire pour le code managé

Vous pouvez configurer l’analyse du code hérité (analyse binaire) pour qu’elle s’exécute après chaque génération d’un projet de code managé. Vous pouvez également avoir des paramètres différents pour chaque configuration de build, par exemple, Debug et Release.

> [!NOTE]
> L’analyse héritée n’est pas disponible pour les nouveaux types de projets, tels que .NET Core et les applications .NET Standard. Ces projets utilisent des [analyseurs de code basés sur .NET Compiler Platform](roslyn-analyzers-overview.md) pour analyser le code, en direct et au moment de la génération. Pour plus d’informations sur la désactivation de l’analyse du code source dans ces projets, consultez [Comment désactiver l’analyse du code source](disable-code-analysis.md).

Pour activer ou désactiver l’analyse du code hérité :

1. Dans **Explorateur de solutions**, sélectionnez le projet et maintenez-le enfoncé (ou cliquez dessus avec le bouton droit), puis sélectionnez **Propriétés**.

2. Dans la boîte de dialogue Propriétés du projet, accédez à l’onglet **analyse du code** .

3. Spécifiez le type de build dans la **configuration** et la plateforme cible dans la **plateforme**. (Projets standard Non-.NET Core/. NET uniquement.)

::: moniker range="vs-2017"

4. Pour activer ou désactiver l’analyse du code automatique, activez ou désactivez la case à cocher **activer l’analyse du code sur la build** .

::: moniker-end

::: moniker range=">=vs-2019"

4. Pour activer ou désactiver l’analyse du code automatique, activez ou désactivez la case à cocher **exécuter lors** de la génération dans la section **analyseurs binaires** .

   ![Exécuter l’analyse du code binaire sur l’option de génération dans Visual Studio](media/run-on-build-binary-analyzers.png)

::: moniker-end

> [!NOTE]
> La désactivation de l’analyse du code binaire sur la build n’affecte pas les [analyseurs de code basés sur .NET Compiler Platform](roslyn-analyzers-overview.md), qui s’exécutent toujours au moment de la génération si vous les avez installés en tant que package NuGet. Pour plus d’informations sur la désactivation de l’analyse à partir de ces analyseurs, consultez [Comment désactiver l’analyse du code source](disable-code-analysis.md).
