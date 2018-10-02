---
title: Propriétés de fichier, JavaScript | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- javascript.project.property.expandedsdknode.fileversion
- javascript.project.property.expandedsdknode.uri
- javascript.project.property.expandedsdknode.filename
- javascript.project.property.reference.description
- javascript.project.property.reference.specificversion
- javascript.project.property.reference.identity
- javascript.project.property.fullpath
- javascript.project.property.packageaction
- javascript.project.property.reference.package
- javascript.project.property.copytooutputdirectory
- javascript.project.property.expandedsdknode.sdkpath
- javascript.project.property.reference.filetype
- javascript.project.property.reference.culture
- javascript.project.property.filename
- javascript.project.property.reference.resolvedpath
- javascript.project.property.reference.version
ms.assetid: 085913b8-a97b-45f7-85fa-bbb0902f3ee9
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fb3f9dcef138bdb9e0452eb1b739dca652d0844d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47494652"
---
# <a name="file-properties-javascript"></a>Propriétés des fichiers, JavaScript
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [propriétés du fichier, JavaScript](https://docs.microsoft.com/visualstudio/ide/reference/file-properties-javascript).  
  
  
Vous pouvez utiliser les propriétés de fichier pour indiquer les actions que le système de projet doit effectuer sur les fichiers. Par exemple, vous pouvez définir des propriétés de fichier pour indiquer si un fichier doit être ajouté au package en tant que fichier de ressources.  
  
 Vous pouvez sélectionner n’importe quel fichier dans l’Explorateur de solutions, puis examiner ses propriétés dans la fenêtre Propriétés. Les fichiers JavaScript ont quatre propriétés : **Copier dans le répertoire de sortie**, **Action de package**, **Nom de fichier** et **Chemin d’accès au fichier**.  
  
## <a name="file-properties"></a>Propriétés du fichier  
 Cette section décrit les propriétés communes aux fichiers JavaScript.  
  
### <a name="copy-to-output-directory-property"></a>Propriété Copier dans le répertoire de sortie  
 Cette propriété spécifie les conditions dans lesquelles le fichier source sélectionné doit être copié dans le répertoire de sortie. Sélectionnez **Ne pas copier** si le fichier ne doit jamais être copié dans le répertoire de sortie. Sélectionnez **Toujours copier** si le fichier doit toujours être copié dans le répertoire de sortie. Sélectionnez **Copier si plus récent** si le fichier doit être copié uniquement lorsqu’il est plus récent qu’un fichier existant du même nom dans le répertoire de sortie.  
  
### <a name="package-action"></a>Action de package  
 La propriété **Action de package** indique ce que Visual Studio doit faire avec un fichier lors de l’exécution d’une build. **Action de package** peut avoir l’une des valeurs suivantes :  
  
-   **Aucun** - Le fichier n’est pas inclus dans le manifeste du package. Exemple : un fichier texte qui contient de la documentation, tel qu’un fichier Lisez-moi.  
  
-   **Contenu** - Le fichier est inclus dans le manifeste du package. Par exemple, ce paramètre est la valeur par défaut pour un fichier .htm, .js, .css, image, audio ou vidéo.  
  
-   **Manifeste** : le fichier n’est pas inclus dans le manifeste du package. Au lieu de cela, le fichier est utilisé pour l’entrée lors de la génération du manifeste du package. Il s’agit de la valeur par défaut pour le fichier package.appxmanifest.  
  
-   **Ressource** - Le fichier n’est pas inclus dans le manifeste du package. Au lieu de cela, le contenu du fichier est indexé dans l’index de ressource de package qui est placé dans le manifeste du package. Il est généralement utilisé pour les fichiers de ressources.  
  
 La valeur par défaut d’**Action de package** dépend de l’extension du fichier que vous ajoutez à la solution.  
  
### <a name="file-name-property"></a>Propriété Nom de fichier  
 Affiche le nom de fichier sous la forme d’une valeur en lecture seule. Pour renommer le fichier, vous devez cliquer avec le bouton droit sur le fichier dans l’Explorateur de solutions et sélectionner **Renommer**.  
  
### <a name="full-path-property"></a>Propriété Chemin d’accès complet  
 Affiche le chemin complet du fichier sous la forme d’une valeur en lecture seule. Pour changer le chemin du fichier, vous pouvez faire glisser le fichier dans l’Explorateur de solutions.  
  
## <a name="reference-file-properties"></a>Propriétés de fichier de référence  
 Cette section décrit les propriétés communes aux fichiers référencés à partir d’une [!INCLUDE[win8_app_js](../../includes/win8-app-js-md.md)]. Lorsque vous sélectionnez une référence telle qu’un fichier .winmd, une référence SDK, une référence de projet à projet ou une référence d’assembly dans l’Explorateur de solutions, d’autres propriétés peuvent afficher dans la fenêtre Propriétés, en fonction du type de fichier.  
  
### <a name="culture"></a>Culture  
 Affiche la langue associée à la référence.  
  
### <a name="file-type"></a>Type de fichier  
 Type le type de fichier de la référence.  
  
### <a name="file-version"></a>Version du fichier  
 Affiche la version de fichier de la référence.  
  
### <a name="identity"></a>Identité  
 Affiche l’identité de la référence utilisée dans le projet, qui est stockée dans le fichier projet.  
  
### <a name="package"></a>Package  
 Affiche le nom du manifeste du package associé à la référence.  
  
### <a name="resolved-path"></a>Chemin résolu  
 Affiche le chemin de la référence qui est utilisée dans le projet.  
  
### <a name="sdk-path"></a>Chemin du SDK  
 Affiche le chemin du fichier du kit SDK référencé.  
  
### <a name="uri"></a>URI  
 Affiche l’URI doit être inclus dans les fichiers du projet HTML ou JavaScript pour inclure le fichier comme fichier source.  
  
### <a name="version"></a>Version  
 Affiche la version de la référence.  
  
## <a name="see-also"></a>Voir aussi  
 [NIB : Propriétés du projet (Visual Studio)](http://msdn.microsoft.com/en-us/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)



