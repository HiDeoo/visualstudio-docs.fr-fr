---
title: Implémentation d’un fournisseur de port | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8218e372ad3aece922811bc20cfd7650f33296f3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "80738555"
---
# <a name="implement-a-port-supplier"></a>Implémenter un fournisseur de port
Un fournisseur de port fournit des ports à la demande au gestionnaire de débogage de session (SDM). Un fournisseur de ports doit être implémenté lors du débogage sur un ordinateur non-DCOM ou lorsqu’un nouvel appareil requiert la prise en charge. Par exemple, pour permettre le débogage sur un téléphone portable, vous pouvez configurer un fournisseur de ports qui fournit des ports, qui se connectent au téléphone portable (par exemple, par le biais d’une connexion IR ou de cellule) et énumère les processus et les programmes en cours d’exécution sur le téléphone.

 Pour déboguer des programmes sur des ordinateurs Windows (y compris le débogage distant), Visual Studio fournit des fournisseurs de port pour les processus natif et CLR (Common Language Runtime). il n’est donc pas nécessaire de configurer votre propre fournisseur de port dans ces cas.

## <a name="in-this-section"></a>Contenu de cette section
 [Implémenter et inscrire un fournisseur de port](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md) Explique comment le SDM interagit avec le fournisseur de ports et ses ports.

 [Interfaces du fournisseur de port requises](../../extensibility/debugger/required-port-supplier-interfaces.md) Documente les interfaces que vous devez implémenter pour obtenir un fournisseur de ports.

## <a name="related-sections"></a>Sections connexes
 [Concepts du débogueur](../../extensibility/debugger/debugger-concepts.md) Décrit les principaux concepts architecturaux du débogage.

## <a name="see-also"></a>Voir aussi
 [Extensibilité du débogueur Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)
