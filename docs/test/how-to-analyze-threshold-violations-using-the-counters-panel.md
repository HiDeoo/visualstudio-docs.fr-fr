---
title: Violations de seuil pour les tests de charge dans Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, threshold violations
ms.assetid: 0126d7b7-0538-4ea9-9046-6556654b3b9d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: cb64626034c8c9bf03875385a80ebc417bf05dcb
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204061"
---
# <a name="how-to-analyze-threshold-violations-using-the-counters-panel-in-load-test-analyzer"></a>Guide pratique pour analyser les violations de seuils dans le volet Compteurs de l’analyseur de test de charge

Le volet **Compteurs** est visible dans la vue Graphiques et la vue Tables de l'**analyseur de test de charge** pendant l'exécution d'un test de charge, ou lorsque vous analysez un résultat de test de charge. Consultez [Analyser les résultats des tests de charge dans la vue Graphiques](../test/analyze-load-test-results-in-the-graphs-view.md), [Analyser les résultats des tests de charge et les erreurs dans la vue Tables](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) et [Guide pratique pour accéder aux résultats des tests de charge pour analyse](../test/how-to-access-load-test-results-for-analysis.md).

 Les violations de seuils sont associées à des compteurs de performance spécifiques, et indiquent que le compteur de performance a dépassé ou est descendu en dessous d'une valeur seuil définie. Les icônes du volet **Compteurs** indiquent les violations de seuil.

 ![Nœud d'ordinateur du panneau Compteur](../test/media/ltest_compnode.png)

 L’icône d’une violation de seuil est propagée du nœud d’arborescence dans lequel réside le compteur qui a échoué jusqu’au nœud racine. L’icône signale à l’utilisateur une violation sur un compteur qui n’est pas forcément visible dans l’arborescence, car cette dernière n’a pas été développée. Un exemple de l’icône est visible dans le **Nœud des ordinateurs** dans le volet **Compteurs** de l’illustration précédente.

 L'icône sera l'un des suivants :

 ![Aucune violation de seuil](../test/media/icon_ltest_1.gif) Aucune violation de seuil.

 ![Une violation de seuil critique dans le dernier intervalle](../test/media/icon_ltest_2.gif) Une violation de seuil critique s'est produite au cours du dernier intervalle.

 ![Une violation de seuil critique dans un intervalle précédant](../test/media/icon_ltest_3.gif) Une violation de seuil critique s'est produite au cours d'un intervalle précédent.

 ![Une violation de seuil d'avertissement dans le dernier intervalle](../test/media/icon_ltest_4.gif) Une violation de seuil d'avertissement s'est produite au cours du dernier intervalle.

 ![Une violation de seuil d'avertissement dans un intervalle précédant](../test/media/icon_ltest_5.gif) Une violation de seuil d'avertissement s'est produite au cours d'un intervalle précédent.

## <a name="to-analyze-threshold-violations-in-the-counters-panel"></a>Pour analyser les violations de seuils dans le volet des compteurs

1.  Après avoir effectué un test de charge, ou après avoir chargé un résultat de test, dans la barre d’outils de l’analyseur de test de charge, choisissez **Graphiques** ou **Tables**.

     Le volet des **compteurs** s’affiche dans la vue Graphiques ou la vue Tables.

2.  Si le volet **Compteurs** n’est pas visible, choisissez **Afficher le volet Compteurs** dans la barre d’outils.

     Tous les nœuds qui contiennent des violations de seuils incluent l'une des icônes répertoriées ci-dessus.

3.  Développez le nœud qui contient une icône de seuil, comme le nœud **Ordinateurs**, comme l’indique l’illustration précédente intitulée « Nœud des ordinateurs dans le volet des compteurs avec violation de seuil ». Continuez à développer le nœud jusqu’au compteur de performance avec la violation de seuil. Par exemple, l’illustration montre l’instance non réussie de **Microsoft Virtual Machine Failed Bus Network Adapter**.

4.  (Facultatif) Cliquez avec le bouton droit sur le compteur de performance avec la violation de seuil et sélectionnez l'une des options suivantes :

    -   **Afficher le compteur sur le graphique** : Dans la vue Graphiques, le compteur de performances est ajouté et mis en surbrillance sur le graphique sélectionné. Pour plus d’informations, consultez [Guide pratique pour ajouter et supprimer des compteurs sur des graphiques](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md).

        > [!NOTE]
        > Les icônes de la violation du seuil peuvent également être affichées sur le graphique dans la vue Graphiques. L'icône de seuil apparaît sur le graphique à côté du point de données où la violation de seuil s'est produite. Pour cela, choisissez la liste déroulante **Afficher la légende** dans la barre d’outils et sélectionnez **Afficher les violations de seuils sur le graphique**.

    -   **Afficher le compteur sur la légende** : Dans la légende, le compteur de performances est ajouté et sélectionné. Pour plus d’informations, voir [Utiliser la légende de la vue Graphiques pour analyser des tests de charge](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

    -   **Ajouter un graphique** :

    1.  La boîte de dialogue **Entrer le nom du graphique** s’affiche.

    2.  Dans la zone de texte **Nom du graphique**, entrez un nom pour le nouveau graphique, puis choisissez **OK**.

    3.  (Facultatif) Cliquez de nouveau avec le bouton droit sur le compteur de performances et sélectionnez **Afficher le compteur sur le graphique**.

         Pour plus d’informations, consultez [Guide pratique pour créer des graphiques personnalisés](../test/how-to-create-custom-graphs-in-load-test-results.md).

5.  (Facultatif) Si vous analysez la violation de seuil dans un résultat de test de charge terminé, pensez à utiliser les fonctionnalités de zoom dans la vue Graphiques. Pour plus d’informations, consultez [Guide pratique pour faire un zoom avant sur une région du graphique](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

    > [!TIP]
    > Si les violations de seuils ont été détectées pendant la série de tests de charge, un lien intitulé « violations de seuils », notamment le nombre de violations, sera disponible dans la barre d'état de l'**analyseur de test de charge**. Vous pouvez cliquer sur le lien pour afficher toutes les violations de seuils dans la table **Seuils** de la vue Tables.

## <a name="see-also"></a>Voir aussi

- [Utilisation du volet Compteurs dans la vue Graphiques et la vue Tables](../test/counters-panel-in-load-test-analyzer.md)
- [Analyser les résultats des tests de charge](../test/analyze-load-test-results-using-the-load-test-analyzer.md)