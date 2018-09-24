---
title: Bien démarrer avec ASP.NET Core
description: Cet article décrit comment démarrer avec ASP.NET dans Visual Studio pour Mac. Il couvre notamment l’installation et la création d’un projet.
author: conceptdev
ms.author: crdun
ms.date: 07/13/2017
ms.assetid: 6E8B0C90-33D6-4546-8207-CE0787584565
ms.openlocfilehash: 231994db8192f5c44919efcf5823e4e57342f2b1
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2018
ms.locfileid: "43224086"
---
# <a name="getting-started-with-aspnet-core"></a>Bien démarrer avec ASP.NET Core

 Visual Studio pour Mac facilite le développement du service de votre application avec sa prise en charge pour la plateforme de développement web ASP.NET Core la plus récente. ASP.NET Core s’exécute sur .NET Core, qui est l’évolution la plus récente du .NET Framework et du runtime. Il a été optimisé pour accélérer les performances, conçu pour des tailles d’installation réduites et réinventé pour s’exécuter sur Linux et macOS, ainsi que sur Windows.

## <a name="installing-net-core"></a>Installation de .NET Core

.NET Core 1.1 est installé automatiquement quand vous installez Visual Studio pour Mac.

## <a name="creating-an-aspnet-core-app-in-visual-studio-for-mac"></a>Création d’une application ASP.NET Core dans Visual Studio pour Mac

Ouvrez Visual Studio pour Mac. Sur l’écran d’accueil, sélectionnez **Nouveau projet...**

![Boîte de dialogue Nouveau projet](media/asp-net-core-image1.png)

La boîte de dialogue Nouveau projet s’affiche et vous permet de sélectionner un modèle pour créer votre application.

Il existe un grand nombre de projets qui vous offrent un modèle prédéfini pour commencer à créer votre application ASP.NET Core. Ces équivalents sont :

- **.NET Core > Application web vide ASP.NET Core**
- **.NET Core > Application web ASP.NET Core**
- **.NET Core > API web ASP.NET Core**
- **Multiplateforme > Application > Application connectée**

![Options des projets ASP.NET](media/asp-net-core-image11.png)

Sélectionnez **Application web vide ASP.NET Core** et appuyez sur **Suivant**. Donnez un nom au projet et appuyez sur **Créer**. Une application ASP.NET Core est créée et devrait ressembler à l’image ci-dessous :

![Vue Nouveau projet vide ASP.NET Core](media/asp-net-core-image4.png)

L’application web vide ASP.NET Core crée une application web avec deux fichiers par défaut : **Program.cs** et **Startup.cs**, qui sont décrits ci-dessous. Elle crée également un dossier de dépendances, qui contient les dépendances du package NuGet de votre projet, comme ASP.NET Core, le framework .NET Core et les cibles MSBuild qui génèrent le projet :

![Panneau Solution affichant les dépendances](media/asp-net-core-image12.png)

### <a name="programcs"></a>Program.cs

Ouvrez et examinez le fichier **Program.cs** de votre projet. Notez que deux choses se produisent dans la méthode `Main`, qui est l’entrée de votre application :

