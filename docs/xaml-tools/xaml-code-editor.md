---
title: Редактор кода XAML
description: Ознакомьтесь с редактором кода XAML в Visual Studio
ms.date: 06/16/2020
ms.topic: overview
monikerRange: vs-2019
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: 6421fd0139b04262ac5f1e835f010c1372c034ee
ms.sourcegitcommit: 57d96de120e0574e506dfd80bb7adfbac73f96be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85329178"
---
# <a name="xaml-code-editor"></a>Редактор кода XAML

Редактор кода XAML в [интегрированной среде разработки Visual Studio](../get-started/visual-studio-ide.md) включает все средства, необходимые для создания приложений WPF и UWP для платформы Windows и для [Xamarin. Forms](/xamarin/xamarin-forms/user-interface/text/editor/). В этой статье описываются обе роли, выполняемые редактором кода при разработке приложений на основе XAML, и функции, которые являются уникальными для редактора кода XAML в Visual Studio 2019.

Для начала давайте взглянем на среду IDE (интегрированная среда разработки) с открытым проектом WPF. На следующем рисунке показано несколько ключевых средств интегрированной среды разработки, которые будут использоваться вместе с редактором кода XAML.

:::image type="content" source="media/xaml-code-editor-overview-sml.png" alt-text="Интегрированная среда разработки Visual Studio 2019 с открытым проектом WPF в XAML" lightbox="media/xaml-code-editor-overview-lrg.png":::

В левом нижнем углу изображения, идущего по часовой стрелке, используются следующие средства интегрированной среды разработки:

