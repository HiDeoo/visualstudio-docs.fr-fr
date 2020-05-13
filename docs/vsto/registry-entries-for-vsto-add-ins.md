---
title: Inscriptions au registre des add-ins VSTO
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- LoadBehavior entry
- add-ins [Office development in Visual Studio], registry entries
- registry keys [Office development in Visual Studio]
- application-level add-ins [Office development in Visual Studio], registry entries
- registry entries [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b02b50c42692ec2fd455358df5157e0b8481562b
ms.sourcegitcommit: b32fbbcbc43910b0ed7ce79aa9a22f2ed36ab57e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79416521"
---
# <a name="registry-entries-for-vsto-add-ins"></a>Inscriptions au registre des add-ins VSTO
  Vous devez créer un ensemble spécifique d'entrées de Registre quand vous déployez des compléments VSTO créés à l'aide de Visual Studio. Ces entrées de Registre fournissent des informations qui permettent à l'application Microsoft Office de découvrir et de charger le complément VSTO.

 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]

[!include[Add-ins note](includes/addinsnote.md)]

 Quand vous générez votre projet, Visual Studio crée ces entrées de Registre sur l'ordinateur de développement pour que vous puissiez facilement exécuter et déboguer le complément VSTO. Si vous utilisez ClickOnce pour déployer votre add-in VSTO, les entrées du registre sont automatiquement créées sur l’ordinateur utilisateur final. Si vous utilisez Windows Installer pour déployer votre add-in VSTO, vous devez configurer le projet InstallShield Limited Edition pour créer les entrées de registre sur l’ordinateur utilisateur final.

 Pour plus d’informations sur la façon dont les entrées de Registre sont utilisées pendant le processus de chargement des compléments VSTO, consultez [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md).

> [!NOTE]
> Dans cette rubrique, le texte *ID du complément* représente l'ID unique de votre complément VSTO. Par défaut, l'ID est le nom de l'assembly de votre complément VSTO.

## <a name="register-vsto-add-ins-for-the-current-user-vs-all-users"></a>Enregistrez les add-ins VSTO pour l’utilisateur actuel par rapport à tous les utilisateurs
 Quand un complément VSTO est installé, il peut être inscrit de deux façons :

- Pour l’utilisateur actuel seulement (c’est-à-dire, il n’est disponible que pour l’utilisateur qui est connecté à l’ordinateur lorsque l’Add-in VSTO est installé). Dans ce cas, les entrées de registre sont créées sous le **HKEY_CURRENT_USER**.

- Pour tous les utilisateurs (c’est-à-dire que tout utilisateur qui se connecte à l’ordinateur peut utiliser l’add-in VSTO). Dans ce cas, les entrées du registre sont créées sous **HKEY_LOCAL_MACHINE**.

  Tous les compléments VSTO que vous créez à l'aide de Visual Studio peuvent être inscrits pour l'utilisateur actuel. En revanche, ils ne peuvent être inscrits pour tous les utilisateurs que dans certains scénarios particuliers. Ces scénarios dépendent de la version de Microsoft Office installée sur l'ordinateur et de la façon dont le complément VSTO a été déployé.

### <a name="deployment-type"></a>Type de déploiement
 Si vous utilisez ClickOnce pour déployer un complément VSTO, ce dernier ne peut être inscrit que pour l'utilisateur actuel. C’est parce que ClickOnce ne prend en charge la création de clés sous **HKEY_CURRENT_USER**. Si vous voulez inscrire un complément VSTO pour tous les utilisateurs d'un ordinateur, vous devez déployer ce complément à l'aide de Windows Installer. Pour plus d’informations sur ces types de déploiement, consultez [la solution Deploy an Office en utilisant ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md) et [Déployez une solution Office en utilisant Windows Installer](../vsto/deploying-a-vsto-solution-by-using-windows-installer.md).

## <a name="registry-entries"></a>Entrées du Registre
 Les entrées de registre d’add-in VSTO requises sont situées sous les clés de registre suivantes où *Root* est **HKEY_CURRENT_USER** ou **HKEY_LOCAL_MACHINE** selon si l’installation est pour l’utilisateur actuel ou tous les utilisateurs.

|Demande de bureau|Chemin d'accès de configuration|
|------------------|------------------|
|Visio|*Root*'Software’Microsoft\\*Visio*\\'Addins*add-in ID*|
|Tous les autres|*Root*\\'Software’Microsoft’Office nom de\\*l’application*'Addins*add-in ID*|

> [!NOTE]
> Si l’installateur cible tous les utilisateurs sur Windows 64 bits, il est recommandé qu’il inclut deux entrées de registre,\\l’une sous le HKEY_LOCAL_MACHINE-Software-Microsoft et l’autre sous la ruche**HKEY_LOCAL_MACHINE-Software WOW6432Node**Microsoft. C’est parce qu’il est possible pour les utilisateurs d’utiliser soit 32 bits ou 64 bits versions de Office sur l’ordinateur.
>
>Si l’installateur cible l’utilisateur actuel, il n’a pas besoin d’installer à la WOW6432Node parce que le chemin HKEY_CURRENT_USER logiciel est partagé.
>
>Pour plus d’informations, veuillez consulter [les données d’application 32 et 64 bits dans le Registre](/windows/win32/sysinfo/32-bit-and-64-bit-application-data-in-the-registry)

 Le tableau suivant répertorie les entrées sous cette clé de Registre.

