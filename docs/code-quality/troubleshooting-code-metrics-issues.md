---
title: Résolution des problèmes liés à la métrique du code
ms.date: 11/04/2016
ms.topic: troubleshooting
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 66655dd1e250ae16e48330eabc77610756fea367
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62820748"
---
# <a name="troubleshooting-code-metrics-issues"></a>Résolution des problèmes liés à la métrique du code
Vous pouvez rencontrer certains des problèmes suivants quand vous collectez des métriques du code :

- [Modifications dans les calculs de complexité du code dans Visual Studio 2010](#Changes_in_Visual_Studio_2010_code_complexity_calculations)

## <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a> Modifications dans les calculs de complexité du code dans Visual Studio 2010
 Pour la même fonction, la métrique de complexité du code calculée dans [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] peut être différente de la métrique calculée par les versions antérieures de [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] dans les situations suivantes :

- La fonction contient un ou plusieurs blocs catch. Dans les versions précédentes de [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], les blocs catch n’étaient pas inclus dans le calcul. Dans [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)], la complexité de chaque bloc catch est ajoutée à la complexité de la fonction.

- La fonction contient une instruction switch (Select Case dans VB). Des différences de compilateur entre [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] et les versions antérieures peuvent générer un code MSIL différent pour certaines instructions switch qui contiennent des éléments case avec fallthrough.

## <a name="see-also"></a>Voir aussi
 [Mesures de la complexité et de la facilité de maintenance du code managé](../code-quality/code-metrics-values.md)