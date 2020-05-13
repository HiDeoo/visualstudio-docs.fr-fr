---
title: Tâche Link | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ForceFileOutput
- VC.Project.VCLinkerTool.LinkStatus
- VC.Project.VCLinkerTool.CLRUnmanagedCodeCheck
- VC.Project.VCLinkerTool.SpecifySectionAttributes
- VC.Project.VCLinkerTool.SupportNobindOfDelayLoadedDLL
- VC.Project.VCLinkerTool.MinimumRequiredVersion
- VC.Project.VCLinkerTool.PerUserRedirection
- VC.Project.VCLinkerTool.CreateHotPatchableImage
- VC.Project.VCLinkerTool.DataExecutionPrevention
- VC.Project.VCLinkerTool.TreatLinkerWarningsAsErrors
- vc.task.link
- VC.Project.VCLinkerTool.ImageHasSafeExceptionHandlers
- VC.Project.VCLinkerTool.CLRSupportLastError
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild (C++), Link task
- Link task (MSBuild (C++))
ms.assetid: 0a61f168-3113-4fa7-83a3-d9142e2a33f8
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 01105e3fd4c86d57077df7804e66592e32ebae07
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "78865347"
---
# <a name="link-task"></a>Lier la tâche

Enveloppe l’outil de liaison Microsoft CMD, *link.exe*. L’outil de l’éditeur de liens lie des bibliothèques et des fichiers objets COFF (Common Object File Format) pour créer un fichier exécutable (*.exe*) ou une bibliothèque de liens dynamiques (DLL). Pour plus d’informations, consultez [les options Linker](/cpp/build/reference/linker-options) et [utilisez MSBuild à partir de la ligne de commande](/cpp/build/msbuild-visual-cpp) et utilisez [l’toolset Microsoft CMD de la ligne de commande](/cpp/build/building-on-the-command-line).

## <a name="parameters"></a>Paramètres

 Le tableau ci-dessous décrit les paramètres de la tâche **Link**. La plupart des paramètres de tâche, et quelques ensembles de paramètres, correspondent à une option de ligne de commande.

- **AdditionalDependencies**

  Paramètre **de chaîne en** option.

  Spécifie une liste de fichiers d’entrée à ajouter à la commande.

  Pour plus d’informations, consultez [Fichiers d’entrée LINK](/cpp/build/reference/link-input-files).

- **AdditionalLibraryDirectories**

  Paramètre **de chaîne en** option.

  Substitue le chemin d’accès de la bibliothèque d’environnement. Spécifiez un nom de répertoire.

  Pour plus d’informations, consultez l’article [/LIBPATH (Autre chemin de bibliothèque)](/cpp/build/reference/libpath-additional-libpath).

- **AdditionalManifestDependencies**

  Paramètre **de chaîne en** option.

  Spécifie les attributs qui sont placés dans la section `dependency` du fichier manifeste.

  Pour plus d’informations, consultez [/MANIFESTDEPENDENCY (Spécifier les dépendances de manifeste)](/cpp/build/reference/manifestdependency-specify-manifest-dependencies). Consultez également [Fichiers de configuration des serveurs de publication](/windows/desktop/SbsCs/publisher-configuration-files).

- **Options supplémentaires**

  Paramètre **de chaîne** facultatif.

  Liste des options de l’Éditeur de liens indiquées sur la ligne de commande. Par exemple, /\<option1> /\<option2> /\<option#>. Utilisez ce paramètre pour spécifier des options de l’Éditeur de liens qui ne sont pas représentées par un autre paramètre de tâche **Link**.

  Pour plus d’informations, consultez [Options de l’éditeur de liens](/cpp/build/reference/linker-options).

- **AddModuleNamesToAssembly**

  Paramètre **de chaîne en** option.

  Ajoute une référence de module à un assembly.

  Pour plus d’informations, consultez [/ASSEMBLYMODULE (Ajouter un module MSIL à l’assembly)](/cpp/build/reference/assemblymodule-add-a-msil-module-to-the-assembly).

- **AllowIsolation**

  Paramètre **Boolean** optionnel.

  Si `true`, le système d’exploitation recherche et charge le manifeste. Si `false`, indique que les DLL sont chargées comme s’il n’existait pas de manifeste.

  Pour plus d’informations, voir [/ALLOWISOLATION (Regard manifeste)](/cpp/build/reference/allowisolation-manifest-lookup).

- **AssemblageDebug**

  Paramètre **Boolean** optionnel.

  Si `true`, émet l’attribut **DebuggableAttribute** avec le suivi des informations de débogage, et désactive les optimisations JIT. Si `false`, émet l’attribut **DebuggableAttribute**, mais désactive le suivi des informations de débogage et active les optimisations JIT.

  Pour plus d’informations, consultez l’article [/ASSEMBLYDEBUG (Ajouter DebuggableAttribute)](/cpp/build/reference/assemblydebug-add-debuggableattribute).