```csharp
public static void Main(string[] args)
{
    var host = new WebHostBuilder()
        .UseKestrel()
        .UseContentRoot(Directory.GetCurrentDirectory())
        .UseIISIntegration()
        .UseStartup<Startup>()
        .Build();

    host.Run();
}
```
Une application ASP.NET Core crée un serveur web dans sa méthode main en configurant et en lançant un hôte via une instance de [ `WebHostBuilder` ](https://docs.microsoft.com/aspnet/core/fundamentals/hosting). Ce générateur fournit des méthodes pour permettre la configuration de l’hôte. Dans le modèle d’application, les configurations suivantes sont utilisées :

 * `UseKestrel` : spécifie que le serveur Kestrel est utilisé par l’application
 * `UseContentRoot(Directory.GetCurrentDirectory())` : utilise le dossier racine du projet web comme racine du contenu de l’application quand l’application est démarrée à partir de ce dossier
 * `.UseIISIntegration()` : spécifie que l’application doit fonctionner avec IIS. Pour utiliser IIS avec ASP.NET Core, `UseKestrel` et `UseIISIntegration` doivent tous deux être spécifiés.
 * `.UseStartup<Startup>()` : spécifie la classe de démarrage.

 Les méthodes Build et Run génèrent l’hôte IWebHost qui hébergera l’application et la démarrera en écoutant les requêtes HTTP entrantes.

### <a name="startupcs"></a>Startup.cs

La classe Startup de votre application est spécifiée dans la méthode `UseStartup()` sur `WebHostBuilder`. C’est dans cette classe que vous spécifiez le pipeline de gestion des demandes et où vous configurez les services.

Ouvrez et examinez le fichier **Startup.cs** de votre projet :

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
    {
        loggerFactory.AddConsole();

        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }

        app.Run(async (context) =>
        {
            await context.Response.WriteAsync("Hello World!");
        });
    }
}
```

Cette classe Startup doit toujours respecter les règles suivantes :

 - Elle doit toujours être publique.
 - Elle doit contenir les deux méthodes publiques `ConfigureServices` et `Configure`.

La méthode `ConfigureServices` définit les services qui seront utilisés par votre application.

La méthode `Configure` vous permet de composer votre pipeline de demandes à l’aide de [middleware](https://docs.microsoft.com/aspnet/core/fundamentals/middleware). Il s’agit des composants utilisés au sein d’un pipeline d’application ASP.NET pour gérer les demandes et les réponses. Le pipeline HTTP se compose d’un certain nombre de délégués de demande, appelés en séquence. Chaque délégué peut choisir de gérer la demande proprement dite ou de la passer au délégué suivant.

Vous pouvez configurer des délégués en utilisant les méthodes `Run`, `Map` et `Use` sur `IApplicationBuilder`, mais la méthode `Run` n’appelle jamais le délégué suivant et doit toujours être utilisée à la fin de votre pipeline.

La méthode `Configure` du modèle prédéfini est conçue pour effectuer certaines opérations. Elle configure d’abord une page de gestion des exceptions à utiliser pendant le développement. Ensuite, elle envoie une réponse à la page web qui fait la demande avec un simple « Hello World ».

Ce projet simple « Hello World » peut maintenant s’exécuter sans ajouter de code supplémentaire. Pour exécuter l’application et la voir dans votre navigateur, cliquez sur le bouton (triangulaire) Lecture dans la barre d’outils :

![Exécuter une application](media/asp-net-core-image5.png)

Visual Studio pour Mac utilise un port aléatoire pour lancer votre projet web. Pour trouver de quel port il s’agit, ouvrez la sortie de l’application, qui se trouve sous **Afficher > Panneaux**. Vous devez trouver une sortie similaire à celle-ci :

![Sortie de l’application montrant le port qui est à l’écoute](media/asp-net-core-image6.png)

Ouvrez le navigateur de votre choix et entrez `http://localhost:5000/`, en remplaçant `5000` par le port indiqué par Visual Studio dans la sortie de l’application. Vous devez normalement voir le texte `Hello World!` :

![navigateur affichant le texte](media/asp-net-core-image7.png)

## <a name="adding-a-controller"></a>Ajour d’un contrôleur

Les applications ASP.NET Core utilisent le modèle de conception MVC (Modèle-Vue-Contrôleur) pour fournir une séparation logique entre les responsabilités de chaque partie de l’application. Le modèle MVC est constitué des éléments suivants :

- **Modèle** : classe qui représente les données de l’application.
- **Vue** : affiche l’interface utilisateur de l’application (qui est souvent constituée des données du modèle).
- **Contrôleur** : classe qui gère les demandes du navigateur et qui répond aux entrées et aux interactions de l’utilisateur.

