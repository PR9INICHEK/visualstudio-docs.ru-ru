---
title: Задачи отладки | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: overview
helpviewer_keywords:
- debugging [Debugging SDK], tasks
ms.assetid: 5d60e9e8-305e-4a48-829f-b9440fc8af7b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 070068853d962bdf9b209edb9410d33d46ccf853
ms.sourcegitcommit: 05487d286ed891a04196aacd965870e2ceaadb68
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85903551"
---
# <a name="debug-tasks"></a>Задачи отладки
Чтобы выполнить отладку программы, она должна быть запущена и к ней должен быть присоединен отладчик (DE), или же DE должен быть присоединен к ранее запущенной программе. После присоединения DE должен создать определенные события запуска. В ответ пакет отладки пытается привязать точки останова, заданные в интегрированной среде разработки. Когда программа достигает привязанной точки останова, она останавливается и ожидает ввода данных пользователем.

## <a name="in-this-section"></a>Содержание раздела
 [Проблемы безопасности](../../extensibility/debugger/security-issues.md) Описание действий по обеспечению безопасности, необходимых для отладки программы.

 [Запуск программы](../../extensibility/debugger/launching-a-program.md) Содержит пошаговые инструкции по заданию DE, который вызывает операционную систему для запуска программы.

 [Прямое подключение к программе](../../extensibility/debugger/attaching-directly-to-a-program.md) Описывает процесс, используемый для отладки программы в уже запущенном процессе.

 [Отправка событий запуска после запуска](../../extensibility/debugger/sending-startup-events-after-a-launch.md) Список событий, происходящих после присоединения к программе, до тех пор, пока программа не станет основной точкой входа и не будет готова к отладке.

 [Управление выполнением](../../extensibility/debugger/control-of-execution.md) Объясняет, как в методе DE обычно отправляется событие точки входа, событие загрузки или событие остановки, в зависимости от обстоятельств.

 [Привязка точек останова](../../extensibility/debugger/binding-breakpoints.md) Описывает, как, если пользователь устанавливает точку останова, интегрированная среда разработки формирует запрос и запрашивает у сеанса отладки создание точки останова.

 [Вычисление выражений](../../extensibility/debugger/evaluating-expressions.md) Объясняет, как создаются выражения и что происходит при вычислении выражения.

 [Визуализация и просмотр данных](../../extensibility/debugger/visualizing-and-viewing-data.md) Описывает, как визуализаторы типов и пользовательские средства просмотра поддерживаются средством оценки выражений (EE).

## <a name="related-sections"></a>Связанные разделы
 [Основные понятия отладчика](../../extensibility/debugger/debugger-concepts.md) Описывает основные понятия архитектуры отладки.

 [Компоненты отладчика](../../extensibility/debugger/debugger-components.md) Содержит общие сведения о компонентах отладки Visual Studio, включая DE, EE и обработчик символов (SH).

 [Контексты отладчика](../../extensibility/debugger/debugger-contexts.md) Объясняется, как происходит одновременное отключение в рамках кода, документации и контекстов оценки выражений. Описывает, для каждого из трех контекстов: расположение, положение или вычисление, относящиеся к нему.

## <a name="see-also"></a>Дополнительно
 [Начало работы](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)
