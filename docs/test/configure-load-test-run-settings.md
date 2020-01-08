---
title: Configuration des paramètres d'exécution des tests de charge
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, configuring run settings
ms.assetid: 0c86918b-cd63-4468-8f49-6d547a1276dc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ffc9d6c2e563fcd16a61e91eaa94889de8607efc
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75595980"
---
# <a name="configure-load-test-run-settings"></a>Configurer les paramètres d’exécution des tests de charge

Les *paramètres d’exécution* sont un jeu de propriétés qui influencent la manière dont un test de charge est exécuté. Les paramètres d’exécution sont classés par catégories dans la fenêtre **Propriétés**.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

Vous pouvez avoir plusieurs paramètres d’exécution dans un test de charge, mais un seul des paramètres d’exécution peut être actif par exécution. Les autres paramètres d'exécution fournissent un moyen rapide de sélectionner un paramètre utilisable avec les séries de tests suivantes.

Les paramètres d’exécution initiaux sont définis quand vous créez un test de charge à l’aide de l’**Assistant Nouveau test de charge**.

![Paramètres d'exécution du test de charge](../test/media/loadtestrunsettings.png)

## <a name="tasks"></a>Tâches

|Tâches|Rubriques associées|
|-|-|
|**Ajouter davantage de paramètres d’exécution à votre test de charge :** en plus du paramètre d’exécution créé quand vous exécutez **l’Assistant Nouveau test de charge**, vous pouvez ajouter davantage de paramètres d’exécution à votre test de charge pour pouvoir exécuter le test dans différentes conditions.|-   [Guide pratique pour ajouter des paramètres d’exécution supplémentaires à un test de charge](../test/how-to-add-additional-run-settings-to-a-load-test.md)|
|**Spécifier le paramètre d’exécution actif à utiliser avec le test de charge :** vous pouvez sélectionner le paramètre d’exécution à utiliser avec votre test de charge à l’aide de l’éditeur de test de charge. Le paramètre d'exécution actif est identifié par le suffixe « [Actif] ».|-   [Guide pratique pour sélectionner le paramètre d’exécution actif d’un test de charge](../test/how-to-select-the-active-run-setting-for-a-load-test.md)|
|**Modifier les propriétés des paramètres d’exécution :** vous pouvez modifier les propriétés de vos paramètres d’exécution, par exemple, pour les options de journalisation (voir ci-dessous) qui déterminent la longueur du test, la durée de préparation, le nombre maximal de détails relatifs aux erreurs signalés, le taux d’échantillonnage, le modèle de connexion (tests de performances web uniquement), le type de stockage des résultats, le niveau de validation et le traçage SQL. Les paramètres d'exécution doivent refléter les objectifs de votre test de charge.|-   [Propriétés des paramètres d’exécution du test de charge](../test/load-test-run-settings-properties.md)<br />-   [Changement des propriétés des paramètres d’exécution](../test/load-test-run-settings-properties.md#change-run-setting-properties)|
|**Spécifier le nombre d’itérations de tests dans les paramètres de série de tests de charge :** vous pouvez spécifier le nombre d’exécutions de tous les tests unitaires et tests de performances web dans l’ensemble des scénarios des tests de charge en configurant la propriété **Itérations de tests**.|-   [Guide pratique pour spécifier le nombre d’itérations de tests dans un paramètre d’exécution](../test/how-to-specify-the-number-of-test-iterations-in-a-load-test.md)|
|**Spécifier le taux d’échantillonnage d’un paramètre d’exécution du test de charge :** vous pouvez spécifier la fréquence à laquelle le test de charge collecte les données des compteurs de performances en configurant la propriété **Taux d’échantillonnage**.|-   [Guide pratique pour spécifier le taux d’échantillonnage](../test/how-to-specify-the-sample-rate-for-a-load-test.md)|
|**Spécifier l’option de stockage des détails de minuterie :** vous pouvez spécifier le mode d’enregistrement des détails du test de charge en configurant la propriété **Stockage des détails de minuterie**.|-   [Guide pratique pour spécifier la propriété de stockage des détails de minuterie](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md)|
|**Spécifier la période de rétention des ressources de test :** accélérez le cycle test > correction > nouveau test en conservant les ressources de test pendant une période donnée à l’aide de la propriété **Délai de rétention des ressources**.|-   [Conserver les ressources pour accélérer le test de charge](/azure/devops/test/load-test/getting-started-with-performance-testing?view=vsts)|
|**Utiliser des paramètres de contexte :** vous pouvez utiliser des paramètres de contexte pour paramétrer une chaîne. Par exemple, si votre test de charge contient un test de performances web qui utilise un serveur web paramétrable, vous pouvez ajouter aux paramètres d’exécution un paramètre de contexte mappé avec un autre serveur.|-   [Guide pratique pour ajouter des paramètres de contexte à un paramètre d’exécution](../test/how-to-add-context-parameters-to-a-load-test-run-setting.md)|
|**Configuration des propriétés de journalisation des tests :** vous pouvez configurer la fréquence d’écriture des données dans le journal associé aux paramètres d’exécution des tests de charge. Cela peut être important lorsque vous exécutez un test de charge volumineux ou complexe parce que le journal peut atteindre plusieurs gigaoctets.<br /><br /> Vous pouvez également définir l'enregistrement automatique du fichier journal lorsque votre test de charge ne permet pas de déboguer et d'analyser votre application.|-   [Modification des paramètres de journalisation du test de charge](../test/modify-load-test-logging-settings.md)|