Pour plus d’informations sur l’utilisation du modèle MVC, consultez le guide [Vue d’ensemble du modèle MVC d’ASP.NET Core](https://docs.microsoft.com/aspnet/core/mvc/overview).

Pour ajouter un contrôleur, procédez comme suit :

1. Cliquez avec le bouton droit sur le nom du projet et sélectionnez **Ajouter > Nouveaux fichiers**. Sélectionnez **Général > Classe vide**, puis entrez un nom de contrôleur :

    ![Boîte de dialogue Nouveau fichier](media/asp-net-core-image8.png)

2. Ajoutez le code suivant au nouveau contrôleur :

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using System.Text.Encodings.Web;

    namespace Hello_ASP
    {
        public class HelloWorldController : Controller
        {
            //
            // GET: /HelloWorld/

            public string Index()
            {
                return "This is my default action...";
            }

        }
    }
    ```

3. Ajoutez la dépendance `Microsoft.AspNetCore.Mvc` au projet en cliquant avec le bouton droit sur le dossier **Dépendance** et en sélectionnant **Ajouter un package...**.

4. Utilisez la zone Rechercher pour trouver `Microsoft.AspNetCore.Mvc` dans la bibliothèque NuGet, puis sélectionnez **Ajouter un package**. L’installation peut prendre quelques minutes et vous serez peut-être invité à accepter différentes licences pour les dépendances nécessaires :

    ![Ajouter NuGet](media/asp-net-core-image9.png)

5. Dans la classe Startup, supprimez l’expression lambda `app.Run` et définissez comme suit la logique de routage d’URL utilisée par MVC pour déterminer quel code il doit appeler :

    ```csharp
    app.UseMvc(routes =>
    {
        routes.MapRoute(
        name: "default",
        template: "{controller=HelloWorld}/{action=Index}/{id?}");
    });
    ```

    Veillez à supprimer l’expression lambda `app.Run`, car ceci remplacera la logique de routage.

    MVC utilise le format suivant pour déterminer le code à exécuter :

    `/[Controller]/[ActionName]/[Parameters]`

    Quand vous ajoutez l’extrait de code ci-dessus, vous indiquez à l’application d’utiliser par défaut le contrôleur `HelloWorld` et la méthode d’action `Index`.

6. Ajoutez l’appel de `services.AddMvc();` à la méthode `ConfigureServices`, comme illustré ci-dessous :

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
    }
    ```

    Vous pouvez également passer des informations sur les paramètres de l’URL au contrôleur.

7. Ajoutez une autre méthode à votre contrôleur HelloWorld, comme illustré ci-dessous :

    ```csharp
    public string Xamarin(string name)
    {
        return HtmlEncoder.Default.Encode($"Hello {name}, welcome to Visual Studio for Mac");
    }
    ```

8. Si vous exécutez l’application maintenant, elle doit ouvrir automatiquement votre navigateur :

    ![Exécution de l’application dans le navigateur](media/asp-net-core-image13.png)

9. Essayez d’accéder à `http://localhost:xxxx/HelloWorld/Xamarin?name=Amy` (en remplaçant `xxxx` par le port approprié). Vous devez normalement voir ceci :

    ![Exécution de l’application dans le navigateur avec des arguments](media/asp-net-core-image10.png)


## <a name="troubleshooting"></a>Résolution des problèmes

Si vous avez besoin d’installer .NET Core manuellement sur Mac OS 10.11 (El Capitan) et ultérieur, procédez comme suit :

1. Avant de commencer l’installation de .NET Core, assurez-vous d’avoir appliqué toutes les mises à jour du système d’exploitation à la dernière version stable. Vous pouvez le vérifier en accédant à l’application App Store et en sélectionnant l’onglet Mises à jour.

2. Suivez les étapes listées sur le [site de .NET Core](https://www.microsoft.com/net/core#macos).

Veillez à effectuer correctement les quatre étapes pour garantir que .NET Core est bien installé.

## <a name="summary"></a>Récapitulatif

Ce guide était une introduction à ASP.NET Core. Il explique ce que c’est et quand l’utiliser, et fournit des informations sur son utilisation dans Visual Studio pour Mac.
Pour plus d’informations sur les étapes à suivre à partir d’ici, consultez les guides suivants :
- Documentation [ASP.NET Core](https://docs.microsoft.com/aspnet/core/?view=aspnetcore-2.1#build-web-ui-and-web-apis-using-aspnet-core-mvc).
- [Création de services backend pour les applications mobiles natives](https://docs.microsoft.com/aspnet/core/mobile/native-mobile-backend), qui montre comment créer un service REST en utilisant ASP.NET Core pour une application Xamarin.Forms.
- [Ateliers pratiques ASP.NET Core](https://github.com/Microsoft/vs4mac-labs/tree/master/Web/Getting-Started).
