---
title: AutoMark | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2d2bbd33308ddf14f14746db7f5c2c4ada6826b6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62776983"
---
# <a name="automark"></a>AutoMark
L’option **AutoMark** spécifie le nombre de millisecondes écoulées entre les collectes des événements des compteurs de performances logiciels Windows. Les compteurs de performances Windows sont spécifiés dans l’option **WinCounter**.

 Vous ne pouvez spécifier qu’une seule option **AutoMark** sur la ligne de commande. Notez que l’intervalle d’échantillonnage de **WinCounter** spécifié par **AutoMark** est indépendant de l’intervalle d’échantillonnage principal.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds
```

#### <a name="parameters"></a>Paramètres
 `Milliseconds` Spécifie le nombre de millisecondes écoulées entre les collectes des événements du compteur de performances Windows.

## <a name="required-options"></a>Options obligatoires
 **WinCounter:** `Path` Spécifie le compteur de performances Windows à collecter. Quand vous utilisez la méthode d’instrumentation, vous pouvez spécifier plusieurs compteurs Windows. Quand vous utilisez la méthode d’échantillonnage, vous ne pouvez spécifier qu’un seul compteur Windows. L’option **WinCounter** doit être spécifiée dans une ligne de commande qui contient l’option **Start**.

## <a name="example"></a>Exemple
 Dans cet exemple, un intervalle d’échantillonnage de 1 000 millisecondes est défini pour deux compteurs de performances Windows.

```cmd
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000
VSPerfCmd.exe /Launch:TestApp.exe
```

## <a name="see-also"></a>Voir aussi
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Profiler des applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Profiler des applications web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profiler des services](../profiling/command-line-profiling-of-services.md)