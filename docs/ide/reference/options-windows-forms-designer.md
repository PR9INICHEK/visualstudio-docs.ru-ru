---
title: Параметры, конструктор Windows Forms, общие
ms.date: 08/09/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.WindowsFormsDesigner.General
helpviewer_keywords:
- Windows Forms Designer options
- Options dialog box, Windows Forms Designer
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: 2a72b27dc2277501d0e0957c8b89b551f4d6852d
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "75568065"
---
# <a name="options-dialog-box-windows-forms-designer"></a>Диалоговое окно "Параметры": Конструктор Windows Forms

На странице параметров конструктора Windows Forms можно задать параметры сетки и другие функции конструктора Windows Forms в Visual Studio. Откройте диалоговое окно **Параметры** в меню **Средства**.

## <a name="code-generation-settings"></a>Настройки создания кода

**Создание оптимизированного кода**\
Включает функцию создания оптимизированного кода. Некоторые элементы управления могут быть несовместимы с этим режимом. Чтобы изменение этого параметра вступило в силу, необходимо закрыть и повторно открыть Visual Studio.

## <a name="high-dpi-support"></a>Поддержка высокого DPI

**Уведомления о масштабировании DPI**\
Показывает в конструкторе Windows Forms сообщение о том, что можно перезапустить Visual Studio со 100%-ным масштабированием. Дополнительные сведения см. в статье об [отключении поддержки определения DPI в Visual Studio](/dotnet/framework/winforms/disable-dpi-awareness-visual-studio).

## <a name="layout-settings"></a>Параметры макета

**Размер ячейки таблицы по умолчанию**\
Задает интервал в пикселях между горизонтальной и вертикальной линиями сетки в конструкторе. Размер по умолчанию составляет 8 и 8. Максимальный размер составляет 200 и 200.

**Режим макета**\
Задает систему выравнивания для макета. Доступны значения SnapToGrid (Привязать к сетке) и "Линии привязки".

**Показать сетку**\
Определяет, отображается ли в конструкторе размерная сетка. По умолчанию сетка отображается.

**Привязка к сетке**\
Определяет, будет ли конструктор привязывать объекты и элементы управления к сетке. Иными словами, изменение размера элементов и их перемещение в конструкторе ограничено шагом GridSize, когда эта функция включена. Параметр SnapToGrid позволяет точно выравнивать компоненты пользовательского интерфейса, но ограничивает возможности произвольного размещения элементов управления. По умолчанию параметр SnapToGrid включен.

## <a name="object-bound-smart-tag-settings"></a>Параметры смарт-тегов, привязанных к объектам

**Автоматически открывать смарт-теги**\
Определяет, будут ли элементы управления и компоненты отображать смарт-теги. Не все элементы управления и компоненты поддерживают смарт-теги.

## <a name="refactoring"></a>Рефакторинг

**Включить рефакторинг при переименовании**\
Если задано значение `true`, выполняется операция оптимизации кода с помощью переименования при переименования компонента в окне свойств или окне структуры документа.

## <a name="toolbox"></a>Панель элементов

**Автоматически заполнять панель элементов**\
Определяет, автоматически ли заполняется окно панели элементов компонентами и элементами управления, создаваемыми проектом.
