---
title: RPC requiert une authentification | Microsoft Docs
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- vs.debug.error.rpc_requires_authentication
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9bb172455226ab290a74da07e97fc40deb30b6ba
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90852548"
---
# <a name="error-rpc-requires-authentication"></a>Erreur : RPC requiert une authentification
Le débogueur Visual Studio ne peut pas se connecter à l'ordinateur distant. Une stratégie RPC est activée sur l'ordinateur local qui empêche le débogage distant.

### <a name="to-correct-this-error"></a>Pour corriger cette erreur

1. Exécuter `\` *windir*`\system32\regedt32.exe`

2. Recherchez et supprimez `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients` .

3. Redémarrez votre ordinateur afin que la modification du Registre entre en vigueur.

4. Si le problème persiste, contactez votre administrateur de domaine à propos de la configuration de l' **ordinateur > Modèles d’administration > système > l’appel de procédure Distante > des restrictions pour le paramètre de stratégie de groupe clients RPC non authentifiés** .