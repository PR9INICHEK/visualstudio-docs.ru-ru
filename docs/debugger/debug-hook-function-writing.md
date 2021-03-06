---
title: Написание функций отладочных ловушек | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: how-to
f1_keywords:
- vc.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], CRT debug support
- debug hook functions
- hooks, debug
- hooks
- debugging [CRT], debug hook functions
ms.assetid: 5510635f-cf69-4907-b72d-ae27af1f19af
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 038c976380ff1e1f0a1a7c4c150fc462f6b1d1db
ms.sourcegitcommit: c076fe12e459f0dbe2cd508e1294af14cb53119f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2020
ms.locfileid: "85350723"
---
# <a name="debug-hook-function-writing"></a>Написание функций отладочных ловушек
В этом подразделе дается краткое описание нескольких функций отладочных ловушек, которые можно написать самостоятельно. Эти функции позволяют разместить пользовательский код в заранее определенных местах в контексте стандартной процедуры отладки.

## <a name="in-this-section"></a>В этом разделе
 [Клиентские функции отладочных ловушек](../debugger/client-block-hook-functions.md) — руководство по написанию функций и заготовки функций, проверяющих или выводящих содержимое, которое хранится в блоках типа _CLIENT_BLOCK.

 [Функции-ловушки выделения](../debugger/allocation-hook-functions.md) — содержит определение функции-ловушки выделения, описание способов их использования и ограничений, а также прототип.

 [Функции-ловушки и выделения памяти CRT](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md) — сведения об ограничениях, связанных с функциями-ловушками выделения, которые явно пропускают блоки `_CRT_BLOCK` при вызове функций библиотеки CRT, выделяющих внутреннюю память. Также в разделе описываются последствия, которые могут возникнуть, если ловушка приложения обработает блоки `_CRT_BLOCK` (с примерами), и способы изменения стандартной функции-ловушки выделения **CrtDefaultAllocHook**.

 [Функции-ловушки для отчетов](../debugger/report-hook-functions.md) — сведения о функции `_CrtSetReportHook`, которая позволяет фильтровать отчеты, чтобы отобрать выделения конкретного типа. В этом разделе также приведена ее заготовка.

## <a name="related-sections"></a>Связанные разделы

- [Техники отладки CRT](../debugger/crt-debugging-techniques.md) — сведения о методах отладки библиотеки времени выполнения языка C, к которым относятся: использование библиотеки отладки CRT, макрос для отчета, различия между функциями `malloc` и `_malloc_dbg`, написание отладочных функций-ловушек, а также отладочная куча CRT.