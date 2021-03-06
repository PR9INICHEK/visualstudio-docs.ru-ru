---
title: Отключить анализ кода прежних версий
ms.date: 10/04/2019
ms.topic: how-to
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 532fe62ceee3ab32fc203976af58dd867b97b453
ms.sourcegitcommit: 48e93538f1e352fc1f972b642bb5fcce2f6834a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2020
ms.locfileid: "85371889"
---
# <a name="how-to-enable-and-disable-binary-code-analysis-for-managed-code"></a>Как включить и отключить анализ двоичного кода для управляемого кода

Можно настроить анализ кода прежних версий (двоичный анализ), который будет выполняться после каждой сборки проекта управляемого кода. Можно также иметь разные параметры для каждой конфигурации сборки, например Отладка и выпуск.

> [!NOTE]
> Устаревший анализ недоступен для новых типов проектов, таких как .NET Core и .NET Standard приложения. Эти проекты используют [анализаторы кода на основе .NET Compiler Platform](roslyn-analyzers-overview.md) для анализа кода как в режиме реального времени, так и во время сборки. Сведения об отключении анализа исходного кода в этих проектах см. [в разделе Отключение анализа исходного кода](disable-code-analysis.md).

Чтобы включить или отключить анализ кода прежних версий, выполните следующие действия.

1. В **Обозреватель решений**щелкните правой кнопкой мыши проект и выберите пункт **свойства**.

2. В диалоговом окне Свойства проекта перейдите на вкладку **анализ кода** .

3. Укажите тип сборки в поле **Конфигурация** и Целевая платформа на **платформе**. (Только проекты Non-.NET Core/. NET Standard.)

::: moniker range="vs-2017"

4. Чтобы включить или отключить автоматический анализ кода, установите или снимите флажок **Включить анализ кода при сборке** .

::: moniker-end

::: moniker range=">=vs-2019"

4. Чтобы включить или отключить автоматический анализ кода, установите или снимите флажок **выполнить при сборке** в разделе **анализаторы двоичных** данных.

   ![Запуск анализа двоичного кода при сборке в Visual Studio](media/run-on-build-binary-analyzers.png)

::: moniker-end

> [!NOTE]
> Отключение анализа двоичного кода в сборке не влияет на [анализаторы кода на основе .NET Compiler Platform](roslyn-analyzers-overview.md), которые всегда выполняются при сборке, если они были установлены в качестве пакета NuGet. Дополнительные сведения об отключении анализа из этих анализаторов см. [в разделе Отключение анализа исходного кода](disable-code-analysis.md).
