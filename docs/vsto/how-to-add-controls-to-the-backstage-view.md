---
title: 'Как добавить элементы управления в представление Backstage '
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- customizing the Ribbon, menus
- controls, Ribbon
- menus, customizing
- Microsoft Office Button
- custom Ribbon, menus
- Ribbon, customizing
- Office button
- Ribbon, menus
- Microsoft Office Menu
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5b4ea5cdcd869f16f987e9431359511831af9573
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85538350"
---
# <a name="how-to-add-controls-to-the-backstage-view"></a>Как добавить элементы управления в представление Backstage
  Конструктор ленты можно использовать для добавления элементов управления в меню, которое открывается, если щелкнуть вкладку **файл** . При запуске приложения элементы управления, добавляемые на вкладку « **файл** », отображаются в группе « **надстройки**».

 Элементы управления нельзя размещать до или после встроенных элементов управления с помощью конструктора ленты в Visual Studio. Встроенный элемент управления — это элемент управления, который уже отображается в представлении Backstage. Если необходимо разместить элементы управления до или после встроенных элементов управления, необходимо использовать ленту XML. Дополнительные сведения о **ленте (XML)** см. в разделе [Ribbon XML](../vsto/ribbon-xml.md). Дополнительные сведения о настройке представления Backstage см. в статье [Введение в представление Backstage office 2010 для разработчиков](/previous-versions/office/developer/office-2010/ee691833(v=office.14)) и [Настройка представления Backstage для разработчиков Office 2010](/previous-versions/office/developer/office-2010/ee815851(v=office.14)).

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

### <a name="to-add-controls-to-backstage-view"></a>Добавление элементов управления в представление Backstage

1. Откройте элемент лента в представление конструирования.

     Дополнительные сведения о добавлении элемента **Лента (визуальный конструктор)** в проект см. [в разделе как приступить к настройке ленты](../vsto/how-to-get-started-customizing-the-ribbon.md).

2. В конструкторе ленты перейдите на вкладку **файл** .

     Откроется конструктор меню. Эта область конструктора не содержит элементов управления.

3. На вкладке **панели элементов** **ленты Office** перетащите в конструктор меню любой из следующих элементов управления:

    - Кнопка

    - CheckBox

    - Коллекции

    - Меню

    - Separator

    - SplitButton

    - ToggleButton

4. Перетащите элементы управления, чтобы переместить их в новое положение в меню.

## <a name="see-also"></a>См. также раздел
- [Общие сведения о ленте](../vsto/ribbon-overview.md)
- [Конструктор лент](../vsto/ribbon-designer.md)
- [XML-ленты](../vsto/ribbon-xml.md)
- [Как начать настройку ленты](../vsto/how-to-get-started-customizing-the-ribbon.md)
- [Пошаговое руководство. Создание настраиваемой вкладки с помощью конструктора лент](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