- **AssemblyLinkResource**

  Paramètre **de chaîne en** option.

  Crée un lien à une ressource .NET Framework dans le fichier de sortie ; le fichier de ressources n’est pas placé dans le fichier de sortie. Spécifiez le nom de la ressource.

  Pour plus d’informations, voir [/ASSEMBLYLINKRESOURCE (Lien vers .NET Framework resource)](/cpp/build/reference/assemblylinkresource-link-to-dotnet-framework-resource).

- **AttributeFileTracking**

  Paramètre **booléen** implicite.

  Active le suivi plus approfondi des fichiers pour capturer le comportement de liaison incrémentielle. Retourne toujours `true`.

- **BaseAddress (baseAddress)**

  Paramètre **de chaîne** facultatif.

  Définit une adresse de base pour le programme ou la DLL en cours de génération. Spécifiez `{address[,size] | @filename,key}`.

  Pour plus d’informations, voir [/BASE (adresse de base)](/cpp/build/reference/base-base-address).

- **BuildingInIDE**

  Paramètre **Boolean** optionnel.

  Si true, indique que MSBuild est appelé à partir de l’IDE. Dans le cas contraire, indique que MSBuild est appelé à partir de la ligne de commande.

  Ce paramètre n’a aucune option équivalente dans l’Éditeur de liens.

- **CLRImageType**

  Paramètre **de chaîne** facultatif.

  Définit le type d’image CLR (Common Language Runtime).

  Spécifiez l’une des valeurs suivantes, chacune d’elles correspondant à une option de l’Éditeur de liens.

  - **Default** - *Défaut\<aucun>*

  - **ForceIJWImage** - **/CLRIMAGETYPE:IJW**

  - **ForcePureILImage** - **/CLRIMAGETYPE:PURE**

  - **ForceSafeILImage** - **/CLRIMAGETYPE:SAFE**

  Pour plus d’informations, voir [/CLRIMAGETYPE (Spécifier le type d’image CLR)](/cpp/build/reference/clrimagetype-specify-type-of-clr-image).

- **CLRSupportLastError**

  Paramètre **de chaîne** facultatif.

  Préserve le dernier code d’erreur des fonctions appelées via le mécanisme P/Invoke.

  Spécifiez l’une des valeurs suivantes, chacune d’elles correspondant à une option de l’Éditeur de liens.

  - **Activé** - **/CLRSupportLastError**

  - **Désactivé** - **/CLRSupportLastError:NON**

  - **SystemDlls** - **/CLRSupportLastError:SYSTEMDLL**

  Pour plus d’informations, voir [/CLRSUPPORTLASTERROR (Préserver le dernier code d’erreur pour les appels PInvoke)](/cpp/build/reference/clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls).

- **CLRThreadAttribute**

  Paramètre **de chaîne** facultatif.

  Spécifie explicitement l’attribut de thread pour le point d’entrée de votre programme CLR.

  Spécifiez l’une des valeurs suivantes, chacune d’elles correspondant à une option de l’Éditeur de liens.

  - **DéfautThreadingAttribute** - **/CLRTHREADATTRIBUTE:NONE**

  - **MTAThreadingAttribute** - **/CLRTHREADATTRIBUTE:MTA**

  - **STAThreadingAttribute** - **/CLRTHREADATTRIBUTE:STA**

  Pour plus d’informations, voir [/CLRTHREADATTRIBUTE (Définissez l’attribut de thread CLR)](/cpp/build/reference/clrthreadattribute-set-clr-thread-attribute).

- **CLRUnmanagedCodeCheck**

  Paramètre **Boolean** optionnel.

  Spécifie si l’Éditeur de liens applique **SuppressUnmanagedCodeSecurityAttribute** aux appels P/Invoke générés par l’Éditeur de liens à partir du code managé dans les DLL natives.

  Pour plus d’informations, consultez [/CLRUNMANAGEDCODECHECK (Ajouter SuppressUnmanagedCodeSecurityAttribute)](/cpp/build/reference/clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute).

- **CréerHotPatchableImage**

  Paramètre **de chaîne** facultatif.

  Prépare une image corrigeable en mémoire.

  Spécifiez l’une des valeurs suivantes, qui correspond à une option de l’Éditeur de liens.

  - **Activé** - **/FUNCTIONPADMIN**

  - **X86Image** - **/FUNCTIONPADMIN:5**

  - **X64Image** - **/FUNCTIONPADMIN:6**

  - **ItaniumImage** - **/FUNCTIONPADMIN:16**

  Pour plus d’informations, voir [/FUNCTIONPADMIN (Créer une image hotpatchable)](/cpp/build/reference/functionpadmin-create-hotpatchable-image).

- **DataExecutionPrevention**

  Paramètre **Boolean** optionnel.

  Si `true`, indique que la compatibilité d’un exécutable avec la fonctionnalité Prévention de l’exécution des données Windows a été testée.

  Pour plus d’informations, consultez l’article [/NXCOMPAT (compatible avec la prévention de l’exécution des données)](/cpp/build/reference/nxcompat-compatible-with-data-execution-prevention).

