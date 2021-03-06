---
title: 'Comment : utiliser AsyncPackage pour charger des VSPackages en arrière-plan | Microsoft Docs'
ms.date: 11/15/2016
ms.topic: conceptual
ms.assetid: dedf0173-197e-4258-ae5a-807eb3abc952
caps.latest.revision: 9
ms.author: gregvanl
ms.openlocfilehash: f59838913ed3f9bc6679336393f6db9181291e3d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "68204027"
---
# <a name="how-to-use-asyncpackage-to-load-vspackages-in-the-background"></a>Guide pratique pour utiliser AsyncPackage pour charger des VSPackages en arrière-plan
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Le chargement et l’initialisation d’un package VS peuvent entraîner des e/s disque. Si ces e/s se produisent sur le thread d’interface utilisateur, cela peut entraîner des problèmes de réactivité. Pour résoudre ce cas, Visual Studio 2015 a introduit la  <xref:Microsoft.VisualStudio.Shell.AsyncPackage> classe qui permet le chargement des packages sur un thread d’arrière-plan.  
  
## <a name="creating-an-asyncpackage"></a>Création d’un AsyncPackage  
 Vous pouvez commencer par créer un projet VSIX (**fichier/nouveau/projet/Visual C#/extensibilité/projet VSIX**) et ajouter un VSPackage au projet (cliquez avec le bouton droit sur le projet, puis sur **Ajouter/nouvel élément/élément C#/extensibilité/package Visual Studio**). Vous pouvez ensuite créer vos services et ajouter ces services à votre package.  
  
1. Dérivez le package de <xref:Microsoft.VisualStudio.Shell.AsyncPackage> .  
  
2. Si vous fournissez des services dont l’interrogation peut entraîner le chargement de votre package :  
  
    Pour indiquer à Visual Studio que votre package est sécurisé pour le chargement en arrière-plan et pour s’abonner à ce comportement, vous <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> devez affecter à la propriété **AllowsBackgroundLoading** la valeur true dans le constructeur d’attribut.  
  
   ```csharp  
   [PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]  
  
   ```  
  
    Pour indiquer à Visual Studio qu’il est possible d’instancier votre service en toute sécurité sur un thread d’arrière-plan, vous devez affecter <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttributeBase.IsAsyncQueryable%2A> à la propriété la valeur true dans le <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> constructeur.  
  
   ```csharp  
   [ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]  
  
   ```  
  
3. Si vous effectuez un chargement via des contextes d’interface utilisateur, vous devez spécifier **PackageAutoLoadFlags. BackgroundLoad** pour <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> ou la valeur (0X2) dans les indicateurs écrits comme valeur de l’entrée de chargement automatique de votre package.  
  
   ```csharp  
   [ProvideAutoLoad(UIContextGuid, PackageAutoLoadFlags.BackgroundLoad)]  
  
   ```  
  
4. Si vous avez un travail d’initialisation asynchrone à effectuer, vous devez substituer <xref:Microsoft.VisualStudio.Shell.AsyncPackage.InitializeAsync%2A> . Supprimez la méthode **Initialize ()** fournie par le modèle VSIX. (La méthode **Initialize ()** dans **AsyncPackage** est sealed). Vous pouvez utiliser l’une des <xref:Microsoft.VisualStudio.Shell.AsyncPackage.AddService%2A> méthodes pour ajouter des services asynchrones à votre package.  
  
    Remarque : pour appeler **base.InitializeAsync ()**, vous pouvez modifier votre code source pour effectuer les opérations suivantes :  
  
   ```csharp  
   await base.InitializeAsync(cancellationToken, progress);  
   ```  
  
5. Vous devez veiller à ne pas créer de RPC (supprimer l’appel de procédure) à partir de votre code d’initialisation asynchrone (dans **InitializeAsync**). Cela peut se produire lorsque vous appelez <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> directement ou indirectement.  Lorsque les chargements de synchronisation sont requis, le thread d’interface utilisateur se bloque à l’aide de <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory> . Le modèle de blocage par défaut désactive les RPC. Cela signifie que si vous tentez d’utiliser un RPC à partir de vos tâches Async, vous interbloquerz si le thread d’interface utilisateur attend le chargement de votre package. L’alternative générale consiste à marshaler votre code vers le thread d’interface utilisateur, si **Joinable Task Factory**nécessaire, à l’aide d’un <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> autre mécanisme qui n’utilise pas d’appel de procédure distante de la fabrique de tâches.  N’utilisez pas **ThreadHelper. Generic. Invoke** ou bloquez généralement le thread appelant qui attend d’accéder au thread d’interface utilisateur.  
  
    Remarque : vous devez éviter d’utiliser **GetService** ou **QueryService** dans votre méthode **InitializeAsync** . Si vous devez les utiliser, vous devrez d’abord basculer vers le thread d’interface utilisateur. L’alternative consiste à utiliser <xref:Microsoft.VisualStudio.Shell.AsyncServiceProvider.GetServiceAsync%2A> à partir de votre **AsyncPackage** (en le castant en <xref:Microsoft.VisualStudio.Shell.Interop.IAsyncServiceProvider> ).  
  
   C# : créer un AsyncPackage :  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]       
[ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]   
public sealed class TestPackage : AsyncPackage   
{   
    protected override Task InitializeAsync(System.Threading.CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)   
    {               
        this.AddService(typeof(SMyTestService), CreateService, true);   
        return Task.FromResult<object>(null);   
    }   
}  
```  
  
## <a name="convert-an-existing-vspackage-to-asyncpackage"></a>Convertir un VSPackage existant en AsyncPackage  
 La majorité du travail est identique à la création d’un nouveau **AsyncPackage**. Vous devez suivre les étapes 1 à 5 ci-dessus. Vous devez également prendre des précautions supplémentaires sur les éléments suivants :  
  
1. N’oubliez pas de supprimer la substitution **d’initialisation** que vous aviez dans votre package.  
  
2. Éviter les interblocages : il peut y avoir des RPC masqués dans votre code qui se produisent maintenant sur un thread d’arrière-plan. Vous devez vous assurer que si vous créez un RPC (par exemple, **GetService**), vous devez (1) basculer vers le thread principal ou (2) utiliser la version asynchrone de l’API, le cas échéant (par exemple, **GetServiceAsync**).  
  
3. Ne pas basculer entre les threads trop fréquemment. Essayez de localiser le travail qui peut se produire dans un thread d’arrière-plan. Cela réduit le temps de chargement.  
  
## <a name="querying-services-from-asyncpackage"></a>Interrogation des services à partir de AsyncPackage  
 Un **AsyncPackage** peut ou non être chargé de façon asynchrone en fonction de l’appelant. Par exemple,  
  
- Si l’appelant a appelé **GetService** ou **QueryService** (à la fois les API synchrones) ou  
  
- Si l’appelant a appelé **IVsShell :: LoadPackage** (ou **IVsShell5 :: LoadPackageWithContext**) ou  
  
- La charge est déclenchée par un contexte d’interface utilisateur, mais vous n’avez pas spécifié que le mécanisme de contexte d’interface utilisateur peut charger de manière asynchrone  
  
  votre package se chargera alors de façon synchrone.  
  
  Notez que votre package a toujours une opportunité (dans sa phase d’initialisation asynchrone) de faire fonctionner le thread d’interface utilisateur, bien que le thread d’interface utilisateur soit bloqué pour la fin de ce travail. Si l’appelant utilise **IAsyncServiceProvider** pour interroger de manière asynchrone votre service, la charge et l’initialisation sont effectuées de façon asynchrone en supposant qu’elles ne se bloquent pas immédiatement sur l’objet de tâche résultant.  
  
  C# : Comment interroger le service de façon asynchrone :  
  
```csharp  
using Microsoft.VisualStudio.Shell;   
using Microsoft.VisualStudio.Shell.Interop;   
  
IAsyncServiceProvider asyncServiceProvider = Package.GetService(typeof(SAsyncServiceProvider)) as IAsyncServiceProvider;   
IMyTestService testService = await ayncServiceProvider.GetServiceAsync(typeof(SMyTestService)) as IMyTestService;  
```
