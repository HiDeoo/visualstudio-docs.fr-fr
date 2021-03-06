---
title: Déboguer les fonctions de l’API Windows | Microsoft Docs
ms.custom: seodec18
ms.date: 06/03/2020
ms.topic: how-to
f1_keywords:
- vs.debug.api
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], Windows API functions
- NT symbols and debugging Windows API functions
- Windows API functions, debugging
- Windows API, debugging API functions
- APIs, debugging
ms.assetid: 7c126f57-62ab-4d94-9805-632d696ba1f0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3f7b293270facbbfa0d2174121ff6a3ac736b75a
ms.sourcegitcommit: ed4372bb6f4ae64f1fd712b2b253bf91d9ff96bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2020
ms.locfileid: "89599887"
---
# <a name="how-can-i-debug-windows-api-functions"></a>Comment puis-je déboguer des fonctions API Windows ?
Si vous voulez déboguer une fonction API Windows qui a chargé les symboles NT, vous devez effectuer les opérations suivantes.

### <a name="to-set-a-breakpoint-on-a-windows-api-function-with-nt-symbols-loaded"></a>Pour définir un point d'arrêt sur une fonction API Windows qui a chargé des symboles NT

- Dans le [point d’arrêt sur fonction](../debugger/using-breakpoints.md#BKMK_Set_a_breakpoint_in_a_source_file), entrez le nom de la fonction ainsi que le nom de la dll dans laquelle la fonction réside (consultez [opérateur de contexte](../debugger/context-operator-cpp.md)). Dans du code 32 bits, utilisez la forme décorée du nom de la fonction. Pour définir un point d’arrêt sur **MessageBeep**, par exemple, vous devez entrer ce qui suit.

    ```cpp
    {,,USER32.DLL}_MessageBeep@4
    ```

     Pour obtenir le nom décoré, consultez [affichage des noms décorés](/previous-versions/5x49w699(v=vs.140)).

     Vous pouvez tester le nom décoré et l’afficher dans le code machine. Pendant la suspension de la fonction dans le débogueur Visual Studio, cliquez avec le bouton droit sur la fonction dans l’éditeur de code ou dans la fenêtre pile des appels, puis sélectionnez atteindre le code **machine**.

- Dans le code 64 bits, vous pouvez utiliser le nom non décoré.

    ```cpp
    {,,USER32.DLL}MessageBeep
    ```

## <a name="see-also"></a>Voir aussi
- [Forum Aux Questions sur le débogage du code natif](../debugger/debugging-native-code-faqs.md)
- [Débogage du code natif](../debugger/debugging-native-code.md)