- **DelayLoadDLLs**

  Paramètre **de chaîne en** option.

  Ce paramètre entraîne le *chargement différé* des DLL. Spécifiez le nom d’une DLL dont vous voulez différer le chargement.

  Pour plus d’informations, consultez [/DELAYLOAD (Différer le chargement de l’importation)](/cpp/build/reference/delayload-delay-load-import).

- **DelaySign**

  Paramètre **Boolean** optionnel.

  Si `true`, signe partiellement un assembly. Par défaut, la valeur est `false`.

  Pour plus d’informations, consultez [/DELAYSIGN (Signer partiellement un assembly)](/cpp/build/reference/delaysign-partially-sign-an-assembly).

- **Pilote**

  Paramètre **de chaîne** facultatif.

  Spécifiez ce paramètre pour générer un pilote en mode noyau Windows NT.

  Spécifiez l’une des valeurs suivantes, chacune d’elles correspondant à une option de l’Éditeur de liens.

  - **NotSet aucun** - >*\<*

  - **Pilote** - **/Pilote**

  - **UpOnly** - **/DRIVER:UPONLY**

  - **WDM** - **/DRIVER:WDM**

  Pour plus d’informations, voir [/DRIVER (Windows NT kernel mode driver)](/cpp/build/reference/driver-windows-nt-kernel-mode-driver).

- **EmbedManagedResourceFile**

  Paramètre **de chaîne en** option.

  Incorpore un fichier de ressources dans un assembly. Spécifiez le nom du fichier de ressources requis. Spécifiez éventuellement le nom logique, qui permet de charger la ressource, ainsi que l’option **PRIVATE**, qui indique dans le manifeste de l’assembly que le fichier de ressources est privé.

  Pour plus d’informations, voir [/ASSEMBLYRESOURCE (Embed a managed resource)](/cpp/build/reference/assemblyresource-embed-a-managed-resource).

- **EnableCOMDATFolding**

  Paramètre **Boolean** optionnel.

  Si `true`, active le pliage COMDAT identique.

  Pour plus d’informations, consultez l’argument `ICF[= iterations]` de l’article [/OPT (Optimisations)](/cpp/build/reference/opt-optimizations).

- **EnableUAC**

  Paramètre **Boolean** optionnel.

  Si `true`, indique que les informations de contrôle de compte d’utilisateur sont incorporées dans le manifeste du programme.

  Pour plus d’informations, consultez l’article [/MANIFESTUAC (Incorporer des informations sur le contrôle de compte d’utilisateur dans le manifeste)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).

- **EntryPointSymbol**

  Paramètre **de chaîne** facultatif.

  Spécifie une fonction de point d’entrée comme adresse de départ d’un fichier *.exe* ou d’une DLL. Spécifiez un nom de fonction comme valeur du paramètre.

  Pour plus d’informations, voir [/ENTRY (Symbole d’entrée)](/cpp/build/reference/entry-entry-point-symbol).

- **FixedBaseAddress**

  Paramètre **Boolean** optionnel.

  Si `true`, crée un programme ou une DLL qui peuvent être chargés uniquement à leur adresse de base préférée.

  Pour plus d’informations, voir [/FIXED (adresse de base fixe)](/cpp/build/reference/fixed-fixed-base-address).

- **ForceFileOutput**

  Paramètre **de chaîne** facultatif.

  Indique à l’éditeur de liens de créer un fichier *.exe* ou une DLL valide même si un symbole est référencé sans être défini ou s’il est défini plusieurs fois.

  Spécifiez l'une des valeurs suivantes, chacune d'elles correspondant à une option de ligne de commande.

  - **Activé** - **/FORCE**

  - **MultiplyDefinedSymbolOnly** - **/FORCE:MULTIPLE**

  - **IndéfinieSymbolOnly** - **/FORCE:UNRESOLVED**

  Pour plus d’informations, consultez [/FORCE (Forcer la sortie d’un fichier)](/cpp/build/reference/force-force-file-output).

- **ForceSymbolReferences**

  Paramètre **de chaîne en** option.

  Ce paramètre indique à l’Éditeur de liens d’ajouter un symbole spécifié à la table de symboles.

  Pour plus d’informations, consultez [/INCLUDE (Forcer les références des symboles)](/cpp/build/reference/include-force-symbol-references).

- **FunctionOrder**

  Paramètre **de chaîne** facultatif.

  Ce paramètre optimise votre programme en plaçant les fonctions empaquetées spécifiées (COMDAT) dans l’image dans un ordre prédéterminé.

  Pour plus d’informations, voir [/ORDER (Mettre des fonctions en ordre)](/cpp/build/reference/order-put-functions-in-order).

- **GenerateDebugInformation**

  Paramètre **Boolean** optionnel.

  Si la valeur est `true`, crée des informations de débogage pour le fichier *.exe* ou la DLL.

  Pour plus d’informations, voir [/DEBUG (Générer des informations de débbug)](/cpp/build/reference/debug-generate-debug-info).

