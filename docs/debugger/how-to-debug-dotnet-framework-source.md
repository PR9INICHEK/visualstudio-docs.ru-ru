---
title: Практическое руководство. Отладка исходного кода .NET Framework | Документация Майкрософт
ms.date: 11/19/2018
ms.topic: how-to
helpviewer_keywords:
- debugging, .NET Framework source
ms.assetid: fc12e472-ac6a-4e77-8e22-a769e13a03b8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 3f043aae44231608fb514e87a05717f4aeb924bc
ms.sourcegitcommit: c076fe12e459f0dbe2cd508e1294af14cb53119f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2020
ms.locfileid: "85350099"
---
# <a name="how-to-debug-net-framework-source"></a>Практическое руководство. Отладка исходного кода .NET Framework

Чтобы отлаживать исходный код .NET Framework, вам потребуется следующее.

- Разрешите выполнение по шагам для исходного кода .NET Framework.

- Получите доступ к символам отладки для этого кода.

  Вы можете скачать символы отладки немедленно или настроить параметры для скачивания в другое время. Если вы не скачаете символы сразу, они будут скачаны в начале следующего сеанса отладки приложения. Во время отладки можно также использовать окна **Модули** или **Стек вызовов** для скачивания и загрузки символов.

### <a name="to-enable-stepping-into-net-framework-source"></a>Включение выполнения по шагам для исходного кода .NET Framework

1. В разделе **Средства** (или **Отладка**) > **Параметры** > **Отладка** > **Общие** установите флажок **Разрешить шаги в исходном коде .NET Framework**.

   - Если был включен режим "Только мой код", появится диалоговое окно с предупреждением об отключении этого режима. Нажмите кнопку **ОК**.

   - Если локальный кэш символов не был настроен ранее, появится диалоговое окно с сообщением о настройке кэша символов по умолчанию. Нажмите кнопку **ОК**.

1. Щелкните **ОК**, чтобы закрыть диалоговое окно **Параметры**.

### <a name="to-set-or-change-symbol-source-locations-and-loading-behavior"></a>Настройка или изменение исходного расположения символов и режима загрузки

1. Выберите категорию **Символы** в разделе **Средства** (или **Отладка**) > **Параметры** > **Отладка**.

1. На странице **Символы** в разделе **Места размещения файлов символов (.pdb):** выберите **Серверы символов (Майкрософт)** , чтобы получить доступ к символам с общедоступных серверов символов Майкрософт. С помощью кнопок на панели инструментов вы можете добавить другие расположения символов и изменить порядок загрузки.

1. Чтобы изменить кэш локальных символов, введите новое расположение или перейдите к нему в разделе **Кэшировать символы в этом каталоге**.

1. Чтобы немедленно скачать символы, выберите действие **Загрузить все символы**. Эта кнопка доступна только в процессе отладки.

   Если вы не скачаете символы сразу, они будут скачаны при следующем запуске отладки.

1. Щелкните **ОК**, чтобы закрыть диалоговое окно **Параметры**.

### <a name="to-load-symbols-from-the-modules-or-call-stack-windows"></a>Загрузка символов из окон "Модули" или "Стек вызовов"

1. В процессе отладки откройте нужное окно, последовательно выбрав **Отладка** > **Окна** > **Модули** (клавиши **CTRL+ALT+U**) или **Отладка** > **Окна** > **Стек вызовов** (клавиши **CTRL+ALT+C**).

1. Щелкните правой кнопкой любой модуль, для которого не загружены символы. В окне **Модули** состояние загрузки символов отображается в столбце **Состояние символов**. В окне **Стек вызовов** это состояние отображается в столбце **Состояние кадра** и соответствующие кадры помечаются как неактивные.

   - Выберите **Загрузить символы** из меню, чтобы найти и загрузить файлы символов из локальной папки на компьютере.

   - Выберите **Сведения о загрузке символов**, чтобы отобразить расположения, в которых отладчик ищет символы.

   - Выберите **Параметры символов**, чтобы открыть страницу **Символы**. На странице **Символы** в разделе **Места размещения файлов символов (.pdb):** выберите **Серверы символов (Майкрософт)** , чтобы получить доступ к символам с общедоступных серверов символов Майкрософт. С помощью кнопок на панели инструментов вы можете добавить другие расположения символов и изменить порядок загрузки. Нажмите кнопку **ОК**, чтобы закрыть это диалоговое окно.

### <a name="see-also"></a>См. также
- [Отладка управляемого кода](../debugger/debugging-managed-code.md)
- [Указание файлов символов (PDB) и файлов с исходным кодом](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)