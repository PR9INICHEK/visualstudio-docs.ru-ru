---
title: 'Ошибка: монитор удаленной отладки Visual Studio на удаленном компьютере запущен от имени другого пользователя'
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: error-reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a69745a051af0ec44eb813054e40fb9f6c6a0aa6
ms.sourcegitcommit: 66f31cc4ce1236e638ab58d2f70d3646206386fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "85460407"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>Ошибка: На удаленном компьютере монитор удаленной отладки Microsoft Visual Studio выполняется в контексте другого пользователя
При выполнении удаленной отладки может появиться следующее сообщение об ошибке:

 На удаленном компьютере монитор удаленной отладки Microsoft Visual Studio выполняется в контексте другого пользователя.

## <a name="cause"></a>Причина:
 Это сообщение появляется, если отладка выполняется в режиме "без аутентификации" и пользователь, запустивший msvsmon, не является пользователем, запустившим Visual Studio.

## <a name="solution"></a>Решение
 Лучшим и наиболее безопасным решением является запуск монитора удаленной отладки (msvsmon.exe) под учетной записью пользователя, запустившего Visual Studio. Если сделать это невозможно, можно запустить монитор удаленной отладки под другой учетной записью, выбрав параметр **Разрешить отладку любому пользователю** в диалоговом окне **Параметры** монитора удаленной отладки.

> [!CAUTION]
> Предоставление другим пользователям разрешения на подключение допускает вероятность случайного подключения к неправильному сеансу удаленной отладки. Отладка в режиме **Без аутентификации** никогда не является безопасной, и ее следует использовать с осторожностью.

## <a name="see-also"></a>См. также
- [Ошибки удаленной отладки и их устранение](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Remote Debugging](../debugger/remote-debugging.md)