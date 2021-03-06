---
title: Не удается подключиться к монитору удаленной отладки Microsoft Visual Studio | Документация Майкрософт
ms.date: 04/14/2020
ms.topic: reference
f1_keywords:
- vs.debug.error.remote_debug
- vs.debug.error.firewall.remotemachine
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d6173d6b3525a1bd723bc859d34b889b3796d295
ms.sourcegitcommit: c3b92a9912a5816f16c6059d1738dbc833851346
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2020
ms.locfileid: "81397380"
---
# <a name="unable-to-connect-to-the-microsoft-visual-studio-remote-debugging-monitor"></a>Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor
Это сообщение можно увидеть по следующим причинам: монитор удаленной отладки на удаленном компьютере неверно настроен или удаленный компьютер недоступен из-за неполадок в работе сети или из-за наличия брандмауэра.

> [!IMPORTANT]
> Если вы считаете, что получили это сообщение из-за ошибки продукта, [сообщите о проблеме](../ide/how-to-report-a-problem-with-visual-studio.md) разработчикам Visual Studio. Если вам нужна дополнительная помощь, обратитесь к разделу [Talk to Us](../ide/feedback-options.md) , чтобы узнать, как связаться с корпорацией Майкрософт.

## <a name="what-is-the-detailed-error-message"></a><a name="specificerrors"></a>Что такое подробное сообщение об ошибке?

Сообщение `Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor` является универсальным. Обычно строка ошибки содержит более конкретное сообщение, которое может помочь вам определить причину проблемы или подобрать более подходящее исправление. Вот несколько самых распространенных сообщений об ошибках, добавляемых к основному сообщению об ошибке.

