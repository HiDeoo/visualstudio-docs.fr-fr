---
title: Microsoft Language Interface Packs (LIP) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-install
ms.topic: conceptual
helpviewer_keywords:
- text [Visual Studio], multiple languages
- Multilingual User Interface [Visual Studio]
- language switching [Visual Studio]
- MUI [Visual Studio]
- multiple language support [Visual Studio SDK]
- Windows Multilingual User Interface
- UI text language [Visual Studio]
- languages, multiple language support
ms.assetid: dc86304b-65b7-47e6-9314-1dfd02ecfa65
caps.latest.revision: 28
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: 503f97d1530f8d22184f42a2452046782a997c18
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "90839849"
---
# <a name="microsoft-language-interface-packs-lips-and-visual-studio"></a>Microsoft Language Interface Packs (LIP) et Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

En utilisant un Pack linguistique LIP (Language Interface Pack) Windows, vous pouvez installer une version linguistique de Windows, puis installer différents packs linguistiques d'interface utilisateur. Les packs linguistiques d'interface utilisateur fournissent une interface utilisateur traduite du système d'exploitation. Par exemple, vous pouvez installer un pack linguistique japonais sur une version anglaise de Windows, puis basculer la langue de l'interface utilisateur Windows entre le japonais et l'anglais. En utilisant des Packs linguistiques LIP, vous pouvez avoir plusieurs versions linguistiques de Windows sur un même ordinateur.

 Sur les ordinateurs où les Packs linguistiques LIP et plusieurs versions linguistiques de Visual Studio sont installés, la modification des paramètres de la langue d'affichage de Windows s'applique à la fois à Windows et à Visual Studio quand les modules linguistiques correspondants sont installés.

## <a name="limitations-of-multi-language-installations"></a>Limitations des installations multilingues
 Quand vous installez différentes versions linguistiques de Visual Studio sur le même ordinateur, vous pouvez basculer entre les langues seulement pour des éditions correspondantes. Par exemple, si vous avez installé une édition Express Edition en anglais, une édition Express Edition en allemand et une édition Professional Edition, vous pouvez basculer entre les langues des éditions Express Edition uniquement, mais pas celle de l'édition Professional Edition.

 Visual Studio utilise un module linguistique unifié. Pour installer plusieurs versions linguistiques de ces produits, vous devez d'abord installer un produit complet dans une langue, puis installer un ou plusieurs modules linguistiques.

> [!NOTE]
> Visual Studio ne prend pas en charge l'installation de plusieurs versions linguistiques du produit complet dans une langue sur le même ordinateur. Après avoir installé un produit complet dans une langue, vous devez ajouter des versions linguistiques en utilisant des modules linguistiques. Vous pouvez quand même installer plusieurs produits complets dans une langue des éditions Express Edition sur le même ordinateur.

### <a name="support-for-code-pages"></a>Prise en charge des pages de codes
 Certains outils Visual Studio n'affichent pas correctement le texte quand celui-ci contient des caractères qui ne sont pas dans la page de codes active. Des points d'interrogation apparaissent à la place ou bien le texte est endommagé. Les outils ou les zones suivants sont affectés :

- Sites déployés à l'aide de FTP.

- Noms d'ordinateurs non-ASCII dans certains contrôles.

- Outils en ligne de commande qui s'exécutent en dehors de Visual Studio.

- Assistant Migration de Visual Basic.

- ActiveX Control Test Container.

- Explorateur d'objets OLE/COM

- Outil de débogage web ISAPI.

- Projets d'application MFC ayant un contenu d'aide HTML.

- L'interface utilisateur de Visual SourceSafe / SCCI revient à l'anglais quand il existe une page de codes incompatible.

- Visual SourceSafe ne prend pas en charge les noms de fichiers Unicode.

- Les caractères définis par l'utilisateur final (zone d'utilisation privée) ne peuvent pas être utilisés en tant que jetons/identificateurs.

- Les caractères de type Latin étendu-B ne peuvent pas être affichés dans certaines fenêtres des outils Visual Studio quand la page de codes Windows est définie sur une langue d'Asie de l'Est.

- Les exécutions de texte constituées de caractères provenant de plusieurs scripts multilingues peuvent afficher le glyphe par défaut pour certains caractères.

- La copie et le collage de chaînes de script complexes dans des contrôles courants peuvent provoquer la perte de la mise en forme des caractères. Au lieu de cela, utilisez le clavier correspondant à la langue pour entrer le texte.

##### <a name="to-correctly-display-characters-that-are-not-included-in-the-current-code-page"></a>Pour afficher correctement les caractères qui ne sont pas inclus dans la page de codes active

1. Cliquez sur **Démarrer**, sur **Panneau de configuration**, puis ouvrez **Options régionales et linguistiques** (ou **Région** dans [!INCLUDE[win8](../includes/win8-md.md)]).

    > [!NOTE]
    > Vous devez être administrateur de l'ordinateur pour effectuer ces étapes.

2. Cliquez sur l’onglet **Avancé**.

3. Dans la liste **Select a language to match the language version of the non-Unicode programs you want to use** (Sélectionner une langue qui correspond à la version des programmes non-Unicode que vous voulez utiliser), sélectionnez la langue que vous utilisez actuellement.

4. Cliquez sur **OK**.

## <a name="changing-the-language-used-for-the-ui-text-in-visual-studio"></a>Changement de la langue utilisée pour le texte de l'interface utilisateur dans Visual Studio
 Quand vous installez plusieurs versions linguistiques de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] sur le même ordinateur, l’interface utilisateur de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] est par défaut **Identique à Microsoft Windows**. Ce paramètre indique que [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] affiche le texte de l’interface utilisateur dans la langue spécifiée comme langue d’affichage du système d’exploitation.

> [!NOTE]
> Si Visual Studio est configuré pour utiliser **Identique à Microsoft Windows** et que le module linguistique correspondant de Visual Studio n’est pas installé, Visual Studio utilise la langue de la première installation de Visual Studio.

#### <a name="to-set-the-language-that-is-used-for-the-ui-text-in-visual-studio"></a>Pour définir la langue utilisée pour le texte de l'interface utilisateur dans Visual Studio

1. Dans le menu **Outils** , cliquez sur **Options**.

2. Dans la boîte de dialogue **Options**, développez **Environnement**, puis cliquez sur **Paramètres internationaux**.

3. Dans la liste **Langue**, choisissez la langue dans laquelle le texte de l’interface utilisateur doit apparaître dans l’environnement de développement.

    Pour que le texte de l’interface utilisateur de l’IDE corresponde à la langue d’affichage définie pour le système d’exploitation, sélectionnez **Identique à Microsoft Windows**.

   Vous pouvez également utiliser la commande devenv pour définir la langue utilisée pour l'interface utilisateur. Pour plus d’informations, consultez [/LCID (devenv.exe)](../ide/reference/lcid-devenv-exe.md).

## <a name="see-also"></a>Voir aussi
 [Paramètres internationaux, Environnement, boîte de dialogue Options](../ide/reference/international-settings-environment-options-dialog-box.md)