|Entrée|Type|Valeur|
|-----------|----------|-----------|
|**Description**|REG_SZ|Obligatoire. Brève description du complément VSTO.<br /><br /> Cette description s'affiche quand l'utilisateur sélectionne le complément VSTO dans le volet **Compléments** de la boîte de dialogue **Options** de l'application Microsoft Office.|
|**Friendlyname**|REG_SZ|Obligatoire. Nom descriptif du complément VSTO qui s'affiche dans la boîte de dialogue **Compléments COM** de l'application Microsoft Office. La valeur par défaut est l'ID du complément VSTO.|
|**LoadBehavior**|REG_DWORD|Obligatoire. Valeur qui spécifie le moment où l'application tente de charger le complément VSTO, ainsi que l'état actuel du complément VSTO (chargé ou non chargé).<br /><br /> Par défaut, cette entrée a la valeur 3, ce qui indique que le complément VSTO est chargé au démarrage. Pour plus d’informations, voir [les valeurs LoadBehavior](#LoadBehavior). **Note:**  Si un utilisateur désactive l’add-in VSTO, cette action modifie la valeur **LoadBehavior** dans la ruche de registre **HKEY_CURRENT_USER.** Pour chaque utilisateur, la valeur de la valeur **LoadBehavior** dans la ruche HKEY_CURRENT_USER remplace le **LoadBehavior** par défaut défini dans la **ruche HKEY_LOCAL_MACHINE.**|
|**Manifest**|REG_SZ|Obligatoire. Chemin d'accès complet du manifeste de déploiement du complément VSTO. Le chemin d'accès peut être un emplacement sur l'ordinateur local, un partage réseau (UNC) ou un serveur web (HTTP).<br /><br /> Si vous utilisez Windows Installer pour déployer la solution, vous devez ajouter le préfixe **file:///** au chemin d'accès du **manifeste** . Vous devez également ajouter la chaîne **&#124;vstolocal (c’est-à-dire,** le caractère de pipe **&#124;** suivie par **vstolocal**) à la fin de ce chemin. Cela permet de garantir que votre solution est chargée à partir du dossier d'installation, et non à partir du cache ClickOnce. Pour plus d’informations, voir [Déployez une solution Office en utilisant Windows Installer](../vsto/deploying-a-vsto-solution-by-using-windows-installer.md). **Note:**  Lorsque vous créez un add-in VSTO sur l’ordinateur de développement, Visual Studio joint automatiquement la **chaîne vstolocal&#124;** à cette entrée de registre.|

### <a name="registry-entries-for-outlook-form-regions"></a><a name="OutlookEntries"></a>Inscriptions au registre des régions de formulaire Outlook
 Si vous créez une zone de formulaire personnalisée dans un complément VSTO pour Outlook, des entrées de Registre supplémentaires sont utilisées pour inscrire la zone de formulaire dans Outlook. Ces entrées sont créées sous une autre clé de Registre pour chaque classe de message prise en charge par la zone de formulaire. Ces clés de registre sont à l’endroit suivant, où *Root* est **HKEY_CURRENT_USER** ou **HKEY_LOCAL_MACHINE**.

 *Root*'Software’Microsoft’Office’Outlook’FormRegions\\*classe de messagerie*

 Comme pour les autres entrées de Registre partagées par l'ensemble des compléments VSTO, Visual Studio crée les entrées de Registre de zones de formulaire sur l'ordinateur de développement au moment où vous générez votre projet. Si vous utilisez ClickOnce pour déployer votre add-in VSTO, les entrées du registre sont automatiquement créées sur l’ordinateur utilisateur final. Si vous utilisez Windows Installer pour déployer votre add-in VSTO, vous devez configurer le projet InstallShield Limited Edition pour créer les entrées de registre sur l’ordinateur utilisateur final.

 Pour plus d’informations sur les entrées de registre de région de formulaire, voir [Spécifier l’emplacement d’une région de forme sous une forme personnalisée](/office/vba/outlook/Concepts/Creating-Form-Regions/specify-the-location-of-a-form-region-in-a-custom-form). Pour plus d’informations sur les régions de formulaire Outlook, voir [Create Outlook former regions](../vsto/creating-outlook-form-regions.md).

## <a name="loadbehavior-values"></a><a name="LoadBehavior"></a>Valeurs LoadBehavior
 **L’entrée LoadBehavior** sous le nom\\*d’application*\\ *Root*'Software’Microsoft’Office 'Addins*addins add-in ID* key contient une combinaison bitwise de valeurs qui spécifient le comportement de temps d’exécution de l’Add-in VSTO. Le bit d'ordre le plus bas (valeurs 0 et 1) indique si le complément VSTO est actuellement chargé ou non chargé. Les autres bits indiquent le moment où l'application tente de charger le complément VSTO.

 En règle générale, **l’entrée LoadBehavior** est destinée à être réglée à 0, 3 ou 16 (en décimale) lorsque l’add-in VSTO est installé sur les ordinateurs de l’utilisateur final. Par défaut, Visual Studio affecte la valeur 3 à l'entrée **LoadBehavior** du complément VSTO quand vous le générez ou que vous le publiez.

 Le tableau suivant répertorie toutes les valeurs possibles de l'entrée **LoadBehavior** . Certaines descriptions de ce tableau font référence au chargement manuel ou par programmation d'un complément VSTO. Pour charger un complément VSTO manuellement, cochez la case à côté du complément VSTO dans la boîte de dialogue **Compléments COM** de l'application. Pour charger un complément VSTO par programmation, affectez à la propriété <xref:Microsoft.Office.Core.COMAddIn.Connect%2A> de l'objet <xref:Microsoft.Office.Core.COMAddIn> qui représente ce complément la valeur **true**.

|Valeur (au format décimal)|État du complément VSTO|Comportement de chargement du complément VSTO|Description|
|--------------------------|-------------------------|--------------------------------|-----------------|
|0|Unloaded|Ne pas charger automatiquement|L'application ne tente jamais de charger le complément VSTO automatiquement. L'utilisateur peut essayer de charger manuellement le complément VSTO. Sinon, le complément VSTO peut être chargé par programmation.<br /><br /> Si le complément VSTO est correctement chargé, la valeur **LoadBehavior** reste 0, mais l'état du complément VSTO dans la boîte de dialogue **Compléments COM** est mis à jour pour indiquer que ce complément est chargé.|
|1|Loaded|Ne pas charger automatiquement|L'application ne tente jamais de charger le complément VSTO automatiquement. L'utilisateur peut essayer de charger manuellement le complément VSTO. Sinon, le complément VSTO peut être chargé par programmation.<br /><br /> Bien que la boîte de dialogue **COM Add-ins** indique que l’add-in VSTO est chargé après le début de l’application, l’Add-in VSTO n’est pas chargé jusqu’à ce qu’il soit chargé manuellement ou programmatiquement.<br /><br /> Si l'application charge correctement le complément VSTO, la valeur de **LoadBehavior** passe à 0, et reste à 0 après la fermeture de l'application.|
|2|Unloaded|Charger au démarrage|L'application ne tente pas de charger le complément VSTO automatiquement. L'utilisateur peut essayer de charger manuellement le complément VSTO. Sinon, le complément VSTO peut être chargé par programmation.<br /><br /> Si l'application charge correctement le complément VSTO, la valeur de **LoadBehavior** passe à 3, et reste à 3 après la fermeture de l'application.|
|3|Loaded|Charger au démarrage|L'application tente de charger le complément VSTO au démarrage de l'application. Il s'agit de la valeur par défaut quand vous générez ou que vous publiez un complément VSTO dans Visual Studio.<br /><br /> Si l'application charge correctement le complément VSTO, la valeur de **LoadBehavior** reste égale à 3. Si une erreur se produit lors du chargement du complément VSTO, la valeur de **LoadBehavior** passe à 2, et reste à 2 après la fermeture de l'application.|
|8|Unloaded|Charger à la demande|L'application ne tente pas de charger le complément VSTO automatiquement. L'utilisateur peut essayer de charger manuellement le complément VSTO. Sinon, le complément VSTO peut être chargé par programmation.<br /><br /> Si l'application charge correctement le complément VSTO, la valeur de **LoadBehavior** passe à 9.|
|9|Loaded|Charger à la demande|Le complément VSTO est chargé seulement quand l'application le requiert, par exemple quand un utilisateur clique sur un élément d'interface utilisateur qui utilise des fonctionnalités du complément VSTO (par exemple un bouton personnalisé dans le ruban).<br /><br /> Si l'application charge correctement le complément VSTO, la valeur de **LoadBehavior** reste 9, mais l'état de ce complément dans la boîte de dialogue **Compléments COM** est mis à jour pour indiquer que le complément VSTO est actuellement chargé. Si une erreur se produit lors du chargement du complément VSTO, la valeur de **LoadBehavior** passe à 8.|
|16|Loaded|Charger la première fois, puis charger à la demande|Définissez cette valeur si vous voulez que votre complément VSTO soit chargé à la demande. L'application charge le complément VSTO quand l'utilisateur exécute l'application pour la première fois. La prochaine fois que l'utilisateur exécute l'application, cette dernière charge tous les éléments d'interface utilisateur définis par le complément VSTO. Toutefois, le complément VSTO n'est pas chargé tant que l'utilisateur n'a pas cliqué sur un élément d'interface utilisateur associé à ce complément.<br /><br /> Quand l'application charge correctement le complément VSTO pour la première fois, la valeur de **LoadBehavior** reste 16 durant le chargement de ce complément. Après la fermeture de l'application, la valeur **LoadBehavior** passe à 9.|

## <a name="see-also"></a>Voir aussi
- [Architecture des solutions Office en Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)
- [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md)
- [Construire des solutions Office](../vsto/building-office-solutions.md)
- [Déployer une solution Office](../vsto/deploying-an-office-solution.md)
 