- **GenerateManifest**

  Paramètre **Boolean** optionnel.

  Si `true`, crée un fichier manifeste côte à côte.

  Pour plus d’informations, consultez [/MANIFEST (Créer un manifeste d’assembly côte à côte)](/cpp/build/reference/manifest-create-side-by-side-assembly-manifest).

- **GenerateMapFile**

  Paramètre **Boolean** optionnel.

  Si `true`, crée un *fichier de mappage*. L’extension du nom de fichier du fichier de la carte est *.map*.

  Pour plus d’informations, voir [/MAP (Générer mapfile)](/cpp/build/reference/map-generate-mapfile).

- **HeapCommitSize**

  Paramètre **de chaîne** facultatif.

  Spécifie la quantité de mémoire physique sur le tas à allouer à la fois.

  Pour plus d’informations, consultez l’argument `commit` dans [/HEAP (Définir la taille des tas)](/cpp/build/reference/heap-set-heap-size). Reportez-vous également au paramètre **HeapReserveSize**.

- **HeapReserveSize**

  Paramètre **de chaîne** facultatif.

  Spécifie l’allocation totale des tas dans la mémoire virtuelle.

  Pour plus d’informations, consultez l’argument `reserve` dans [/HEAP (Définir la taille des tas)](/cpp/build/reference/heap-set-heap-size). Reportez-vous également au paramètre **HeapCommitSize** dans ce tableau.

- **IgnoreAllDefaultLibraries**

  Paramètre **Boolean** optionnel.

  Si `true`, indique à l’Éditeur de liens de supprimer une ou plusieurs bibliothèques par défaut de la liste de recherche des bibliothèques lors de la résolution des références externes.

  Pour plus d’informations, consultez [/NODEFAULTLIB (Ignorer les bibliothèques)](/cpp/build/reference/nodefaultlib-ignore-libraries).

- **IgnoreEmbeddedIDL**

  Paramètre **Boolean** optionnel.

  Si la valeur est `true`, spécifie que les attributs IDL définis dans le code source ne doivent pas être traités dans un fichier *.idl*.

  Pour plus d’informations, consultez [/IGNOREIDL (Ne pas traiter les attributs dans MIDL)](/cpp/build/reference/ignoreidl-don-t-process-attributes-into-midl).

- **IgnoreImportLibrary**

  Paramètre **Boolean** optionnel.

  Si `true`, spécifie que la bibliothèque d’importation générée par cette configuration ne doit pas être importée dans des projets dépendants.

  Ce paramètre ne correspond pas à une option de l’Éditeur de liens.

- **IgnoreSpecificDefaultLibraries**

  Paramètre **de chaîne en** option.

  Spécifie un ou plusieurs noms de bibliothèques par défaut à ignorer. Séparez plusieurs bibliothèques à l’aide de points-virgules.

  Pour plus d’informations, consultez [/NODEFAULTLIB (Ignorer les bibliothèques)](/cpp/build/reference/nodefaultlib-ignore-libraries).

- **ImageHasSafeExceptionHandlers**

  Paramètre **Boolean** optionnel.

  Si `true`, l’Éditeur de liens produit une image uniquement s’il peut également produire un tableau des gestionnaires d’exceptions sécurisés de l’image.

  Pour plus d’informations, voir [/SAFESEH (Image a des gestionnaires d’exception sûrs)](/cpp/build/reference/safeseh-image-has-safe-exception-handlers).

- **ImportLibrary**

  Nom de bibliothèque d’importation spécifié par l’utilisateur qui remplace le nom de bibliothèque par défaut.

  Pour plus d’informations, voir [/IMPLIB (Bibliothèque d’importation de nom)](/cpp/build/reference/implib-name-import-library).

- **KeyContainer (keyContainer)**

  Paramètre **de chaîne** facultatif.

  Conteneur qui contient la clé d’un assembly signé.

  Pour plus d’informations, voir [/KEYCONTAINER (Spécifier un conteneur clé pour signer une assemblée)](/cpp/build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly). Reportez-vous également au paramètre **KeyFile** de ce tableau.

- **Keyfile**

  Paramètre **de chaîne** facultatif.

  Spécifie un fichier qui contient la clé d’un assembly signé.

  Pour plus d’informations, voir [/KEYFILE (Spécifier la clé ou la paire de clés pour signer une assemblée)](/cpp/build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly). Reportez-vous également au paramètre **KeyContainer**.

- **LargeAddressAware**

  Paramètre **Boolean** optionnel.

  Si `true`, l’application peut gérer des adresses supérieures à 2 gigaoctets.

  Pour plus d’informations, consultez [/LARGEADDRESSAWARE (Gérer les longues adresses)](/cpp/build/reference/largeaddressaware-handle-large-addresses).

- **LinkDLL**

  Paramètre **Boolean** optionnel.

  Si `true`, génère une DLL comme fichier de sortie principal.

  Pour plus d’informations, consultez l’article [/DLL (Générer une DLL)](/cpp/build/reference/dll-build-a-dll).

