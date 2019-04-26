---
title: WinCounter | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ff319ffc-f249-4c3f-9eb2-06e392e3ae80
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8e93cc526ad61916e2a8663caa9652842ce136c5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62960192"
---
# <a name="wincounter"></a>WinCounter
L’option **WinCounter** spécifie un compteur de performances Windows ou d’application à collecter à des intervalles définis pendant l’exécution du profil. Les compteurs de performances Windows et d’application sont répertoriés en tant que marques dans le fichier de données de profilage. Vous pouvez spécifier plusieurs compteurs de performances à collecter dans des options distinctes.

 Par défaut, les compteurs sont collectés toutes les 500 millisecondes. Utilisez l’option **AutoMark** pour spécifier un autre intervalle de collecte.

 Une seule option **AutoMark** est utilisée. Si plusieurs options **AutoMark** sont spécifiées, seule la dernière est utilisée.

 L’option **WinCounter** peut être utilisée seulement avec l’option **Start**.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Start:Method /Wincounter:Path [/WinCounter:Path] [AutoMark:Milliseconds] [Options]
```

#### <a name="parameters"></a>Paramètres
 `Path` Compteur de performances Windows au format de chemin de compteur PDH.

## <a name="required-options"></a>Options obligatoires
 L’option **WinCounter** peut être utilisée seulement avec l’option **Start**.

 **Start :** `Method` L’option **Start** initialise le profileur avec la méthode de profilage spécifiée.

## <a name="exclusive-options"></a>Options exclusives
 L’option **AutoMark** peut être utilisée seulement avec l’option **WinCounter**.

 **AutoMark :** `Milliseconds` Spécifie le nombre de millisecondes écoulées entre les collectes des données du compteur de performances Windows.

## <a name="example"></a>Exemple
 Dans l’exemple suivant, deux compteurs de performance Windows sont configurés être collectés à un intervalle de 1 000 millisecondes.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WinCounter:"\Processor(0)\% Processor Time" /WinCounter:"\System\Context Switches/sec" /AutoMark:1000
```

## <a name="see-also"></a>Voir aussi
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Profiler des applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Profiler des applications web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profiler des services](../profiling/command-line-profiling-of-services.md)