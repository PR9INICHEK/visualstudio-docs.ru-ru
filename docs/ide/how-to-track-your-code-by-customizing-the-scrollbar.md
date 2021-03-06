---
title: Режим полосы и режим карты для полосы прокрутки
ms.date: 03/20/2020
ms.topic: how-to
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5d1b659dabed2337013ffb84ff48277f0edacb09
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85283987"
---
# <a name="how-to-customize-the-scroll-bar"></a>Практическое руководство. Настройка полосы прокрутки

Когда вы работаете с длинными файлами кода, может быть трудно запомнить расположение элементов в файле. Вы можете настроить полосу прокрутки в редакторе кода, чтобы лучше понимать, что происходит в коде.

## <a name="annotations"></a>Заметки

Можно выбрать, должны ли на полосе прокрутки отображаться заметки, такие как изменения в коде, точки останова, закладки, ошибки и положение курсора.

   1. Откройте страницу параметров **Полосы прокрутки**. Для этого последовательно выберите **Средства** > **Параметры** > **Текстовый редактор** > **Все языки** > **Полосы прокрутки**.

   2. Установите флажок **Показывать примечания над вертикальной полосой прокрутки**, а затем выберите нужные заметки. Доступны следующие заметки:

      - изменения
      - метки
      - ошибки
      - положение курсора.

      > [!TIP]
      > Параметр **Показывать метки** включает точки останова и закладки.

Посмотрите, как он работает. Для этого откройте большой файл кода и замените любой текст, который повторяется в нескольких местах в файле. На полосе прокрутки отображаются результаты замены, поэтому вы сможете отменить операцию, если изменили что-то не то.

Вот как выглядит полоса прокрутки после поиска строки. Обратите внимание, что все экземпляры строки отображаются на полосе прокрутки.

![Полоса прокрутки в Visual Studio после поиска строки](../ide/media/enhancedscrollbarsearch.png)

Вот как выглядит полоса прокрутки после замены всех экземпляров строки. Красные метки на полосе прокрутки обозначают места, где из-за изменения текста появились ошибки.

![Полоса прокрутки в Visual Studio после замены строки с ошибками](../ide/media/enhancedscrollbarreplace.png)

## <a name="display-modes"></a>Режимы отображения

У полосы прокрутки есть два режима: режим полосы и режим карты.

### <a name="bar-mode"></a>Режим полосы

В *режиме полосы* индикаторы заметок отображаются на полосе прокрутки. Если щелкнуть полосу прокрутки, вместо перехода к определенному месту в файле страница будет прокручена вверх или вниз.

### <a name="map-mode"></a>Режим карты

В *режиме карты* показано миниатюрное изображение строк кода на полосе прокрутки. Вы можете задать ширину столбца карты, выбрав определенное значение для параметра **Обзор исходного кода**. Чтобы при наведении указателя на карту отображалось более широкое окно предварительного просмотра кода, выберите **Показывать подсказку предварительного просмотра**. Свернутые области затенены иначе. Они развертываются, если дважды щелкнуть их.

> [!TIP]
> Можно отключить миниатюрное представление кода в режиме карты. Для этого задайте для параметра **Обзор исходного кода** значение **Выкл.** Если установлен флажок **Показывать подсказку предварительного просмотра**, окно предварительного просмотра кода все так же будет отображаться в том расположении на полосе прокрутки, на которое вы наведите указатель. А если щелкнуть эту точку, курсор по-прежнему будет в нее перемещаться.

На следующем изображении показано, как выглядит пример поиска в режиме карты со **средней** шириной:

![Полоса прокрутки Visual Studio в режиме карты](../ide/media/enhancedscrollbar.png)

На следующем рисунке показано, как работает параметр **Показывать подсказку предварительного просмотра**:

![Полоса прокрутки Visual Studio и окно с подсказкой](../ide/media/enhancedscrollbarsearchtooltip.png)

> [!TIP]
> Чтобы изменить цвета, отображаемые в режиме карты, последовательно выберите **Сервис** > **Параметры** > **Среда** > **Шрифты и цвета**. Затем в разделе **Отображаемые элементы** выберите любой из элементов, которому предшествует "Overview" (Обзор), измените цвета, а затем нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также

- [Возможности редактора кода](../ide/writing-code-in-the-code-and-text-editor.md)