- **LinkErrorReporting**

  Paramètre **de chaîne** facultatif.

  Vous permet de signaler les erreurs internes du compilateur (ICE) directement à Microsoft.

  Spécifiez l'une des valeurs suivantes, chacune d'elles correspondant à une option de ligne de commande.

  - **NoErrorReport** - **/ERRORREPORT:NONE**

  - **PromptImmediately** - **/ERRORREPORT:PROMPT**

  - **QueueForNextLogin** - **/ERRORREPORT:QUEUE**

  - **SendErrorReport** - **/ERRORREPORT:SEND**

  Pour plus d’informations, consultez [/ERRORREPORT (Signaler les erreurs internes de l’éditeur de liens)](/cpp/build/reference/errorreport-report-internal-linker-errors).

- **LinkIncremental**

  Paramètre **Boolean** optionnel.

  Si `true`, active les liens incrémentiels.

  Pour plus d’informations, consultez [/INCREMENTAL (Lier par incrément)](/cpp/build/reference/incremental-link-incrementally).

- **LinkLibraryDependencies**

  Paramètre **Boolean** optionnel.

  Si la valeur est `true`, spécifie que les sorties de bibliothèque émanant des dépendances du projet sont automatiquement liées.

  Ce paramètre ne correspond pas à une option de l’Éditeur de liens.

- **LinkStatus**

  Paramètre **Boolean** optionnel.

  Si `true`, spécifie que l’Éditeur de liens doit afficher un indicateur de progression qui montre le pourcentage d’exécution du lien.

  Pour plus d’informations, voir l’argument `STATUS` de [/LTCG (Link-time code generation)](/cpp/build/reference/ltcg-link-time-code-generation).

- **LinkTimeCodeGeneration**

  Paramètre **de chaîne** facultatif.

  Spécifie des options pour l’optimisation guidée par profil.

  Spécifiez l'une des valeurs suivantes, chacune d'elles correspondant à une option de ligne de commande.

  - **Default** - *Défaut\<aucun>*

  - **UseLinkTimeCodeGeneration** - **/LTCG**

  - **PGInstrument** - **/LTCG:PGInstrument**

  - **PGOptimisation** - **/LTCG:PGOptimize**

  - **PGUpdate**

    \- **/LTCG:PGUpdate**

  Pour plus d’informations, consultez [/LTCG (Génération de code durant l’édition de liens)](/cpp/build/reference/ltcg-link-time-code-generation).

- **ManifesteFile**

  Paramètre **de chaîne** facultatif.

  Remplace le nom du fichier manifeste par défaut par le nom du fichier spécifié.

  Pour plus d’informations, voir [/MANIFESTFILE (Fichier manifeste nom)](/cpp/build/reference/manifestfile-name-manifest-file).

- **MapExports**

  Paramètre **Boolean** optionnel.

  Si `true`, indique à l’Éditeur de liens d’inclure les fonctions exportées dans un fichier de mappage.

  Pour plus d’informations, voir l’argument `EXPORTS` de [/MAPINFO (Inclure des informations dans mapfile)](/cpp/build/reference/mapinfo-include-information-in-mapfile).

- **MapFileName**

  Paramètre **de chaîne** facultatif.

  Remplace le nom du fichier de mappage par défaut par le nom du fichier spécifié.

- **MergedIDLBaseFileName**

  Paramètre **de chaîne** facultatif.

  Indique le nom et l’extension de nom du fichier *.idl*.

  Pour plus d’informations, voir [/IDLOUT (Nom MIDL fichiers de sortie)](/cpp/build/reference/idlout-name-midl-output-files).

- **MergeSections**

  Paramètre **de chaîne** facultatif.

  Combine des sections dans une image. Spécifiez `from-section=to-section`.

  Pour plus d’informations, voir [/MERGE (Sections Combine)](/cpp/build/reference/merge-combine-sections).

- **MidlCommandFile**

  Paramètre **de chaîne** facultatif.

  Spécifiez le nom d’un fichier qui contient les options de ligne de commande MIDL.

  Pour plus d’informations, voir [/MIDL (Spécifier les options de ligne de commande MIDL)](/cpp/build/reference/midl-specify-midl-command-line-options).

- **MinimumRequiredVersion**

  Paramètre **de chaîne** facultatif.

  Spécifie la version minimale requise du sous-système. Les arguments sont des nombres décimaux compris entre 0 et 65 535.

- **ModuleDefinitionFile**

  Paramètre **de chaîne** facultatif.

  Spécifie le nom d’un [fichier de définition de module](/cpp/build/reference/module-definition-dot-def-files).

  Pour plus d’informations, voir [/DEF (Fichier de définition du module)](/cpp/build/reference/def-specify-module-definition-file).

- **MSDOSStubFileName**

  Paramètre **de chaîne** facultatif.

  Attache le programme stub MS-DOS spécifié à un programme Win32.

  Pour plus d’informations, voir [/STUB (MS-DOS nom de fichier stub)](/cpp/build/reference/stub-ms-dos-stub-file-name).

- **NoEntryPoint**

  Paramètre **Boolean** optionnel.

  Si `true`, crée une DLL de ressource uniquement.

  Pour plus d’informations, voir [/NOENTRY (Pas de point d’entrée)](/cpp/build/reference/noentry-no-entry-point).

