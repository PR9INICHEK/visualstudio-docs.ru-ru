---
title: Вкладка "Сообщения", диалоговое окно "Параметры сообщения" | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- message options, Messages
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de50e6fe997ce10266cbb51f2fd91c318ab2bd1f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62905536"
---
# <a name="messages-tab-message-options-dialog-box"></a>Вкладка "Сообщения" диалогового окна "Параметры сообщения"
Вкладка **Сообщения** позволяет выбрать типы сообщений для отображения в [представлении сообщений](../debugger/messages-view.md) и указать условия для поиска сообщений. Чтобы открыть диалоговое окно [Параметры сообщений](../debugger/message-options-dialog-box.md), выберите пункт **Записывать сообщения** в меню **Spy**.

 Обычно удобно выбрать **Группы сообщений**, а затем скорректировать выбор, отмечая отдельные **сообщения для просмотра**. Кнопка **Выделить все** позволяет выбрать все типы сообщений, а кнопка **Очистить все** — отменить выбор всех типов.

 На вкладке **Сообщения** доступны следующие параметры:

 **Сообщения для просмотра** — выберите конкретные сообщения для просмотра. Когда вы создаете новое окно сообщений, в нем могут отображаться все сообщения. Настроенный на вкладке **Сообщения** фильтр применяется только к новым сообщениям, но не к тем, которые уже появились в представлении "Окна".

 **Группы сообщений** — выберите группы сообщений для просмотра. Здесь доступны следующие группы:

- WM_USER — все с кодом не меньше, чем WM_USER.

- Registered — зарегистрированные вызовом функции **RegisterWindowMessage**.

- Unknown — неизвестные сообщения в диапазоне от 0 до (WM_USER-1).

  Обратите внимание, что эти **Группы сообщений** не сопоставляются с конкретными записями в разделе **Сообщения для просмотра**. Выбранная группа напрямую применяется к потоку сообщений.

  Неактивный флажок в списке **Группы сообщений** указывает на то, что список **Сообщения для просмотра** для этой группы изменен, и в ней выбраны не все типы сообщений.

  **Сохранить параметры в качестве параметров по умолчанию** — сохраните текущие параметры, чтобы снова применить их для поиска сообщений позднее. Также параметры автоматически сохраняются при выходе из Spy++.