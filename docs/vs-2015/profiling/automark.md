---
title: Параметр AutoMark | Документы Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e01dac3f1012c76ebe6095b5b5a244226fe4843
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47559901"
---
# <a name="automark"></a>Параметр AutoMark
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [AutoMark](https://docs.microsoft.com/visualstudio/profiling/automark).  
  
Параметр **AutoMark** указывает интервал (в миллисекундах) между сбором событий счетчиков производительности для программного обеспечения Windows. Счетчики производительности Windows указываются в параметре **WinCounter**.  
  
 В командной строке можно указать только один параметр **AutoMark**. Обратите внимание, что интервал выборки **WinCounter**, указанный в **AutoMark**, не зависит от основного интервала выборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds  
```  
  
#### <a name="parameters"></a>Параметры  
 `Milliseconds`  
 Указывает интервал (в миллисекундах) между сбором данных счетчиков производительности Windows.  
  
## <a name="required-options"></a>Обязательные параметры  
 **WinCounter:** `Path`  
 Указывает счетчик производительности Windows, данные которого нужно собрать. При использовании метода инструментирования можно указать несколько счетчиков Windows. При использовании метода выборки можно указать всего один счетчик программного обеспечения. Параметр **WinCounter** следует указывать в командной строке, которая содержит параметр **Start**.  
  
## <a name="example"></a>Пример  
 В этом примере для двух счетчиков производительности Windows установлен интервал выборки 1000 миллисекунд.  
  
```  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>См. также  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Профилирование автономных приложений](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Профилирование веб-приложений ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Профилирование служб](../profiling/command-line-profiling-of-services.md)