- **ObjectFiles**

  Paramètre **String[]** implicite.

  Spécifie les fichiers objets liés.

- **OptimizeReferences**

  Paramètre **Boolean** optionnel.

  Si `true`, élimine les fonctions et/ou les données qui ne sont jamais référencées.

  Pour plus d’informations, consultez l’argument `REF` dans l’article [/OPT (Optimisations)](/cpp/build/reference/opt-optimizations).

- **Outputfile**

  Paramètre **de chaîne** facultatif.

  Remplace le nom et l’emplacement par défaut du programme créé par l’Éditeur de liens.

  Pour plus d’informations, voir [/OUT (Nom de fichier de sortie)](/cpp/build/reference/out-output-file-name).

- **PerUserRedirection**

  Paramètre **Boolean** optionnel.

  Si `true` et si l’inscription de la sortie est activée, force les entrées de Registre écrites dans **HKEY_CLASSES_ROOT** à être redirigées vers **HKEY_CURRENT_USER**.

- **PreprocessOutput**

  Paramètre `ITaskItem[]` facultatif.

  Définit un tableau d’éléments de sortie de préprocesseur pouvant être consommés et émis par des tâches.

- **PreventDllBinding**

  Paramètre **Boolean** optionnel.

  Si la valeur est `true`, indique à *Bind.exe* que l’image liée ne doit pas être associée.

  Pour plus d’informations, voir [/ALLOWBIND (Prevent DLL binding)](/cpp/build/reference/allowbind-prevent-dll-binding).

- **Profil**

  Paramètre **Boolean** optionnel.

  Si `true`, génère un fichier de sortie utilisable avec le profileur **Outils d’analyse des performances**.

  Pour plus d’informations, consultez [/PROFILE (Profileur des outils d’analyse des performances)](/cpp/build/reference/profile-performance-tools-profiler).

- **ProfileGuidedDatabase**

  Paramètre **de chaîne** facultatif.

  Spécifie le nom du fichier *.pgd* qui sera utilisé pour contenir des informations sur le programme en cours d’exécution

  Pour plus d’informations, consultez [/PGD (Spécifier la base de données pour les optimisations guidées par profil)](/cpp/build/reference/pgd-specify-database-for-profile-guided-optimizations).

- **ProgramDatabaseFile**

  Paramètre **de chaîne** facultatif.

  Spécifie le nom de la base de données du programme (PDB) créée par l’Éditeur de liens.

  Pour plus d’informations, consultez [/PDB (Utiliser la base de données du programme)](/cpp/build/reference/pdb-use-program-database).

- **RandomizedBaseAddress**

  Paramètre **Boolean** optionnel.

  Si `true`, génère une image exécutable qui peut être redéfinie de façon aléatoire au moment du chargement en utilisant la fonctionnalité de *randomisation du format d’espace d’adresse* (ASLR) de Windows.

  Pour plus d’informations, consultez l’article [/DYNAMICBASE (Utiliser la randomisation du format d’espace d’adresse)](/cpp/build/reference/dynamicbase-use-address-space-layout-randomization).

- **RegisterOutput**

  Paramètre **Boolean** optionnel.

  Si `true`, inscrit la sortie principale de cette génération.

- **SectionAlignment**

  Paramètre **entier** facultatif.

  Spécifie l’alignement de chaque section dans l’espace d’adressage linéaire du programme. La valeur du paramètre est un numéro d’unité d’octets et une puissance de deux.

  Pour plus d’informations, consultez [/ALIGN (Alignement des sections)](/cpp/build/reference/align-section-alignment).

- **SetChecksum**

  Paramètre **Boolean** optionnel.

  Si la valeur est `true`, définit la somme de contrôle dans l’en-tête d’un fichier *.exe*.

  Pour plus d’informations, voir [/RELEASE (Réglez le checksum)](/cpp/build/reference/release-set-the-checksum).

- **ShowProgress**

  Paramètre **de chaîne** facultatif.

  Spécifie le niveau de détail des rapports de progression de l’opération de liaison.

  Spécifiez l'une des valeurs suivantes, chacune d'elles correspondant à une option de ligne de commande.

  - **NotSet aucun** - >*\<*

  - **LinkVerbose** - **/VERBOSE**

  - **LinkVerboseLib** - **/VERBOSE:Lib**

  - **LinkVerboseICF** - **/VERBOSE:ICF**

  - **LinkVerboseREF** - **/VERBOSE:REF**

  - **LinkVerboseSAFESEH** - **/VERBOSE:SAFESEH**

  - **LinkVerboseCLR** - **/VERBOSE:CLR**

  Pour plus d’informations, consultez [/VERBOSE (Imprimer les messages d’avancement)](/cpp/build/reference/verbose-print-progress-messages).

- **récentes**

  Paramètre `ITaskItem[]` requis.

  Définit un tableau d’éléments de fichier source MSBuild pouvant être consommés et émis par des tâches.

