---
title: Configurations et plateformes pour les tests codés de l’interface utilisateur
ms.date: 10/04/2015
ms.topic: reference
helpviewer_keywords:
- coded UI tests
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: df0955cc86ef3b57885234fe4e7b1a52fa37f950
ms.sourcegitcommit: 1c8e07b98fc0a44b5ab90bcef77d9fac7b3eb452
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2019
ms.locfileid: "56796567"
---
# <a name="supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings"></a>Plateformes et configurations prises en charge pour les tests codés de l’interface utilisateur et les enregistrements des actions

Les plateformes et configurations prises en charge pour les tests codés de l’interface utilisateur pour Visual Studio Enterprise sont indiquées dans le tableau suivant. Ces configurations s’appliquent aussi aux enregistrements d’actions créés à l’aide de [!INCLUDE[MTRlong](../test/includes/mtrlong_md.md)].

> [!NOTE]
> Le processus de test codé de l’interface utilisateur doit avoir les mêmes privilèges que l’application testée.

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

**Spécifications**

-   Visual Studio Enterprise

## <a name="supported-configurations"></a>Configurations prises en charge

| Configuration | Prise en charge |
|-| - |
| Systèmes d’exploitation | [!INCLUDE[win7](../debugger/includes/win7_md.md)]<br /><br /> [!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)]<br /><br /> [!INCLUDE[win8](../debugger/includes/win8_md.md)]<br /><br /> Windows 10 |
| Prise en charge des éditions 32 bits et 64 bits | Windows 32 bits exécutant [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] 32 bits permet de tester les applications 32 bits.<br /><br /> Windows 64 bits exécutant [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] 32 bits permet de tester les applications WOW 32 bits qui sont dotées de la fonctionnalité de synchronisation d’interface utilisateur.<br /><br /> Windows 64 bits exécutant [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] 32 bits permet de tester les applications Windows Forms et WPF 64 bits qui ne sont pas dotées de la fonctionnalité de synchronisation d’interface utilisateur. |
| Architecture | x86 et x64 **Remarque :**  Internet Explorer n’est pas pris en charge en mode 64 bits, sauf en cas d’exécution sous [!INCLUDE[win8](../debugger/includes/win8_md.md)] ou versions ultérieures. |
| .NET | .NET 2.0, 3.0, 3.5, 4 et 4.5. **Remarque :** [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] et Visual Studio nécessitent tous les deux .NET 4 pour fonctionner. Cependant, les applications développées à l’aide des versions .NET répertoriées sont prises en charge. |

> [!NOTE]
> La*synchronisation d’interface utilisateur* est une fonctionnalité permettant de vérifier la lecture dans la file d’attente de messages de chaque contrôle. Si un contrôle ne répond pas à l’événement qui lui a été envoyé, l’événement est envoyé une nouvelle fois.


## <a name="platform-support"></a>Plateforme prise en charge