- [Отладчику не удалось подключиться к удаленному компьютеру. Отладчику не удалось разрешить указанное имя компьютера.](#cannot_connect)
- [Запрос на подключение был отклонен удаленным отладчиком.](#rejected)
- [Подключение к удаленной конечной точке завершено.](#connection_terminated)
- [Недопустимый доступ к участку памяти.](#invalid_access)
- [На этом удаленном компьютере сервер с указанным именем отсутствует.](#no_server)
- [Запрошенное имя допустимо, но данные запрошенного типа не найдены.](#valid_name)
- [Удаленный отладчик Visual Studio на удаленном компьютере не может подключиться к этому компьютеру.](#cant_connect_back)
- [Доступ запрещен](#access_denied)
- [Ошибка в пакете безопасности.](#security_package)

## <a name="the-debugger-cannot-connect-to-the-remote-computer-the-debugger-was-unable-to-resolve-the-specified-computer-name"></a><a name="cannot_connect"></a> Отладчику не удалось подключиться к удаленному компьютеру. Отладчику не удалось разрешить указанное имя компьютера.

Попробуйте выполнить следующие действия.

1. Введите допустимое имя компьютера и допустимый номер порта в диалоговом окне **Присоединение к процессу** или в свойствах проекта (если необходимо задать свойства, см. [эти инструкции](#server_incorrect)). Имя компьютера должно иметь следующий формат:

    `computername:port`

    > [!NOTE]
    > Номер порта должен совпадать с [номером порта удаленного отладчика](../debugger/remote-debugger-port-assignments.md), который *должен выполняться* на конечном компьютере.

2. Если имя компьютера не работает, попробуйте использовать IP-адрес и номер порта.

3. Убедитесь в том, что версия удаленного отладчика, выполняемого на конечном компьютере, соответствует вашей версии Visual Studio. Чтобы узнать правильную версию удаленного отладчика, см. раздел [Удаленная отладка](../debugger/remote-debugging.md).

    > [!TIP]
    > Если при присоединении к процессу вы успешно подключаетесь, но не видите нужный процесс, установите флажок **Показать процессы, запущенные всеми пользователями**. В результате будут показаны процессы, запущенные с использованием других учетных записей пользователей.

4. Если эти действия не помогли устранить ошибку, см. раздел [Удаленный компьютер недоступен](#dns).

## <a name="connection-request-was-rejected-by-the-remote-debugger"></a><a name="rejected"></a> Запрос на подключение был отклонен удаленным отладчиком.

Убедитесь в том, что имя удаленного компьютера и номер порта в диалоговом окне **Присоединение к процессу** или в свойствах проекта соответствуют отображаемым в окне удаленного отладчика. Если имеются расхождения, исправьте их и повторите попытку.

Если эти значения верны, но в сообщении упоминается режим **проверки подлинности Windows**, убедитесь в том, что удаленный отладчик находится в правильном режиме проверки подлинности (**Сервис > Параметры**).

## <a name="connection-with-the-remote-endpoint-was-terminated"></a><a name="connection_terminated"></a> Подключение к удаленной конечной точке завершено.

При отладке приложения Службы приложений Azure попробуйте использовать команду [Присоединить отладчик](../debugger/remote-debugging-azure.md#remote_debug_azure_app_service) из Cloud Explorer или обозревателя сервера вместо команды **Присоединиться к процессу**.

Если для отладки используется диалоговое окно **Присоединение к процессу**, выполните указанные ниже действия.

- Убедитесь в том, что имя удаленного компьютера и номер порта в диалоговом окне **Присоединение к процессу** или в свойствах проекта соответствуют отображаемым в окне удаленного отладчика. Если имеются расхождения, исправьте их и повторите попытку.

- Если вы пытаетесь подключиться по имени узла, попробуйте использовать вместо него IP-адрес.

- Проверьте журнал приложений на сервере (средство "Просмотр событий" в Windows), чтобы получить более подробные сведения для устранения проблемы.

- В противном случае попробуйте перезапустить Visual Studio с правами администратора и повторить попытку.

## <a name="invalid-access-to-memory-location"></a><a name="invalid_access"></a> Недопустимый доступ к участку памяти.

Внутренняя ошибка. Перезапустите Visual Studio и повторите попытку.

## <a name="there-is-no-server-by-the-specified-name-running-on-the-remote-computer"></a><a name="no_server"></a> На этом удаленном компьютере сервер с указанным именем отсутствует.

Visual Studio не удалось подключиться к удаленному отладчику. Это сообщение может появляться по нескольким причинам.

- Удаленный отладчик может быть запущен с другой учетной записью пользователя. См. [эти инструкции](#user_accounts).

- Порт блокируется в брандмауэре. Убедитесь в том, что брандмауэр [не блокирует ваш запрос](#firewall), особенно если используется сторонний брандмауэр.

- Версия удаленного отладчика не соответствует Visual Studio. Чтобы узнать правильную версию удаленного отладчика, см. раздел [Удаленная отладка](../debugger/remote-debugging.md).

## <a name="the-requested-name-was-valid-but-no-data-of-the-requested-type-was-found"></a><a name="valid_name"></a> Запрошенное имя допустимо, но данные запрошенного типа не найдены.

Удаленный компьютер существует, но Visual Studio не удалось подключиться к удаленному отладчику. Это сообщение может появляться по нескольким причинам.

- Ошибка DNS препятствует подключению. См. [эти инструкции](#dns).

- Удаленный отладчик может быть запущен с другой учетной записью пользователя. Выполните [следующие действия](#user_accounts).

- Порт блокируется в брандмауэре. Убедитесь в том, что брандмауэр [не блокирует ваш запрос](#firewall), особенно если используется сторонний брандмауэр.

- Версия удаленного отладчика не соответствует Visual Studio. Чтобы узнать правильную версию удаленного отладчика, см. раздел [Удаленная отладка](../debugger/remote-debugging.md).

## <a name="the-visual-studio-remote-debugger-on-the-target-computer-cannot-connect-back-to-this-computer"></a><a name="cant_connect_back"></a> Удаленный отладчик Visual Studio на удаленном компьютере не может подключиться к этому компьютеру.

Удаленный отладчик может быть запущен с другой учетной записью пользователя. В удаленном отладчике выберите пункт **Сервис > Разрешения**, чтобы добавить пользователя в список разрешений удаленного отладчика. Дополнительные сведения см. в разделе [Удаленный отладчик запущен с использованием другой учетной записи пользователя](#user_accounts).

Если в сообщении об ошибке также упоминается брандмауэр, то брандмауэр на локальном компьютере может препятствовать передаче данных с удаленного компьютера в Visual Studio. См. [эти инструкции](#firewall).

## <a name="access-denied"></a><a name="access_denied"></a> Доступ запрещен

Эта ошибка может возникать при попытке выполнить отладку на 64-разрядном удаленном компьютере с 32-разрядного компьютера (такая возможность не поддерживается).

## <a name="a-security-package-specific-error-occurred"></a><a name="security_package"></a> Ошибка в пакете безопасности.

Это может быть устаревшая проблема, характерная для Windows XP и Windows 7. См. [эти сведения](https://stackoverflow.com/questions/4786016/unable-to-connect-to-the-microsoft-remote-debugging-monitor-a-security-package).

## <a name="causes-and-recommendations"></a>Причины и рекомендации

### <a name="the-remote-machine-is-not-reachable"></a><a name="dns"></a> Удаленный компьютер недоступен

Если вы не можете подключиться с помощью имени удаленного компьютера, попробуйте использовать IP-адрес. Для получения IPv4-адреса можно использовать `ipconfig` в командной строке на удаленном компьютере. Если вы используете файл HOSTS, убедитесь в том, что он настроен правильно.

Если происходит сбой, убедитесь в том, что удаленный компьютер доступен по сети ([проверьте связь](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee624059(v=ws.10)) с ним). Удаленная отладка через Интернет не поддерживается, за исключением некоторых сценариев Microsoft Azure.

### <a name="the-server-name-is-incorrect-or-third-party-software-is-interfering-with-the-remote-debugger"></a><a name="server_incorrect"></a> Неправильное имя сервера, или стороннее программное обеспечение мешает удаленному отладчику.

В Visual Studio просмотрите свойства проекта и убедитесь в том, что имя сервера указано правильно. См. разделы для [C# и Visual Basic](../debugger/remote-debugging-csharp.md#remote_csharp) и для [C++](../debugger/remote-debugging-cpp.md#remote_cplusplus). Для ASP.NET откройте **Свойства > Веб > Серверы** или **Свойства > Отладка** в зависимости от типа проекта.

> [!NOTE]
> При присоединении к процессу удаленные параметры в свойствах проекта не используются.

Если имя сервера указано правильно, то антивирусная программа или сторонний брандмауэр могут блокировать удаленный отладчик. При локальной отладке эта ошибка может возникать из-за того, что Visual Studio является 32-разрядным приложением, поэтому для отладки 64-разрядных приложений используется 64-разрядная версия удаленного отладчика. 32- и 64-разрядный процессы взаимодействуют друг с другом по локальной сети на локальном компьютере. Сетевой трафик не отправляется с компьютера, но приложение для обеспечения безопасности от сторонних разработчиков может блокировать обмен данными.

### <a name="the-remote-debugger-is-running-under-a-different-user-account"></a><a name="user_accounts"></a> Удаленный отладчик запущен с использованием другой учетной записи пользователя

По умолчанию удаленный отладчик принимает подключения только от пользователя, запустившего удаленный отладчик, и членов группы администраторов. Другим пользователям разрешения должны быть предоставлены явно.

Решить эту проблему можно одним из указанных ниже способов.

- Добавить пользователя Visual Studio в список разрешений удаленного отладчика можно, выбрав пункт **Сервис > Разрешения**.

- На удаленном компьютере перезапустите удаленный отладчик с той же учетной записью пользователя и паролем, что и на компьютере с Visual Studio.

    > [!NOTE]
    > Если удаленный отладчик запущен на удаленном сервере, щелкните правой кнопкой мыши приложение удаленного отладчика и выберите пункт **Запуск от имени администратора** (можно также запустить удаленный отладчик как службу). Если он запущен не на удаленном сервере, просто запустите его в обычном режиме.

- Удаленный отладчик можно запустить из командной строки с параметром **/allow \<имя_пользователя>** параметр: `msvsmon /allow <username@computer>`.

- Кроме того, можно разрешить любому пользователю выполнять удаленную отладку. В окне удаленного отладчика откройте диалоговое окно **Сервис > Параметры**. Если выбрать   **Без аутентификации**, то затем можно установить флажок **Разрешить отладку любому пользователю**. Однако этот параметр следует использовать, если другие параметры не работают или если вы находитесь в частной сети.

### <a name="the-firewall-on-the-remote-machine-doesnt-allow-incoming-connections-to-the-remote-debugger"></a><a name="firewall"></a> Брандмауэр на удаленном компьютере запрещает входящие подключения к удаленному отладчику
 Брандмауэры на компьютере Visual Studio и на удаленном компьютере нужно настроить так, чтобы разрешить обмен данными между Visual Studio и удаленным отладчиком. Информацию о портах, используемых удаленным отладчиком, см. в разделе [Remote Debugger Port Assignments](../debugger/remote-debugger-port-assignments.md). Информацию о настройке брандмауэра Windows см. в разделе [Configure the Windows Firewall for Remote Debugging](../debugger/configure-the-windows-firewall-for-remote-debugging.md).

### <a name="the-version-of-the-remote-debugger-doesnt-match-the-version-of-visual-studio"></a>Версия удаленного отладчика не соответствует версии Visual Studio.
 Запущенная локально версия Visual Studio должна совпадать с версией монитора удаленной отладки, запущенного на удаленном компьютере. Чтобы устранить эту проблему, скачайте и установите соответствующую версию монитора удаленной отладки. Чтобы узнать правильную версию удаленного отладчика, см. раздел [Удаленная отладка](../debugger/remote-debugging.md).

### <a name="the-local-and-remote-machines-have-different-authentication-modes"></a>На локальном и удаленном компьютерах используются разные режимы аутентификации
 На локальном и удаленном компьютерах должен использоваться один и тот же режим аутентификации. Чтобы устранить эту проблему, настройте на обоих компьютерах один и тот же режим аутентификации. Можно изменить режим проверки подлинности. В окне удаленного отладчика откройте диалоговое окно **Сервис > Параметры**.

 Более подробную информацию о режимах аутентификации см. в статье [Обзор аутентификации Windows](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831472(v=ws.11)).

### <a name="anti-virus-software-is-blocking-the-connections"></a>Антивирусная программа блокирует подключения.
 Антивирусная программа Windows разрешает подключения к удаленному отладчику, но некоторые антивирусные программы сторонних разработчиков могут блокировать их. Чтобы узнать, как разрешить эти подключения, см. документацию по используемой антивирусной программе.

### <a name="network-security-policy-is-blocking-communication-between-the-remote-machine-and-visual-studio"></a>Политика сетевой безопасности блокирует обмен данными между удаленным компьютером и Visual Studio.
 Проверьте, не блокирует ли политика сетевой безопасности обмен данными. Дополнительные сведения о политике сетевой безопасности Windows см. в статье [Параметры политики безопасности](/windows/device-security/security-policy-settings/security-policy-settings).

### <a name="the-network-is-too-busy-to-support-remote-debugging"></a>Удаленная отладка невозможна из-за слишком высокой загрузки сети.
 Попробуйте выполнить удаленную отладку в другое время или перепланировать работу в сети на другое время.

## <a name="more-help"></a>Дополнительная справка
 Чтобы получить дополнительную справку по удаленному отладчику, откройте страницу справки (**Справка > Использование** в удаленном отладчике).

## <a name="see-also"></a>См. также
- [Remote Debugging](../debugger/remote-debugging.md)
