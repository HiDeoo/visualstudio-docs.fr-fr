---
title: L’utilisateur n’a pas pu exécuter la procédure stockée sp_enable_sql_debug | Microsoft Docs
ms.date: 11/04/2016
ms.topic: error-reference
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
ms.openlocfilehash: c8131c7b16205b308e04b621dd1fcb536ba94c14
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90852424"
---
# <a name="error-user-could-not-execute-stored-procedure-sp_enable_sql_debug"></a>Erreur : L'utilisateur n'a pas pu exécuter la procédure stockée sp_enable_sql_debug

La procédure stockée sp_enable_sql_debug n'a pas pu s'exécuter sur le serveur. Cela peut être provoqué par :

- Un problème de connexion. Vous devez avoir une connexion stable au serveur.

- Un manque d'autorisations nécessaires sur le serveur. Pour déboguer sur SQL Server 2005, le compte exécutant Visual Studio et le compte utilisé pour la connexion à SQL Server doivent être membres du rôle sysadmin. Le compte utilisé pour la connexion à SQL Server est soit votre compte d'utilisateur Windows (si vous utilisez l'authentification Windows) soit un compte avec l'ID et le mot de passe d'utilisateur (si vous utilisez l'authentification SQL).

Pour plus d’informations, consultez [Comment : définir des autorisations de SQL Server pour le débogage](/previous-versions/w1bhybwz(v=vs.100)).

## <a name="see-also"></a>Voir aussi

- [Comment : définir des autorisations de SQL Server pour le débogage](/previous-versions/w1bhybwz(v=vs.100))
- [Configuration du débogage SQL](/previous-versions/visualstudio/visual-studio-2010/s4sszxst\(v\=vs.100\))