---
title: 'DA0504 : Jeu de travail maximal en octets pour le processus en cours de profilage | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.DA0504
- vs.performance.504
- vs.performance.rules.DA0504
ms.assetid: 36e71603-ece7-4000-85fc-9da4eed61bf2
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2c57e006196611b49909f3ad6bfc866a028a8621
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "75850882"
---
# <a name="da0504-maximum-working-set-in-bytes-for-the-process-being-profiled"></a>DA0504 : jeu de travail maximal en octets pour le processus en cours de profilage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ID de règle | DA0504 |  
| Catégorie | Gestion des ressources |  
| Méthode de profilage | Tout |  
| Message | Ces informations ont été collectées à titre d’information uniquement. Le compteur Jeu de travail de processus mesure l’utilisation de la mémoire physique par le processus en cours de profilage. La valeur signalée correspond à la valeur maximale observée dans l’ensemble des intervalles de mesure.|  
| Type de règle | Informations |  
  
 Lorsque vous effectuez un profilage à l’aide de la méthode d’échantillonnage, de mémoire .NET ou de conflit des ressources, vous devez collecter au moins 10 échantillons pour déclencher cette règle.  
  
## <a name="rule-description"></a>Description de la règle  
 Ce message signale la quantité maximale de mémoire physique, en octets, que le processus utilise. Le jeu de travail du processus comprend les pages de l’espace d’adressage de processus qui résident actuellement dans la mémoire physique. Cette règle signale la valeur maximale du jeu de travail du processus pendant que le profilage était actif.  
  
 La valeur signalée comprend les pages résidant dans les segments de mémoire partagée que le processus a référencées. Les DLL partagées que le processus référence sont incluses dans les segments de mémoire partagée qui sont comptabilisés. La valeur du jeu de travail du processus peut être supérieure à la quantité de mémoire virtuelle que le processus a allouée, en raison des segments de mémoire partagée.  
  
 La taille du jeu de travail du processus correspond à la mémoire virtuelle que le processus utilise activement. Elle est également affectée par la quantité de mémoire physique (ou RAM) disponible pour exécuter l’application, et par les conflits entre cette mémoire physique et d’autres processus en cours d’exécution. Pour plus d’informations sur les jeux de travail de processus, consultez [Jeu de travail](https://msdn.microsoft.com/library/cc441804.aspx) dans la documentation MSDN relative à la gestion de la mémoire dans Windows.  
  
## <a name="how-to-use-rule-data"></a>Comment utiliser des données de règle  
 La règle rassemble ces données de mesure à partir de la fonctionnalité d’analyse des performances de Windows et les fournit dans un but informatif. Utilisez ces données pour comparer les performances des différentes versions du programme ou pour comprendre les performances de l’application dans différents scénarios de test.  
  
 Double-cliquez sur le message dans la fenêtre Liste d’erreurs pour accéder à la [vue Marques](../profiling/marks-view.md) des données de profilage. Accédez aux colonnes de compteur **Processus\Jeu de travail** et **Mémoire\Pages/s**. Recherchez la valeur maximale de la colonne **Processus\Jeu de travail** et comparez-la à celle de la colonne **Mémoire\Pages/s**. Souvent, la valeur maximale du jeu de travail est associée à un intervalle durant lequel une baisse de l’activitité d’E/S de pagination s’est produite, en particulier si la mémoire de l’ordinateur est limitée.
