---
title: 'Débogage de F # | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Debugging [F#]
- F#, debugging
ms.assetid: 20bcd51c-2d06-4281-9a1e-ef2b91d1a779
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e7bc3934136f0966439bec2e4368488e52099602
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "72738270"
---
# <a name="debugging-f"></a>Débogage de F\#
Le débogage de F# est semblable au débogage de tout langage managé, à quelques exceptions près :

- La fenêtre **Automatique** n’affiche pas les variables F#.

- L'opération Modifier &amp; Continuer n'est pas prise en charge pour F# La modification du code F# pendant une session de débogage est possible mais doit être évitée. Dans la mesure où les modifications du code ne sont pas appliquées pendant la session de débogage, le fait de modifier le code F# lors du débogage provoquera une incompatibilité entre le code source et le code débogué.

- Le débogueur ne reconnaît pas les expressions F#. Pour entrer une expression dans une fenêtre du débogueur ou une boîte de dialogue lors du débogage de F#, vous devez traduire l'expression en syntaxe C#. Lorsque vous traduisez une expression F# en syntaxe C#, assurez-vous que C# utilise == comme opérateur de comparaison d'égalité et que F# utilise un signe = unique.

## <a name="see-also"></a>Voir aussi
- [Débogage du code managé](../debugger/debugging-managed-code.md)
