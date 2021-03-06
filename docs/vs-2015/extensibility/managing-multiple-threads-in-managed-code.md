---
title: Gestion de plusieurs threads dans du code managé | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 59730063-cc29-4dae-baff-2234ad8d0c8f
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 296ef23bc512a86917920b3c3d5fbb5ec203a21e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "86387016"
---
# <a name="managing-multiple-threads-in-managed-code"></a>Gérer plusieurs threads dans le code managé
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Si vous avez une extension de VSPackage managée qui appelle des méthodes asynchrones ou a des opérations qui s’exécutent sur des threads autres que le thread d’interface utilisateur de Visual Studio, vous devez suivre les instructions indiquées ci-dessous. Vous pouvez maintenir la réactivité du thread d’interface utilisateur, car il n’a pas besoin d’attendre la fin du travail sur un autre thread. Vous pouvez rendre votre code plus efficace, car vous n’avez pas de threads supplémentaires qui occupent de l’espace de pile et vous pouvez le rendre plus fiable et plus facile à déboguer, car vous évitez les interblocages et l’absence de réponse.  
  
 En général, vous pouvez passer du thread d’interface utilisateur à un thread différent, ou vice versa. Lorsque la méthode retourne, le thread actuel est le thread à partir duquel il a été appelé à l’origine.  
  
> [!IMPORTANT]
> Les instructions suivantes utilisent les API de l' <xref:Microsoft.VisualStudio.Threading> espace de noms, en particulier la <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory> classe. Les API de cet espace de noms sont nouvelles dans [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)] . Vous pouvez obtenir une instance de <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory> à partir de la <xref:Microsoft.VisualStudio.Shell.ThreadHelper> propriété `ThreadHelper.JoinableTaskFactory` .  
  
## <a name="switching-from-the-ui-thread-to-a-background-thread"></a>Passage du thread d’interface utilisateur à un thread d’arrière-plan  
  
1. Si vous êtes sur le thread d’interface utilisateur et que vous souhaitez effectuer un travail asynchrone sur un thread d’arrière-plan, utilisez Task. Run () :  
  
    ```csharp  
    await Task.Run(async delegate{  
        // Now you’re on a separate thread.  
    });  
    // Now you’re back on the UI thread.  
  
    ```  
  
2. Si vous êtes sur le thread d’interface utilisateur et que vous souhaitez bloquer de façon synchrone pendant que vous effectuez un travail sur un thread d’arrière-plan, utilisez la <xref:System.Threading.Tasks.TaskScheduler> propriété `TaskScheduler.Default` à l’intérieur de <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A> :  
  
    ```csharp  
    // using Microsoft.VisualStudio.Threading;  
    ThreadHelper.JoinableTaskFactory.Run(async delegate {  
        await TaskScheduler.Default;  
        // You're now on a separate thread.  
        DoSomethingSynchronous();  
        await OrSomethingAsynchronous();  
    });  
    ```  
  
## <a name="switching-from-a-background-thread-to-the-ui-thread"></a>Basculement d’un thread d’arrière-plan vers le thread d’interface utilisateur  
  
1. Si vous êtes sur un thread d’arrière-plan et que vous souhaitez effectuer une opération sur le thread d’interface utilisateur, utilisez <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> :  
  
    ```csharp  
    // Switch to main thread  
    await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
    ```  
  
     Vous pouvez utiliser la <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> méthode pour basculer vers le thread d’interface utilisateur. Cette méthode publie un message dans le thread d’interface utilisateur avec la continuation de la méthode asynchrone actuelle, et communique également avec le reste de l’infrastructure de thread pour définir la priorité correcte et éviter les interblocages.  
  
     Si votre méthode de thread d’arrière-plan n’est pas asynchrone et que vous ne pouvez pas la rendre asynchrone, vous pouvez toujours utiliser la `await` syntaxe pour basculer vers le thread d’interface utilisateur en encapsulant votre travail avec <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A> , comme dans cet exemple :  
  
    ```csharp  
    ThreadHelper.JoinableTaskFactory.Run(async delegate {  
        // Switch to main thread  
        await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
        // Do your work on the main thread here.  
    });  
    ```
