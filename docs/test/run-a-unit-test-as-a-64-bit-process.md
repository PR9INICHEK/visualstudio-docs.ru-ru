---
title: Выполнение модульного теста как 64-разрядного процесса
ms.date: 03/10/2020
ms.topic: how-to
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: 04895e3dd72a7cb4f0373c970db0f12582506ef9
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85285560"
---
# <a name="run-a-unit-test-as-a-64-bit-process"></a>Выполнение модульного теста как 64-разрядного процесса

На 64-разрядном компьютере можно выполнять модульные тесты и получать данные о покрытии кода в рамках 64-разрядного процесса.

## <a name="to-run-a-unit-test-as-a-64-bit-process"></a>Выполнение модульного теста как 64-разрядного процесса

1. Если код или тесты были скомпилированы как 32-разрядные (x86), но вы хотите выполнять их в 64-разрядном процессе, перекомпилируйте их в конфигурации **Любой ЦП**.

   ::: moniker range="vs-2017"
   В Visual Studio 2017 проект также можно скомпилировать как **64-разрядный**.
   ::: moniker-end

    > [!TIP]
    > Для максимальной гибкости тестовые проекты следует компилировать в конфигурации **Любой ЦП**. Тогда выполнение возможно как на 32-разрядных, так и на 64-разрядных агентах. Компиляция тестовых проектов в конфигурации **64 разряда** не дает никаких преимуществ.

2. Настройте выполнение модульных тестов в 64-разрядном процессе.

   ::: moniker range=">=vs-2019"
   В меню Visual Studio выберите пункт **Тест**, а затем — **Процессорная архитектура для проектов AnyCPU**. Выберите **x64**, чтобы выполнять тесты в 64-разрядном процессе.
   ::: moniker-end
   ::: moniker range="vs-2017"
   В меню Visual Studio выберите пункт **Тест**, а затем — **Параметры теста** и **Архитектура процессора**. Выберите **x64**, чтобы выполнять тесты в 64-разрядном процессе.
   ::: moniker-end

   \- или -

   Укажите `<TargetPlatform>x64</TargetPlatform>` в файле *.runsettings*. Преимущество этого метода состоит в том, что можно задавать группы настроек в разных файлах и быстро переключаться между различными настройками. Кроме того, вы можете копировать настройки между решениями. Дополнительные сведения см. в разделе [Настройка модульных тестов с помощью файла .runsettings](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).

## <a name="see-also"></a>См. также

- [Выполнение модульных тестов с помощью обозревателя тестов](../test/run-unit-tests-with-test-explorer.md)
- [Модульное тестирование кода](../test/unit-test-your-code.md)