- **SpecifySectionAttributes**

  Paramètre **de chaîne** facultatif.

  Indique les attributs d’une section. Il remplace les attributs qui ont été définis quand le fichier *.obj* correspondant à la section a été compilé.

  Pour plus d’informations, voir [/SECTION (Spécifier les attributs de section)](/cpp/build/reference/section-specify-section-attributes).

- **StackCommitSize**

  Paramètre **de chaîne** facultatif.

  Spécifie la quantité de mémoire physique contenue dans chaque allocation lorsque de la mémoire supplémentaire est allouée.

  Pour plus d’informations, consultez l’argument `commit` dans [/STACK (Allocations de la pile)](/cpp/build/reference/stack-stack-allocations).

- **StackReserveSize**

  Paramètre **de chaîne** facultatif.

  Spécifie la taille totale d’allocation de piles dans la mémoire virtuelle.

  Pour plus d’informations, consultez l’argument `reserve` dans [/STACK (Allocations de la pile)](/cpp/build/reference/stack-stack-allocations).

- **StripPrivateSymbols**

  Paramètre **de chaîne** facultatif.

  Crée un second fichier de base de données du programme (PDB) qui omet les symboles que vous ne souhaitez pas distribuer à vos clients. Spécifiez le nom du second fichier PDB.

  Pour plus d’informations, voir [/PDBSTRIPPED (Bandes privées)](/cpp/build/reference/pdbstripped-strip-private-symbols).

- **Sous-système**

  Paramètre **de chaîne** facultatif.

  Spécifie l'environnement pour l'exécutable.

  Spécifiez l'une des valeurs suivantes, chacune d'elles correspondant à une option de ligne de commande.

  - **NotSet aucun** - >*\<*

  - **Console** - **/SUBSYSTEM:CONSOLE**

  - **Windows** - **/SUBSYSTEM:WINDOWS**

  - **Native** - **/SUBSYSTEM:NATIVE**

  - **Demande EFI** - **/SUBSYSTEM:EFI_APPLICATION**

  - **EFI Boot Service Driver** - **/SUBSYSTEM:EFI_BOOT_SERVICE_DRIVER**

  - **EFI ROM** - **/SUBSYSTEM:EFI_ROM**

  - **EFI Runtime** - **/SUBSYSTEM:EFI_RUNTIME_DRIVER**

  - **WindowsCE** - **/SUBSYSTEM:WINDOWSCE**

  - **POSIX** - **/SOUS-SYSTÈME:POSIX**

  Pour plus d’informations, consultez l’article [/SUBSYSTEM (Spécifier le sous-système)](/cpp/build/reference/subsystem-specify-subsystem).

- **SupportNobindOfDelayLoadedDLL**

  Paramètre **Boolean** optionnel.

  Si `true`, indique à l’Éditeur de liens de ne pas inclure dans l’image finale de table IAT (Import Address Table).

  Pour plus d’informations, voir l’argument `NOBIND` de [/DELAY (Réglages d’importation de charge de retard)](/cpp/build/reference/delay-delay-load-import-settings).

- **SupportUnloadOfDelayLoadedDLL**

  Paramètre **Boolean** optionnel.

  Si `true`, indique à la fonction d’assistance de chargement différé de prendre en charge le déchargement explicite de la DLL.

  Pour plus d’informations, voir l’argument `UNLOAD` de [/DELAY (Réglages d’importation de charge de retard)](/cpp/build/reference/delay-delay-load-import-settings).

- **SuppressStartupBanner**

  Paramètre **Boolean** optionnel.

  Si la valeur est `true`, empêche l'affichage du message de copyright et de numéro de version quand la tâche démarre.

  Pour plus d’informations, consultez [/NOLOGO (Supprimer la bannière de démarrage) (éditeur de liens)](/cpp/build/reference/nologo-suppress-startup-banner-linker).

- **SwapRunFromCD**

  Paramètre **Boolean** optionnel.

  Si `true`, indique au système d’exploitation de copier tout d’abord la sortie de l’Éditeur de liens dans un fichier d’échange, puis d’y exécuter l’image.

  Pour plus d’informations, voir l’argument `CD` de [/SWAPRUN (sortie de liaison de charge à l’échange de fichiers)](/cpp/build/reference/swaprun-load-linker-output-to-swap-file). Consultez également le paramètre **SwapRunFromNET**.

- **SwapRunFromNET**

  Paramètre **Boolean** optionnel.

  Si `true`, indique au système d’exploitation de copier tout d’abord la sortie de l’Éditeur de liens dans un fichier d’échange, puis d’y exécuter l’image.

  Pour plus d’informations, voir l’argument `NET` de [/SWAPRUN (sortie de liaison de charge à l’échange de fichiers)](/cpp/build/reference/swaprun-load-linker-output-to-swap-file). Reportez-vous également au paramètre **SwapRunFromCD** de ce tableau.

