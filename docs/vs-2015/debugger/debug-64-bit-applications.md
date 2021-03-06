---
title: Déboguer des applications 64 bits | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], 64-bit
- 64-bit debugging
ms.assetid: db648e5f-6375-4e2d-aa98-eb7261958927
caps.latest.revision: 38
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c0eaa719bb3eeca2eb3dfe558184699ccca42819
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "86387198"
---
# <a name="debug-64-bit-applications"></a>Déboguer des applications 64 bits
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la version la plus récente de cette rubrique dans [Déboguer des Applications 64 bits](/visualstudio/debugger/debug-64-bit-applications) .  
  
Vous pouvez déboguer une application 64 bits qui s'exécute sur l'ordinateur local ou sur un ordinateur distant.  
  
 Pour déboguer une application 64 bits qui s’exécute sur un ordinateur distant, consultez [Remote Debugging](../debugger/remote-debugging.md).  
  
 Pour déboguer des applications 64 bits localement, Visual Studio utilise un processus de travail 64 bits (msvsmon.exe) pour effectuer les opérations de bas niveau qui ne peuvent pas être réalisées à l’intérieur du processus Visual Studio 32 bits.  
  
 Le débogage en mode mixte n’est pas pris en charge pour les processus 64 bits qui utilisent .NET Framework version 3.5 ou antérieure.  
  
## <a name="debug-a-64-bit-application"></a>Déboguer une application 64 bits  
 Pour essayer de déboguer une application 64 bits :  
  
1. Créez une solution Visual Studio, par exemple une application console C#.  
  
2. Définissez une configuration 64 bits à l’aide du Gestionnaire de configurations. Pour plus d'informations, consultez [How to: Configure Projects to Target Platforms](../ide/how-to-configure-projects-to-target-platforms.md).  
  
3. À ce stade, la version 64 bits du débogueur distant (msvsmon.exe) démarre. Le débogueur s’exécute tant que la solution avec la configuration 64 bits est ouverte.  
  
4. Démarrez le débogage. Vous devez avoir la même expérience qu’avec une configuration 32 bits. Si vous obtenez des erreurs, consultez la section de résolution des problèmes ci-dessous.  
  
## <a name="troubleshooting-64-bit-debugging"></a>Résolution des problèmes de débogage 64 bits  
 L’erreur suivante peut s’afficher : « Une opération de débogage 64 bits prend plus de temps que prévu ». Dans ce cas, Visual Studio a envoyé une demande à la version 64 bits de msvsmon.exe et l’obtention du résultat de cette demande a pris beaucoup de temps.  
  
 Deux causes principales peuvent provoquer cette erreur :  
  
- Un logiciel de sécurité réseau installé sur votre ordinateur altère la fiabilité de la pile de mise en réseau, et il a ignoré des paquets qui passent sur localhost. Essayez de désactiver tous les logiciels de sécurité réseau et voyez si le problème est résolu. Si tel est le cas, signalez à votre fournisseur de logiciels de sécurité réseau que le logiciel interfère avec le trafic de localhost.  
  
- Vous rencontrez un problème où Visual Studio cesse de répondre ou d’autres problèmes de performances. Si le problème se produit régulièrement, vous pouvez collecter les dumps de Visual Studio (devenv.exe) et le processus de travail (msvsmon.exe), puis les envoyer à Microsoft. 
  
## <a name="see-also"></a>Voir aussi  
 [Applications 64 bits](https://msdn.microsoft.com/library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)   
 [Configuration des programmes pour 64 bits](https://msdn.microsoft.com/library/cb99f72b-8c74-48f4-846a-8921b37b97e9)   
 [Prise en charge de l’IDE Visual Studio 64 bits](../ide/visual-studio-ide-64-bit-support.md)   
 [Utilisation des fichiers dump](../debugger/using-dump-files.md)   
 [Débogage à distance](../debugger/remote-debugging.md)
