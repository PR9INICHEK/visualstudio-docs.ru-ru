---
title: Работа с элементами в конструкторе XAML | Документы Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a29690bf-f212-4ac6-a77a-adc53d14102e
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 917d0b66f479789b3cb727aeb822c3f2aa164cff
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47559400"
---
# <a name="working-with-elements-in-xaml-designer"></a>Working with elements in XAML Designer
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [работа с элементами в конструкторе XAML](https://docs.microsoft.com/visualstudio/designers/working-with-elements-in-xaml-designer).  
  
Вы можете добавлять элементы (элементы управления, макеты и фигуры) в приложение на языке XAML в коде или с помощью конструктора XAML. В этом разделе описывается работа с элементами в конструкторе XAML в Visual Studio или Blend для Visual Studio.  
  
## <a name="adding-an-element-to-a-layout"></a>Добавление элемента в макет  
 *Макет* — это процесс изменения размеров и положения элементов в пользовательском интерфейсе. Для размещения визуальных элементов необходимо поместить их в структуру [Панель](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.panel.aspx). `Panel` имеет дочернее свойство, которое является коллекцией типов [FrameworkElement](http://msdn.microsoft.com/library/windows/apps/br208706.aspx). Вы можете использовать различные дочерние элементы `Panel`, такие как [Canvas](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.canvas.aspx), [StackPanel](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.stackpanel.aspx) и [Grid](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.grid.aspx), в качестве контейнеров макета и для размещения и упорядочения элементов на странице.  
  
 По умолчанию панель `Grid` используется в качестве контейнера макета верхнего уровня на странице или форме. Вы можете добавлять панели, элементы управления и другие элементы на макет страницы верхнего уровня.  
  
#### <a name="to-add-an-element-to-a-layout"></a>Добавление элемента в макет  
  
-   В конструкторе XAML выполните одно из следующих действий.  
  
    -   Дважды щелкните элемент на **панели элементов** (или выберите элемент на панели элементов и нажмите клавишу ВВОД).  
  
    -   Перетащите элемент с **панели элементов** в область рисования.  
  
    -   На **панели элементов** выберите один из инструментов рисования (например, [Эллипс](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.shapes.ellipse.aspx) или [Прямоугольник](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.shapes.rectangle.aspx)) и создайте объект на активной панели.  
  
## <a name="changing-the-layering-order-of-elements"></a>Изменение порядка слоев элементов  
 При наличии двух элементов в области рисования в конструкторе XAML один из них будет отображаться перед другим согласно порядку слоев. В нижней части списка элементов в окне "Структура документа" находится первый передний элемент (если не задано свойство **ZIndex** элемента). При вставке элемента на страницу, форму или в контейнер макета элемент автоматически помещается перед другими элементами в активном элементе контейнера. Чтобы изменить порядок элементов, можно использовать команды **Порядок** или перетаскивать элементы в дереве объектов в окне "Структура документа".  
  
#### <a name="to-change-the-layering-order"></a>Изменение порядка слоев  
  
-   Выполните одно из следующих действий.  
  
    -   В окне **Структура документа** перетащите элементы вверх или вниз, чтобы создать требуемый порядок слоев.  
  
    -   Щелкните правой кнопкой мыши в окне "Структура документа" или в области рисования элемент, для которого требуется изменить порядок слоев, наведите указатель на элемент **Порядок** и выберите один из следующих параметров:  
  
        -   **На передний план** — чтобы показывать элемент перед всеми другими элементами.  
  
        -   **Переместить вперед** — чтобы переместить элемент на один уровень вперед.  
  
        -   **Переместить назад** — чтобы переместить элемент на один уровень назад.  
  
        -   **На задний план** — чтобы показывать элемент за всеми другими элементами.  
  
     Измените свойство **ZIndex** в разделе **Макет** окна "Свойства". Для перекрывающихся элементов свойство **ZIndex** имеет приоритет над порядком элементов, показанных в окне "Структура документа". Элемент с меньшим значением свойства **ZIndex** отображается на переднем плане при перекрытии элементов.  
  
## <a name="changing-the-alignment-of-an-element"></a>Изменение выравнивания элемента  
 Вы можете выравнивать элементы в области рисования, используя команды меню или перетаскивая элементы к линиям привязки.  
  
 *Линия привязки* является визуальным средством, помогающим выравнивать элементы относительно других элементов в приложении.  
  
#### <a name="to-align-two-or-more-elements-by-using-menu-commands"></a>Выравнивание нескольких элементов с помощью команд меню  
  
1.  Выберите элементы, которые требуется выровнять. Можно выбрать несколько элементов, нажав и удерживая нажатой клавишу CTRL.  
  
2.  Выберите одно из следующих свойств в поле **HorizontalAlignment** в разделе **Макет** окна "Свойства": **По левому краю**, **По центру**, **По правому краю** или **Растянуть**.  
  
3.  Выберите одно из следующих свойств в поле **VerticalAlignment** в разделе **Макет** окна "Свойства": **По верхнему краю**, **По центру**, **По нижнему краю** или **Растянуть**.  
  
#### <a name="to-align-two-or-more-elements-by-using-snaplines"></a>Выравнивание нескольких элементов с помощью линий привязки  
  
-   В конструкторе XAML в макете, который содержит по крайней мере два элемента, перетащите один из элементов или измените его размер, чтобы его край был выровнен с другим элементом.  
  
     Когда края будут выровнены, появится *граница выравнивания*. Граница выравнивания отображается как красная пунктирная линия. Границы выравнивания появляются, только если **привязка к линиям привязки** включена. Изображение области рисования с границей выравнивания см. в разделе [Создание пользовательского интерфейса с помощью конструктора XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).  
  
## <a name="changing-the-an-elements-margins"></a>Изменение полей элемента  
 Поля в конструкторе XAML определяют пустое пространство вокруг элемента в области рисования. Например, поля определяют расстояние между внешними краями элемента и границами панели `Grid`, содержащей элемент. Поля также определяют расстояние между элементами в `StackPanel`.  
  
#### <a name="to-change-an-elements-margins-in-the-properties-window"></a>Изменение полей элемента в окне "Свойства"  
  
1.  Выберите элемент, поля которого требуется изменить.  
  
2.  В разделе **Макет** окна "Свойства" измените значение (в пикселях или в аппаратно-независимых единицах, равных приблизительно 1/96 дюйма) для любого из свойств **полей** (**Верхнее**, **Левое**, **Правое** или **Нижнее**).  
  
#### <a name="to-change-an-elements-margins-in-the-artboard"></a>Изменение полей элемента в области рисования  
  
-   Чтобы изменить поля элемента относительно его контейнера макета, щелкните *графические элементы полей*, отображаемые вокруг элемента в области рисования, когда элемент выбран и находится в пределах контейнера макета. Изображение графических элементов полей см. в разделе [Создание пользовательского интерфейса с помощью конструктора XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).  
  
     Если графический элемент поля открыт по вертикали или по горизонтали, значение поля не задано. Если графический элемент поля закрыт, это поле установлено.  
  
     Если вы открываете графический элемент поля, а противоположное поле не задано, противоположному полю будет задано верное значение в соответствии с расположением элемента на монтажной панели. Для противоположных полей, например полей **Слева** и **Справа**, всегда будет задано хотя бы одно значение.  
  
    > [!IMPORTANT]
    >  У элементов, помещенных в некоторые контейнеры макета, такие как <xref:Windows.UI.Xaml.Controls.Canvas>, нет графических элементов полей. У элементов, помещенных в <xref:Windows.UI.Xaml.Controls.StackPanel>, есть графические элементы для левого и правого поля или верхнего и нижнего поля в зависимости от ориентации `StackPanel`.  
  
## <a name="grouping-and-ungrouping-elements"></a>Группировка и разгруппировка элементов  
 При группировке двух или более элементов в конструкторе XAML создается новый контейнер макета, а эти элементы размещаются в этом контейнере. Если разместить два или более элемента в контейнере макета, вы сможете легко выбирать, перемещать и преобразовывать группу так, будто бы элементы представляют один элемент. Группировка также полезна для обнаружения элементов, которые связаны друг с другом определенным образом, например кнопок, составляющих элемент навигации. При разгруппировке элементов вы просто удаляете контейнер макета, содержащий эти элементы.  
  
#### <a name="to-group-elements-into-a-new-layout-container"></a>Группировка элементов в новом контейнере макета  
  
1.  Выберите элементы, которые необходимо сгруппировать. (Чтобы выбрать несколько элементов, нажмите и удерживайте клавишу CTRL при их выборе.)  
  
2.  Щелкните выделенные элементы правой кнопкой, наведите указатель на команду **Сгруппировать в**, а затем выберите тип контейнера макета, в котором будет размещена группа.  
  
    > [!TIP]
    >  Если выбрать <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border>, или <xref:Windows.UI.Xaml.Controls.ScrollViewer> для группировки элементов, они размещаются в новой панели <xref:Windows.UI.Xaml.Controls.Grid> в <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border> или <xref:Windows.UI.Xaml.Controls.ScrollViewer>. Если разгруппировать элементы в одном из этих контейнеров макета, удаляется только <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border> или <xref:Windows.UI.Xaml.Controls.ScrollViewer>, а панель <xref:Windows.UI.Xaml.Controls.Grid> сохраняется. Чтобы удалить панель `Grid`, разгруппируйте элементы еще раз.  
  
#### <a name="to-ungroup-elements-and-delete-the-layout"></a>Разгруппировка элементов и удаление макета  
  
-   Щелкните правой кнопкой мыши группу, которую необходимо разгруппировать, и выберите пункт **Разгруппировать**.  
  
 Также можно группировать и разгруппировывать элементы, щелкнув правой кнопкой мыши выбранные элементы в окне "Структура документа" и выбрав пункт **Сгруппировать в** или **Разгруппировать**.  
  
## <a name="resetting-the-element-layout"></a>Переустановка макета элемента  
 Вы можете восстановить значения по умолчанию для отдельных свойств макета элемента с помощью команд переустановки макета. С помощью этой команды можно переустановить поля, выравнивание, ширину, высоту и размер одного или группы элементов.  
  
#### <a name="to-reset-the-element-layout"></a>Чтобы переустановить макет элемента  
  
-   В окне "Структура документа" или в области рисования щелкните правой кнопкой мыши элемент и последовательно выберите **Макет**, **Сброс** *имя_свойства*, где *имя_свойства* — это свойство, которое нужно переустановить (или выберите **Макет**, **Сбросить все**, чтобы переустановить все свойства макета элемента).  
  
## <a name="see-also"></a>См. также  
 [Создание пользовательского интерфейса с помощью конструктора XAML в Visual Studio](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)