- **TargetMachine**

  Paramètre **de chaîne** facultatif.

  Spécifie la plateforme cible du programme ou de la DLL.

  Spécifiez l'une des valeurs suivantes, chacune d'elles correspondant à une option de ligne de commande.

  - **NotSet aucun** - >*\<*

  - **MachineARM** - **/MACHINE:ARM**

  - **MachineEBC** - **/MACHINE:EBC**

  - **MachineIA64** - **/MACHINE:IA64**

  - **MachineMIPS** - **/MACHINE:MIPS**

  - **MachineMIPS16** - **/MACHINE:MIPS16**

  - **MachineMIPSFPU** - **/MACHINE:MIPSFPU**

  - **MachineMIPSFPU16** - **/MACHINE:MIPSFPU16**

  - **MachineSH4** - **/MACHINE:SH4**

  - **MachineTHUMB** - **/MACHINE:THUMB**

  - **MachineX64** - **/MACHINE:X64**

  - **MachineX86** - **/MACHINE:X86**

  Pour plus d’informations, voir [/MACHINE (Specify target platform)](/cpp/build/reference/machine-specify-target-platform).

- **TerminalServerAware**

  Paramètre **Boolean** optionnel.

  Si `true`, définit un indicateur dans le champ DllCharacteristics IMAGE_OPTIONAL_HEADER de l’en-tête facultatif de l’image du programme. Si cet indicateur est défini, le serveur Terminal Server n’apportera aucune modification à l’application.

  Pour plus d’informations, [voir/TSAWARE (Créer l’application Terminal Server aware)](/cpp/build/reference/tsaware-create-terminal-server-aware-application).

- **TrackerLogDirectory**

  Paramètre **de chaîne** facultatif.

  Spécifie le répertoire du journal de Tracker.

- **TreatLinkerWarningAsErrors**

  Paramètre **Boolean** optionnel.

  Si `true`, aucun fichier de sortie n’est créé lorsque l’Éditeur de liens génère un avertissement.

  Pour plus d’informations, consultez [/WX (Traiter les avertissements de l’éditeur de liens comme des erreurs)](/cpp/build/reference/wx-treat-linker-warnings-as-errors).

- **TurnOffAssemblyGeneration**

  Paramètre **Boolean** optionnel.

  Si `true`, crée une image du fichier de sortie actif sans générer un assembly .NET Framework.

  Pour plus d’informations, voir [/NOASSEMBLY (Créer un module MSIL)](/cpp/build/reference/noassembly-create-a-msil-module).

- **TypeLibraryFile**

  Paramètre **de chaîne** facultatif.

  Spécifie l’extension du nom de fichier et du fichier du fichier *.tlb.* Spécifiez un nom de fichier, ou un chemin d’accès et un nom de fichier.

  Pour plus d’informations, consultez [/TLBOUT (Nommer le fichier .tlb)](/cpp/build/reference/tlbout-name-dot-tlb-file).

- **TypeLibraryResourceID**

  Paramètre **entier** facultatif.

  Désigne une valeur spécifiée par l’utilisateur pour une bibliothèque de types créé par l’Éditeur de liens. Spécifiez une valeur comprise entre 1 et 65535.

  Pour plus d’informations, voir [/TLBID (Spécifier l’ID de ressources pour TypeLib)](/cpp/build/reference/tlbid-specify-resource-id-for-typelib).

- **UACExecutionLevel**

  Paramètre **de chaîne** facultatif.

  Spécifie le niveau d’exécution demandé pour l’application lorsqu’elle est exécutée avec le Contrôle de compte d’utilisateur.

  Spécifiez l'une des valeurs suivantes, chacune d'elles correspondant à une option de ligne de commande.

  - **CommeInvoker** - `level='asInvoker'`

  - **Le plus disponible** - `level='highestAvailable'`

  - **ExigerAdministrator** - `level='requireAdministrator'`

  Pour plus d’informations, consultez l’argument `level` dans l’article [/MANIFESTUAC (Incorporer des informations sur le contrôle de compte d’utilisateur dans le manifeste)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).

- **UACUIAccess**

  Paramètre **Boolean** optionnel.

  Si `true`, l’application ignore les niveaux de protection de l’interface utilisateur et exécute l’entrée vers des fenêtres d’autorisations supérieures sur le Bureau. Dans le cas contraire, `false`.

  Pour plus d’informations, consultez l’argument `uiAccess` dans l’article [/MANIFESTUAC (Incorporer des informations sur le contrôle de compte d’utilisateur dans le manifeste)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).

- **UseLibraryDependencyInputs**

  Paramètre **Boolean** optionnel.

  Si `true`, les entrées de l’outil Générateur de bibliothèques sont utilisées à la place du fichier bibliothèque lors de la liaison des sorties de bibliothèque des dépendances du projet.

- **Version**

  Paramètre **de chaîne** facultatif.

  Insère un numéro de version dans l’en-tête du fichier *.exe* ou *.dll*. Spécifiez « `major[.minor]` ». Les arguments `major` et `minor` sont des nombres décimaux compris entre 0 et 65535.

  Pour plus d’informations, voir [/VERSION (Informations version)](/cpp/build/reference/version-version-information).

## <a name="see-also"></a>Voir aussi

- [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)