- В окне **[редактора кода XAML](#xaml-code-editor-ui)** &mdash; находится тема этой статьи, &mdash; где вы создаете и редактируете код.
- Окно **[конструктор XAML](creating-a-ui-by-using-xaml-designer-in-visual-studio.md)** , в котором вы разрабатываете пользовательский интерфейс.
- Закрепляемое окно **[панели элементов](../ide/reference/toolbox.md)** , в которое добавляются элементы управления в пользовательский интерфейс.
- Кнопка **[Отладка](../debugger/debugger-feature-tour.md)** , в которой выполняется код и производится его отладка. <br>(Можно также изменить код в режиме реального времени во время отладки с помощью [горячей перезагрузки XAML](xaml-hot-reload.md).)
- Окно **[Обозреватель решений](../ide/solutions-and-projects-in-visual-studio.md)** , в котором можно управлять файлами, проектами и решениями.
- Окно **[Свойства](../ide/reference/properties-window.md)** , в котором можно изменить вид пользовательского интерфейса и принципы работы элементов управления пользовательского интерфейса.

Чтобы продолжить, давайте подробнее рассмотрим редактор кода XAML.

## <a name="xaml-code-editor-ui"></a>Пользовательский интерфейс редактора кода XAML

Хотя окно редактора кода для приложений XAML использует некоторые элементы ПОЛЬЗОВАТЕЛЬСКОГО интерфейса (пользовательский интерфейс), которые также отображаются в нашей стандартной интегрированной среде разработки, он также включает несколько уникальных функций, упрощающих разработку приложений XAML.

Вот как выглядит окно редактора кода XAML.

![Окно редактора кода XAML в Visual Studio](media/xaml-code-editor-window.png "Снимок экрана: окно редактора кода XAML в Visual Studio 2019")

Теперь рассмотрим функции каждого из элементов пользовательского интерфейса в редакторе кода.

### <a name="first-row"></a>Первая строка

В первой строке в верхней части окна кода XAML в левой части находится вкладка **конструктор** , кнопка **панели переключения** , вкладка **XAML** и кнопка **XAML** .

![Первая из двух верхних строк в окне редактора кода XAML в Visual Studio с левой стороны первой выделенной строки](media/xaml-code-editor-top-row-left.png "Снимок экрана первой из двух верхних строк в окне редактора кода XAML в Visual Studio 2019, в которых выделены элементы пользовательского интерфейса слева")

Вот как они работают:

- Вкладка **конструктор** меняет фокус с редактора кода XAML на конструктор XAML.
- Кнопка **Переставить панели** изменяет расположение конструктор XAML и редактора кода XAML в интегрированной среде разработки.
- Вкладка **XAML** изменяет фокус обратно на редактор кода XAML.
- Кнопка открыть **XAML** создает отдельное окно редактора кода XAML, которое находится за пределами интегрированной среды разработки.

По продолжению справа есть кнопка **вертикального разделения** , кнопка **горизонтального разбиения** и кнопка **свертывания областей** .

![Первая из двух верхних строк в окне редактора кода XAML в Visual Studio с правой стороны первой выделенной строки](media/xaml-code-editor-top-row-right.png "Снимок экрана: первая из двух верхних строк в окне редактора кода XAML в Visual Studio 2019, в которой выделены элементы пользовательского интерфейса справа")

Вот как они работают:

- Кнопка **вертикального разбиения** изменяет положение конструктор XAML и редактора кода XAML в IDE с горизонтального выравнивания на вертикальное выравнивание.
- Кнопка **горизонтального разбиения** изменяет положение конструктор XAML и редактора кода XAML в IDE с вертикального выравнивания на горизонтальное выравнивание.
- Кнопка **свертывания панели** позволяет свернуть содержимое нижней панели, будь то редактор кода или конструктор. (Чтобы восстановить нижнюю панель, снова нажмите ту же кнопку, которая теперь называется кнопкой **развернуть область** .)

<!-- [!TIP]
> You can run two parallel instances of the XAML code editor concurrently by using both the **Pop Out XAML** button and the **Expand Pane** button.
>
> You might find it useful to have one larger window open that reveals more of your code in context and a smaller pane open that has its focus directly on the code that you're working on. -->

### <a name="second-row"></a>Вторая строка

Во второй строке в верхней части окна кода XAML есть два раскрывающихся списка в окне. Однако если просмотреть подсказку для этих элементов пользовательского интерфейса, она будет дополнительно определять их как "Element: Window" и "Member: Window".

![Вторая из двух верхних строк в окне редактора кода XAML в Visual Studio, где отображаются оба раскрывающихся списка окна](media/xaml-code-editor-top-row-windows.png "Снимок экрана второй из двух верхних строк окна редактора кода XAML в Visual Studio 2019, в котором отображаются оба раскрывающихся списка окна")

Раскрывающиеся списки окон имеют различные функции, как показано ниже.

- **Элемент: окно** , расположенное слева, позволяет просматривать и переходить к родственному элементу или родительским элементам.

  В частности, он показывает представление структуры кода с помощью структуры тегов. При выборе из списка фокус в редакторе кода будет привязан к строке кода, включающей выбранный элемент.

    ![Раскрывающийся список Element: Window в Visual Studio](media/xaml-element-window-dropdown.png "Снимок экрана: раскрывающийся список «элемент» в Visual Studio 2019")

- **Окно Member: Window** справа позволяет просматривать атрибут или дочерние элементы и переходить к ним.

    В частности, он показывает список свойств в коде. При выборе из списка фокус в редакторе кода будет привязан к строке кода, включающей выбранное свойство.

    ![Раскрывающийся список Member: Window в Visual Studio](media/xaml-member-window-dropdown.png "Снимок экрана: раскрывающийся список «элемент» в Visual Studio 2019")

### <a name="middle-pane-code-editor"></a>Средняя область, редактор кода

Средней областью является часть "Code" редактора кода XAML. Он включает большинство функций, которые можно найти в [редакторе кода интегрированной среды разработки](../get-started/tutorial-editor.md). Мы будем касаться некоторых функций универсальной среды разработки, которые могут помочь при разработке кода XAML. Кроме того, в интегрированной среде разработки также будут выделяться функции уникальности для XAML.

![Редактор кода XAML, только посрединная панель, в Visual Studio](media/xaml-code-editor-middle.png "Снимок экрана редактора кода XAML, только средней панели, в Visual Studio 2019")

#### <a name="quick-actions"></a>Быстрые действия

[Быстрые действия](../ide/quick-actions.md) можно использовать для рефакторинга, создания или изменения кода с помощью одного действия.

Например, одна полезная задача, которую можно выполнить с помощью быстрых действий, состоит в **удалении ненужных using** из кода C# на вкладке **MainWindow.XAML.CS** .

Это делается так.

1. Наведите указатель мыши на инструкцию using, щелкните значок лампочки, а затем в раскрывающемся списке выберите **удалить ненужные операторы using** .

    ![Параметр "удалить ненужные использования using" редактора IDE в меню "быстрые действия"](media/xaml-code-editor-remove-usings.png "Снимок экрана: параметр "удалить ненужные параметры using" редактора IDE в меню "быстрые действия"")

1. Выберите, следует ли исправить все вхождения в **документе**, **проекте**или **решении**.
1. Откройте диалоговое окно **предварительного просмотра** и нажмите кнопку **Применить**.

Вы также можете получить доступ к этой функции из строки меню. Для этого выберите **изменить**  >  **IntelliSense**  >  **Удалить и сортировать с помощью**.

Дополнительные сведения об использовании параметров см. на странице [Сортировка с использованием](../ide/reference/sort-usings.md) . Дополнительные сведения о технологии IntelliSense см. на странице [IntelliSense в Visual Studio](../ide/using-intellisense.md) . Дополнительные сведения о некоторых типичных способах использования быстрых действий разработчиками см. на странице [Общие быстрые действия](../ide/common-quick-actions.md) .

#### <a name="change-tracking"></a>Change tracking

С помощью цвета левого поля окна можно отслеживать изменения, внесенные в файл. Вот как цвета связаны с выполняемыми вами действиями:

- Изменения, внесенные с момента открытия файла, но не сохраненные, обозначаются **желтой** полосой на левом поле (называется полем выбора).

    ![Редактирование редактора кода с помощью желтой черты](media/code-editor-edit-yellow.png "Снимок экрана редактора кода с изменением, отмеченным желтой полосой в поле выбора.")

- После сохранения изменений (но перед закрытием файла) панель становится **зеленой**.

    ![Редактирование редактора кода с помощью зеленой панели](media/code-editor-edit-green.png "Снимок экрана редактора кода с изменением, отмеченным зеленой линией в поле выбора.")

Чтобы отключить и включить эту функцию, измените параметр **Track Changes** в параметрах **текстового редактора** (**Сервис**  >  **Параметры**  >  **текстовый редактор**).

Дополнительные сведения об отслеживании изменений &mdash; для включения волнистых линий (также называемых «волнистыми»), отображаемых в разделе строки кода, &mdash; см. в разделе **[функции редактора](../ide/writing-code-in-the-code-and-text-editor.md#editor-features)** статьи [функции редактора кода Visual Studio](../ide/writing-code-in-the-code-and-text-editor.md) .

#### <a name="right-click-context-menu"></a>Контекстное меню, которое следует щелкнуть правой кнопкой мыши

При редактировании кода в редакторе кода XAML существует несколько функций, доступ к которым можно получить с помощью контекстного меню щелчка правой кнопкой мыши. Большинство этих функций доступны в интегрированной среде разработки Visual Studio, а некоторые — только для использования редактора кода вместе с окном конструктора.

![Контекстное меню редактора кода XAML в Visual Studio, которое можно щелкнуть правой кнопкой мыши](media/xaml-code-editor-right-click-menu.png "Снимок экрана: контекстное меню редактора кода XAML, которое можно щелкнуть правой кнопкой мыши в Visual Studio 2019")

Вот что делает каждая функция и как она полезна:

- **Просмотр кода** — открывает окно кода языка программирования, которое обычно открывается рядом с представлением по умолчанию, включающим окно конструктора и редактор кода XAML.
- **Конструктор представлений** — открывает представление по умолчанию, включающее окно конструктора и редактор кода XAML. (Если вы уже используете представление по умолчанию, это не делает ничего.)
- **Быстрые действия и рефакторинг** — пересчеты, создание или изменение кода с помощью одного действия. При наведении указателя мыши на код вы увидите значок лампочки при наличии быстрого действия или рефакторинга. <br>См. также [быстрые действия](../ide/quick-actions.md) и [рефакторинг кода](../ide/refactoring-in-visual-studio.md).
- **Переименовать...** — Переименовывает только пространства имен. Если у вас нет пространства имен для переименования, появится сообщение об ошибке "только префиксы пространства имен могут быть переименованы".
- **Удаление и сортировка пространств имен** — удаляет неиспользуемые пространства имен, а затем сортирует оставшиеся пространства имен.
- **Показать определение** — предварительный просмотр определения типа, не оставляя текущего расположения в редакторе. <br>См. также: Просмотр [определения](../ide/go-to-and-peek-definition.md#peek-definition) и [Просмотр и изменение кода с помощью команды "Показать определение](../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)".
- **Переход к определению** — переход к источнику типа или члена и открытие результата на новой вкладке. <br>См. также: [Переход к определению](../ide/go-to-and-peek-definition.md#go-to-definition).
- **Окружить...** — Используйте окружающие фрагменты кода, которые добавляются вокруг выбранного блока кода. <br>См. также: [фрагменты расширения и окружающие фрагменты кода](../ide/code-snippets.md#expansion-snippets-and-surround-with-snippets).
- **Вставить фрагмент** — вставляет фрагмент кода в позицию курсора.
- **Вырезание** -самостоятельное пояснение
- **Копирование** -самостоятельное пояснение
- **Вставка** — пояснения
- **Структурирование** — разворачивание и сворачивание разделов кода. <br>См. также: [структурирование](../ide/outlining.md).
- **Система управления версиями** — Просмотр истории вкладов кода в репозиторий с открытым кодом.

### <a name="middle-pane-scroll-bar"></a>Средняя область, полоса прокрутки

Полоса прокрутки может быть больше, чем прокручивать код. Его также можно использовать для открытия другой панели редактора кода. Кроме того, можно использовать полосу прокрутки для более эффективного кодирования, добавляя к ней заметки или используя различные режимы отображения.

#### <a name="split-the-code-window"></a>Разделение окна кода

В полосе прокрутки редактора кода есть кнопка с **разделителем** в правом верхнем углу. При выборе можно открыть другую панель редактора кода. Это полезно, так как они работают независимо друг от друга, поэтому их можно использовать для работы с кодом в разных местах.

![Редактор кода XAML, только посрединная панель, в Visual Studio](media/code-editor-split-window-button.png "Снимок экрана редактора кода XAML, только средней панели, в Visual Studio 2019")

Дополнительные сведения о разделении окна редактора см. на странице " [Управление окнами редактора](../ide/how-to-manage-editor-windows.md) ".

#### <a name="use-annotations-or-map-mode"></a>Использование заметок или режима схемы

Можно также изменить вид полосы прокрутки и дополнительные функции, которые она содержит. Например, многие пользователи хотели бы включать *заметки* на полосу прокрутки, которые предоставляют визуальные подсказки, такие как изменения кода, точки останова, закладки, ошибки и позиции курсора.

Другие пользователи оценят использование *режима Map*, который отображает строки кода в миниатюре на полосе прокрутки. Разработчики, имеющие большой объем кода в файле, могут обнаружить, что режим отображения отслеживает несколько строк кода более эффективно, чем полоса прокрутки по умолчанию.

Дополнительные сведения об изменении параметров полосы прокрутки по умолчанию см. в разделе Настройка страницы полосы [прокрутки](../ide/how-to-track-your-code-by-customizing-the-scrollbar.md) .

## <a name="xaml-specific-features"></a>Функции, относящиеся к XAML

Большинство из приведенных ниже функций универсально доступно в интегрированной среде разработки Visual Studio, но к некоторым из них добавлены измерения, упрощающие написание кода для разработчиков XAML.

### <a name="xaml-code-snippets"></a>Фрагменты кода XAML

Фрагменты кода — это небольшие блоки повторно используемого кода, которые можно вставить в файл кода, щелкнув правой кнопкой мыши команду контекстного меню **Вставить фрагмент** или сочетание клавиш (**CTRL** + **K**, **CTRL** + **X**). Мы улучшили [IntelliSense](../ide/using-intellisense.md) , чтобы она поддерживала отображение фрагментов кода XAML, которые работают как с встроенными фрагментами, так и с пользовательскими фрагментами кода, добавляемыми вручную. Вот некоторые готовые фрагменты кода XAML: `#region` ,, `Column definition` `Row definition` , `Setter` и `Tag` .

![Редактор кода XAML с параметрами фрагментов кода XAML, отображаемыми в IntelliSense](media/xaml-code-snippets.png "Снимок экрана редактора кода XAML с параметрами фрагмента кода XAML, отображаемыми в IntelliSense")

Дополнительные сведения см. в разделе [фрагменты кода](../ide/code-snippets.md) и страницы [фрагментов кода C#](../ide/visual-csharp-code-snippets.md) .

### <a name="xaml-region-support"></a>Поддержка #region XAML

Начиная с Visual Studio 2015 мы сделали #region поддержку для разработчиков XAML в WPF и UWP и в последнее время в [Xamarin. Forms](/xamarin/xamarin-forms/user-interface/text/editor/). В Visual Studio 2019 мы продолжаем вносить добавочные улучшения в поддержку #region. Например, в [версии 16,4](/visualstudio/releases/2019/release-notes-v16.4/) и более поздних #region параметры отображаются при начале ввода `<!` .

![Редактор кода XAML с параметрами #region, отображаемыми в IntelliSense](media/code-editor-xaml-region.png "Снимок экрана редактора кода XAML с параметрами #region, отображаемыми в IntelliSense")

Регионы можно использовать, если требуется сгруппировать разделы кода, которые также нужно развернуть или свернуть.

```xaml
    <!--#region NameOfRegion-->
    Your code is here
    <!--#endregion-->
```

Дополнительные сведения о регионах см. на странице [#region (Справочник по C#)](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-region/) . Дополнительные сведения о развертывании и свертывании разделов кода см. на странице [структурирования](../ide/outlining.md) .

### <a name="xaml-comments"></a>Комментарии XAML

Разработчики часто предпочитают документировать свой код с помощью комментариев. Комментарии можно добавить в код XAML, который находится на вкладке **MainWindow. XAML** , следующими способами.

- Введите `<!--` перед комментарием и добавьте `-->` после комментария.
- Введите `<!` , а затем выберите `!--` в списке параметров.

  ![В редакторе кода XAML щелкните правой кнопкой мыши диалоговое окно "Добавление комментариев"](media/xaml-code-editor-comments.png "Снимок экрана: контекстное меню щелчка правой кнопкой мыши для добавления комментариев в редактор кода XAML")

- Выберите код, который необходимо заключить в комментарий, а затем нажмите кнопку **Комментарий** на панели инструментов в интегрированной среде разработки. Чтобы отменить действие, нажмите кнопку **раскомментировать** .

  ![Кнопка "комментарий" и кнопка "раскомментировать" на панели инструментов интегрированной среды разработки](media/comment-undo-comment-buttons.png "Снимок экрана: кнопка "комментарий" и кнопка "раскомментировать" на панели инструментов интегрированной среды разработки")

- Выберите код, который необходимо заключить в комментарий, а затем нажмите клавиши **CTRL** + **K**, **CTRL** + **C**. Чтобы раскомментировать выбранный код, нажмите клавиши **CTRL** + **K**, **CTRL** + **U**.

Дополнительные сведения об использовании комментариев в коде C#, который находится на вкладке **MainWindow.XAML.CS** , см. на странице [комментариев к документации](/dotnet/csharp/language-reference/language-specification/documentation-comments/) .

### <a name="xaml-lightbulbs"></a>Лампочки XAML

Значки лампочки, которые появляются в коде XAML, являются частью [быстрых действий](../ide/quick-actions.md) , которые можно использовать для рефакторинга, создания или изменения кода.

Вот несколько примеров того, как они могут выиграть при написании кода XAML:

- **Удалите ненужные пространства имен**. В редакторе кода XAML ненужные пространства имен отображаются в недоступном тексте. Если навести указатель мыши на ненужное использование, появится лампочка. Если в раскрывающемся списке выбран параметр **удалить ненужные пространства имен** , вы увидите предварительную версию, которую можно удалить.

  ![Параметр "удалить ненужные пространства имен" в редакторе кода XAML из лампочки быстрых действий](media/xaml-code-editor-dimmed-namespaces-preview.png "Снимок экрана: параметр "удалить ненужные пространства имен" редактора кода XAML, который отображается с помощью лампочки "быстрые действия"")

- **Переименуйте пространство имен**. Эта функция, доступная при щелчке правой кнопкой мыши в контекстном меню после выделения пространства имен, упрощает изменение нескольких экземпляров параметра одновременно. Вы также можете получить доступ к этой функции с помощью строки меню, **изменить**  >  **Рефакторинг**  >  **переименования**или нажав клавиши **CTRL** + **r**, а затем снова **CTRL** + **r** .

  ![Параметр переименования пространства имен в редакторе кода XAML из контекстного меню щелчка правой кнопкой мыши](media/code-editor-rename-namespace.png "Снимок экрана с параметром "переименовать пространство имен" редактора кода XAML, который отображается с помощью контекстного меню щелчка правой кнопкой мыши")

  Дополнительные сведения см. на странице [рефакторинга "Переименование символа кода](../ide/reference/rename.md) ".

### <a name="conditional-xaml-for-uwp"></a>Условный XAML для UWP

Условный код XAML обеспечивает возможность использовать метод [ApiInformation.IsApiContractPresent](/uwp/api/windows.foundation.metadata.apiinformation.isapicontractpresent/) в разметке XAML. Благодаря этому можно задавать свойства и создавать экземпляры объектов в разметке в зависимости от наличия API, а необходимость использования кода программной части отсутствует.

Дополнительные сведения см. на странице [Условный XAML](/windows/uwp/debug-test-perf/conditional-xaml/) -сервер и [элементы управления XAML UWP в классических приложениях (острова XAML)](/windows/apps/desktop/modernize/xaml-islands/) .

### <a name="xaml-structure-visualizer"></a>Визуализатор структуры XAML

Функция визуализатор структуры в редакторе кода показывает направляющие структуры, которые представляют собой вертикальные пунктирные линии, указывающие совпадающие открытые и закрытые элементы тега в коде. Эти вертикальные линии упрощают просмотр начала и окончания логических блоков.

Дополнительные сведения см. на странице [Навигация по коду](../ide/navigating-code.md) .

### <a name="intellicode-for-xaml"></a>Интелликоде для XAML

При добавлении тега XAML в код обычно начинается с левой угловой скобки `<` . При вводе этой угловой скобки появится меню Интелликоде, в котором перечислены некоторые из наиболее популярных тегов XAML. Выберите тот, который вы хотите быстро добавить в код.

Вы можете распознать настройки Интелликоде, так как они отображаются в верхней части списка и являются звездочками.

![Список Интелликоде для текстового редактора XAML](media/xaml-intellicode-selection.png "Снимок экрана со списком Интелликоде для текстового редактора XAML")

Дополнительные сведения см. в [обзоре страницы интелликоде](/visualstudio/intellicode/overview/) .

### <a name="settings"></a>Настройки

Дополнительные сведения о *всех* параметрах в интегрированной среде разработки Visual Studio см. в разделе [функции на странице редактора кода](../ide/writing-code-in-the-code-and-text-editor.md) .

## <a name="xaml-optional-settings"></a>Необязательные параметры XAML

С помощью диалогового окна [Параметры](../ide/reference/options-dialog-box-visual-studio.md) можно изменить параметры по умолчанию для редактора кода XAML. Чтобы просмотреть параметры, выберите **Сервис**  >  **Параметры**  >  **текстовый редактор**  >  **XAML**.

![Список параметров для текстового редактора XAML](media/xaml-tools-options.png "Снимок экрана: список параметров для текстового редактора XAML")

> [!NOTE]
> Для доступа к диалоговому окну «Параметры» можно также использовать сочетания клавиш. Вот как это можно делать: нажмите клавиши **CTRL** + **Q** для поиска в интегрированной среде разработки, введите **Параметры**и нажмите клавишу **Ввод**. Затем нажмите клавиши **CTRL** + **E** для поиска в диалоговом окне Параметры, введите **текстовый редактор**, нажмите клавишу **Ввод**, введите **XAML**и нажмите клавишу **Ввод**.
>  
> Дополнительные сведения о сочетаниях клавиш см. на странице с [советами по Visual Studio](../ide/productivity-shortcuts.md#code-editor) .

### <a name="universal-text-editor-options"></a>Параметры универсального текстового редактора

В диалоговом окне [Параметры](../ide/reference/options-text-editor-xaml-formatting.md) XAML следующие три первых элемента являются универсальными для всех языков программирования, поддерживаемых интегрированной средой разработки Visual Studio. Чтобы получить дополнительные сведения об этих параметрах и способах их использования, обратитесь к связанным сведениям в следующей таблице.

|Имя  |Дополнительные сведения  |
|---------|---------|
|Общие  | [Диалоговое окно "Параметры": текстовый редактор > все языки](../ide/reference/options-text-editor-all-languages.md) |
|Полосы прокрутки | [Диалоговое окно "Параметры", папка "Текстовый редактор", параметры "Все языки", "Полосы прокрутки"](../ide/reference/options-text-editor-all-languages-scroll-bars.md) |
|Вкладки  |  ["Параметры", "Текстовый редактор", "Все языки", "Вкладки"](../ide/reference/options-text-editor-all-languages-tabs.md) |

### <a name="xaml-specific-text-editor-options"></a>Параметры текстового редактора, специфичные для XAML

В следующей таблице перечислены параметры в диалоговом окне [Параметры](../ide/reference/options-text-editor-xaml-formatting.md) , которые могут улучшить возможности редактирования при разработке приложений на основе XAML. Чтобы узнать больше об этих параметрах и способах их использования, посетите связанные сведения.

|Имя  |Дополнительные сведения  |
|---------|---------|
|Форматирование | ["Параметры", "Текстовый редактор", XAML, "Форматирование"](../ide/reference/options-text-editor-xaml-formatting.md) |
|Прочее |  ["Параметры", "Текстовый редактор", XAML, "Прочее"](../ide/reference/options-text-editor-xaml-miscellaneous.md) |

> [!TIP]
> Параметр **имени метода обработчика событий «прописные буквы** » в разделе « **Разное** » особенно полезен для разработчиков XAML. Этот параметр *отключен* по умолчанию, так как он является новым, но мы рекомендуем установить его в значение *On* для поддержки правильного регистра в коде.

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения о том, как изменить код в режиме реального времени во время работы приложения, см. на странице " [горячая Загрузка XAML](xaml-hot-reload.md) ".

## <a name="see-also"></a>См. также

- [Функции редактора Visual Studio Code](../ide/writing-code-in-the-code-and-text-editor.md)
- [XAML в приложениях UWP](/windows/uwp/xaml-platform/xaml-overview/)
- [XAML в приложениях Xamarin.Forms](/xamarin/xamarin-forms/xaml/)
- [Разработка мобильных приложений Xamarin (Mac)](/visualstudio/mac/xamarin/)
- [Visual Studio 2019 для Mac — Обзор IDE (Mac)](/visualstudio/mac/ide-tour/)
