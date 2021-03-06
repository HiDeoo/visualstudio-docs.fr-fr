---
title: Codes de message | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1c09245056bf7e947985bfa55dc9cc4a3a96b8cf
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "62846271"
---
# <a name="message-codes"></a>Codes des messages
Chaque ligne de message affichée dans la [vue messages](../debugger/messages-view.md) contient un code’P, ', ', 'ou’R'. Ces codes ont les significations suivantes :

|Code|Signification|
|----------|-------------|
|P|Le message a été publié dans la file d’attente avec la fonction **PostMessage** . Aucune information n’est disponible concernant la disposition finale du message.|
|S|Le message a été envoyé avec la fonction **SendMessage** . Cela signifie que l’expéditeur ne reprend pas le contrôle tant que le destinataire ne traite pas et ne renvoie pas le message. Le récepteur peut donc retourner une valeur de retour à l’expéditeur.|
|s|Le message a été envoyé, mais la sécurité empêche l’accès à la valeur de retour.|
|R|Chaque ligne’a une ligne’R' (retour) correspondante qui répertorie la valeur de retour du message. Parfois, les appels de message sont imbriqués, ce qui signifie qu’un gestionnaire de messages envoie un autre message.|