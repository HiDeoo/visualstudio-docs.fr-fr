---
title: Afficher les pièces jointes de données et diagnostic des tests de charge dans Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, data and diagnostics attachments
ms.assetid: 73309bdd-437a-4eb0-88c8-702c3e24b9b0
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 228f8306b803fcbd0e83e23e5b8e919dc2116c37
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39382462"
---
# <a name="how-to-view-data-and-diagnostic-attachments-using-the-load-test-analyzer"></a>Guide pratique pour afficher les pièces jointes des données et des diagnostics à l’aide de l’analyseur de test de charge

Avant d'exécuter un test de charge, vous pouvez sélectionner un paramètre de test qui spécifie les adaptateurs de diagnostic et de données que vous souhaitez utiliser. Une fois que le test de charge est terminé, utilisez **l’analyseur de test de charge** pour afficher les détails des adaptateurs de diagnostic et de données pendant l’analyse des résultats. Pour afficher les détails des adaptateurs de diagnostic et de données, choisissez le bouton **Afficher les pièces jointes de données et diagnostic** dans la barre d’outils de **l’analyseur de test de charge**. Par exemple, si l'adaptateur des informations système est configuré pour le test de charge dans le paramètre de test, vous pouvez afficher les informations système de l'ordinateur qui a été utilisé lors de l'exécution du test de charge.

![Boîte de dialogue Sélection de la pièce jointe d'adaptateur de données de diagnostic](../test/media/load_adapterdialog.png)

L'autre exemple est un test de charge qui inclut l'adaptateur IntelliTrace dans le paramètre de test. L’adaptateur IntelliTrace permet d’ouvrir la page **Résumé IntelliTrace**.

![Résumé IntelliTrace](../test/media/load_intellitrace.png)

Pour plus d’informations, consultez [Collecter des informations de diagnostic à l’aide des paramètres de test](../test/collect-diagnostic-information-using-test-settings.md) et [Collecter les données IntelliTrace](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md).

## <a name="to-view-data-and-diagnostic-attachments-in-a-load-test-from-the-load-test-analyzer"></a>Pour afficher les pièces jointes de données et diagnostic dans un test de charge à partir de l'analyseur de test de charge

1.  Après avoir effectué un test de charge, ou après avoir affiché un résultat de test de charge, dans la barre d’outils de **l’analyseur de test de charge**, choisissez **Afficher les pièces jointes de données et diagnostic**.

     La boîte de dialogue **Choisir la pièce jointe de l’adaptateur de données de diagnostic** s’affiche.

2.  Sélectionnez la pièce jointe de l’adaptateur de données de diagnostic à analyser, puis choisissez **OK**.

## <a name="see-also"></a>Voir aussi

- [Analyser les résultats des tests de charge](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
