---
title: Возврат к функции, вызвавшей MFC, при прерывании работы в MFC | Документация Майкрософт
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: how-to
f1_keywords:
- vs.debug.mfc
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- functions [C++], debugging
- function calls, returning to calling function
- debugging [MFC], returning to calling function
- debugging [MFC], functions
- Break command
- programs, halting
- functions [debugger]
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ef96bab28b1a17d4f20728a393511720fd10c624
ms.sourcegitcommit: c076fe12e459f0dbe2cd508e1294af14cb53119f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2020
ms.locfileid: "85349475"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>Практическое руководство. Возврат к функции, вызвавшей MFC, при прерывании работы в MFC

> [!NOTE]
> Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Сброс параметров](../ide/environment-settings.md#reset-settings).

При использовании команды **Прервать** из меню **Отладка** для остановки выполнения программы и завершения в MFC и при наличии ошибок в коде, можно вызвать окно "Стек вызовов" для обратного перехода к функции. Дополнительные сведения см. в разделе [Практическое руководство. использовать окно "Стек вызовов"](../debugger/how-to-use-the-call-stack-window.md).

Иногда код может прерываться в генераторе сообщений. В таком случае в стеке вызовов нет пользовательского кода. Во избежание этой проблемы используются точки останова (с условиями и количеством обращений) вместо команды **Прервать**. Для получения дополнительной информации см. [Breakpoints and Tracepoints](https://msdn.microsoft.com/library/fe4eedc1-71aa-4928-962f-0912c334d583).

## <a name="navigate-to-the-function-from-which-mfc-was-called"></a>Переход к функции, из которой был вызван MFC

- Используйте окно **Стек вызовов**.

## <a name="see-also"></a>См. также

- [Вопросы и ответы по отладке машинного кода](../debugger/debugging-native-code-faqs.md)
- [Отладка машинного кода](../debugger/debugging-native-code.md)