| Plateforme | Niveau de prise en charge |
|-| - |
| Applications Windows Phone | Seules les applications Windows Phone XAML WinRT sont prises en charge. |
| Applications UWP | Seules les applications UWP en XAML sont prises en charge. |
| Applications de la plateforme Windows universelle | Seules les applications de la plateforme Windows universelle XAML pour téléphone et Bureau sont prises en charge. |
| Microsoft Edge | L’enregistrement des étapes d’action ou l’utilisation du générateur pour afficher les propriétés des objets n’est pas pris en charge. Les tests peuvent être lus dans le navigateur Edge, à l’aide de Visual Studio 2015 Update 2 (et versions ultérieures) via l’[extension de test codé de l’interface utilisateur pour navigateurs multiples](https://marketplace.visualstudio.com/items?itemName=AtinBansal.SeleniumcomponentsforCodedUICrossBrowserTesting). |
| Internet Explorer 8<br /><br /> Internet Explorer 9<br /><br /> Internet Explorer 10 **Important :**  Internet Explorer 10 est pris en charge uniquement sur le Bureau. <br /><br /> Internet Explorer 11 **Important :**  Internet Explorer 11 est pris en charge uniquement sur le Bureau. | Prise en charge intégrale.<br /><br /> -   **Prise en charge de HTML5 dans Internet Explorer 9 et Internet Explorer 10 :** Les tests codés de l’interface utilisateur prennent en charge l’enregistrement, la lecture et la validation des contrôles HTML5 suivants : Audio, Video, ProgressBar et Slider. Pour plus d’informations, consultez [Utilisation de contrôles HTML5 dans des tests codés de l’interface utilisateur](../test/using-html5-controls-in-coded-ui-tests.md). **Avertissement :**      Si vous créez des tests codés d’une interface utilisateur dans Internet Explorer 10, il est possible qu'ils ne s’exécutent pas avec Internet Explorer 9 ou Internet Explorer 8. Cela tient au fait qu’Internet Explorer 10 inclut les contrôles HTML5 tels que Audio, Video, ProgressBar et Slider. Ces contrôles HTML5 ne sont pas reconnus par Internet Explorer 9 ni Internet Explorer 8. De même, votre test codé de l’interface utilisateur avec Internet Explorer 9 peut inclure certains contrôles HTML5 qui ne seront pas non plus reconnus dans Internet Explorer 8.<br />-   **Prise en charge de la vérification de l’orthographe dans Internet Explorer 10 :** Internet Explorer 10 inclut des fonctions de vérification de l’orthographe pour toutes les zones de texte. Cette fonction vous permet d’accéder à une liste de corrections suggérées. Les tests codés de l’interface utilisateur ignorent certaines actions utilisateur, telles que la sélection d’une autre suggestion d’orthographe. Seul le texte final tapé dans la zone de texte est enregistré.<br />     Les actions suivantes qui utilisent le contrôle de vérification de l’orthographe sont enregistrées pour le test codé d’IU : Ajouter au dictionnaire, Copier, Sélectionner tout, Ajouter au dictionnaire et Ignorer.<br />-   **Prise en charge d’Internet Explorer 64 bits exécuté sur Windows 8 :** auparavant, les versions 64 bits d’Internet Explorer n’étaient pas prises en charge pour l’enregistrement et la lecture. Avec [!INCLUDE[win8](../debugger/includes/win8_md.md)] et [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], les tests codés de l’interface utilisateur ont été activés pour les versions 64 bits de Microsoft Internet Explorer. **Avertissement :**      La prise en charge 64 bits de Microsoft Internet Explorer s’applique uniquement quand vous exécutez [!INCLUDE[win8](../debugger/includes/win8_md.md)] ou version ultérieure.<br />-   **Prise en charge des sites épinglés dans Internet Explorer 9 :** dans Internet Explorer 9, les sites épinglés ont été introduits. Avec les sites épinglés, vous pouvez accéder à vos sites favoris directement à partir de la barre des tâches Windows, sans devoir ouvrir Internet Explorer au préalable. Les tests codés de l’interface utilisateur peuvent maintenant générer des actions avec intention sur les sites épinglés. Pour plus d’informations sur les sites épinglés, consultez [Sites épinglés](http://go.microsoft.com/fwlink/?LinkId=220037).<br />-   **Prise en charge des balises sémantiques d’Internet Explorer 9 :** Internet Explorer 9 a introduit les balises sémantiques suivantes : section, nav, article, aside, hgroup, header, footer, figure, figcaption et mark. Les tests codés de l’interface utilisateur ignorent toutes ces balises sémantiques pendant l’enregistrement. Vous pouvez ajouter des assertions sur ces balises à l’aide du générateur de test codé de l’interface utilisateur. Vous pouvez utiliser le bouton de navigation dans le générateur de test codé de l’interface utilisateur pour accéder à l’un de ces éléments et afficher leurs propriétés.<br />-   **Gestion transparente des caractères d’espace blanc entre les différentes versions d’Internet Explorer :** il existe des différences dans la gestion des caractères d’espace blanc entre Internet Explorer 8, Internet Explorer 9 et Internet Explorer 10. Les tests codés de l’interface utilisateur gèrent ces différences en toute transparence. Par conséquent, un test codé de l’interface utilisateur créé dans Internet Explorer 8, par exemple, sera lu correctement dans Internet Explorer 9 et Internet Explorer 10.<br />-   **La zone de notification d’Internet Explorer est désormais enregistrée avec l’attribut « Continuer en cas d’erreur » défini :** toutes les actions dans la zone de notification d’Internet Explorer sont désormais enregistrées avec l’attribut « Continuer en cas d’erreur » défini. Si la barre de notification n’apparaît pas pendant la lecture, les actions la concernant sont ignorées et le test codé de l’interface utilisateur continue avec l’action suivante. |
| Contrôles tiers Windows Forms et WPF | Prise en charge intégrale.<br /><br /> Pour activer des contrôles tiers dans Windows Forms et dans les applications WPF, vous devez ajouter des références et du code. Pour plus d’informations, consultez [Activer le test codé de l’interface utilisateur de vos contrôles](../test/enable-coded-ui-testing-of-your-controls.md). |
| Internet Explorer 6<br /><br /> Internet Explorer 7 | Non pris en charge. |
| Chrome<br /><br /> Firefox | L’enregistrement des étapes d’action n’est pas pris en charge. Les tests codés de l’interface utilisateur peuvent être lus sur les navigateurs Chrome et Firefox avec Visual Studio 2012 Update 4 ou version ultérieure. Cliquez [ici](using-different-web-browsers-with-coded-ui-tests.md) pour plus d’informations. |
| Opera<br /><br /> Safari | Non pris en charge. |
| Silverlight | Non pris en charge.<br /><br /> Cependant, pour Visual Studio 2013, vous pouvez télécharger le [plug-in de test codé de l’interface utilisateur Microsoft Visual Studio 2013 pour Silverlight](https://go.microsoft.com/fwlink/?LinkId=691026) à partir de la galerie Visual Studio. |
| Flash/Java | Non pris en charge. |
| Windows Forms 2.0 et versions ultérieures | Prise en charge intégrale. **Remarque :**  Les contrôles NetFx sont entièrement pris en charge ; en revanche, certains contrôles tiers ne sont pas pris en charge. |
| WPF 3.5 et versions ultérieures | Prise en charge intégrale.<br /><br /> **Remarque** Les contrôles NetFx sont entièrement pris en charge ; en revanche, certains contrôles tiers ne sont pas pris en charge. |
| Windows Win32 | Peut fonctionner en générant des problèmes connus, mais n’est pas officiellement pris en charge. |
| MFC | Prise en charge partielle. Consultez [Infrastructure UITest](https://blogs.msdn.microsoft.com/vstsqualitytools/2010/04/15/uitest-framework-mfc-support-in-vs-2010/) pour plus d’informations sur les fonctionnalités prises en charge. |
| SharePoint | Prise en charge intégrale. |
| Applications clientes Office | Non pris en charge. |
| Client web Dynamics CRM | Prise en charge intégrale. |
| Client Dynamics (Ax) 2012 | L’enregistrement et la lecture des actions sont partiellement pris en charge. Pour plus d’informations, consultez [Interface utilisateur codée Visual Studio 10/Prise en charge de l’enregistrement pour Microsoft Dynamics](https://blogs.msdn.microsoft.com/dave_froslie/2011/09/01/visual-studio-10-coded-ui-action-recordings-support-for-microsoft-dynamics-ax-2012/). |
| SAP | Non pris en charge. |
| Citrix/Services Terminal Server | Nous vous déconseillons d’enregistrer des actions sur un serveur Terminal Server. L’enregistreur ne prend pas en charge l’exécution simultanée de plusieurs instances. |
| PowerBuilder | Prise en charge partielle.<br /><br /> La prise en charge de l’accessibilité étendue est activée pour les contrôles PowerBuilder. |

 Pour plus d’informations sur la création d’extensions prenant en charge d’autres plateformes, consultez [Activer le test codé de l’interface utilisateur de vos contrôles](../test/enable-coded-ui-testing-of-your-controls.md) et [Étendre les tests codés de l’interface utilisateur et les enregistrements des actions](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md).

## <a name="see-also"></a>Voir aussi

- [Utiliser l’automatisation de l’interface utilisateur pour tester votre code](../test/use-ui-automation-to-test-your-code.md)
