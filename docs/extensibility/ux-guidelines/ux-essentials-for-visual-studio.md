---
title: UX Основы для визуальной студии (ru) Документы Майкрософт
ms.date: 04/26/2017
ms.topic: conceptual
ms.assetid: a793cf7a-f230-43ce-88d0-fa5d6f1aa9c7
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c6c329eda477d77ab73be2ad913ac18d67ff3c08
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "80698331"
---
# <a name="ux-essentials-for-visual-studio"></a>Основы UX для Visual Studio

## <a name="best-practices"></a>Рекомендации

### <a name="1-be-consistent-within-the-visual-studio-environment"></a>1. Будьте последовательны в среде Visual Studio.

- Следуйте существующим [шаблонам взаимодействия](interaction-patterns-for-visual-studio.md) в оболочке.

- Особенности дизайна должны соответствовать требованиям оболочки к визуальному языку и [мастерству.](evaluation-tools-for-visual-studio.md)

- Используйте общие команды и элементы управления, когда они существуют.

- Понимание иерархии Visual Studio и того, как она устанавливает контекст и управляет uI.

### <a name="2-use-the-environment-service-for-fonts-and-colors"></a>2. Используйте службу окружающей среды для шрифтов и цветов.

- Пользовательский уифи-узло должно соблюдать текущую настройку [шрифта среды,](fonts-and-formatting-for-visual-studio.md) если он не подвергается настройке на странице шрифтов и цветов в диалоге опционов.

- Элементы uI должны использовать [службу VSColor,](colors-and-styling-for-visual-studio.md)используя общие маркеры среды или маркеры, специфичные для конкретных функций.

### <a name="3-make-all-imagery-consistent-with-the-new-vs-style"></a>3. Сделать все изображения в соответствии с новым стилем VS.

- Следуйте принципам дизайна Visual Studio для иконок, глифов и другой графики.

- Не размещайте текст в графических элементах.

### <a name="4-design-from-a-user-centric-perspective"></a>4. Дизайн с точки зрения, ориентированной на пользователя.

- Создайте поток задач перед отдельными объектами внутри него.

- Будьте знакомы с пользователями и сделать эти знания явным в вашей спецификации.

- При просмотре uI оцените полный опыт, а также детали.

- Дизайн вашего uI так, чтобы он оставался функциональным и привлекательным, независимо от языка или языка.

## <a name="screen-resolution"></a>Разрешение экрана

### <a name="minimum-resolution"></a>Минимальное разрешение

- Минимальное разрешение для Visual Studio 2015 **1280x720**. Это означает, что visual Studio *можно* использовать в этом разрешении, хотя это может быть не оптимальным пользовательским интерфейсом. Нет никакой гарантии, что все аспекты будут пригодны для узла при разрешении ниже 1280x720.

- Целевое разрешение для Visual Studio **1366x768**. Это самое низкое разрешение, при котором мы обещаем *хороший* пользовательский опыт.

- Первоначальная высота диалога должна быть **меньше 700 пикселей,** поэтому она вписывается в минимальное разрешение кадра IDE на уровне 96 dpi.

### <a name="high-density-displays"></a>Дисплеи высокой плотности
 UI в Visual Studio должен хорошо работать во всех факторах масштабирования DPI, которые Windows поддерживает из коробки: 150%, 200 и 250%.

## <a name="anti-patterns"></a>Антишаблоны
 Visual Studio содержит множество примеров uI, которые следуют нашим рекомендациям и передовым практикам. Стремясь быть последовательными, разработчики часто заимствуют из шаблонов проектирования uI продукта, аналогичные тем, которые они строят. Хотя это хороший подход, который помогает нам управлять согласованности в пользовательском взаимодействии и визуальном дизайне, мы иногда корабль особенности с несколькими деталями, которые не отвечают нашим руководящим принципам из-за ограничения графика или дефект приоритетов. В этих случаях мы не хотим, чтобы команды копировали один из этих «антишаблонов», потому что они распространяются плохо или несовместимы с использованием ума в среде Visual Studio.

### <a name="required-fieldssettings-shown-in-error-state-by-default"></a>Требуемые поля/параметры, отображаемые в состоянии ошибки по умолчанию

#### <a name="feature-team-goals"></a>Цели команды характеристики

- Предупредите пользователей о том, что они добавили элемент, который должен быть настроен.

- Обращайте внимание пользователя на области, которые нуждаются в входе.

#### <a name="anti-pattern-solution"></a>Решение для борьбы с шаблонами
 Как только пользователь инициировал действие и прежде чем он выполнил задачу, немедленно поместите значки критической остановки рядом с областями, которые нуждаются в конфигурации.

#### <a name="example-manifest-designer-declarations"></a>Пример: Манифест дизайнер деклараций
 Добавление декларации в список немедленно помещает его в состояние ошибки, которое сохраняется до тех пор, пока пользователь не закажет требуемые свойства.

 В этом случае возникает дополнительная проблема, поскольку значок, используемый для оповещения, содержит «значок»&times;« так что общий значок удаления не может быть использован рядом с ним. В результате, uI использует кнопку Удалить, более неуклюжим управления.

 ![Размещение uI в состоянии ошибки по умолчанию является антишаблоном Visual Studio.](../../extensibility/ux-guidelines/media/manifestdesignererrordeclarationsanti-pattern.png "МанифестДизайнерошибкадексанти-паттерн")<br />Размещение uI в состоянии ошибки по умолчанию является антишаблоном Visual Studio.

#### <a name="alternatives"></a>Альтернативные варианты

Лучшим решением этой проблемы является:

- Разрешить пользователю добавить декларацию без предупреждения, а затем немедленно переместить, чтобы установить свойства на элементе.

- Добавьте значок предупреждения (золотой треугольник) при переходе фокуса от элемента, например, чтобы добавить еще одну декларацию в список или попытаться изменить вкладки внутри конструктора.

- Если пользователь пытается изменить вкладки перед установкой свойств в любых декларациях, разочавайте диалог, объясняя, что приложение не будет создавать (или какие бы последствия) не были устранены. Если пользователь отвергает диалог и в любом случае изменяет вкладки, то значок (критический или предупредительный, по мере необходимости) добавляется во вкладку Декларации.

### <a name="multiple-clicks-to-dismiss-ui"></a>Несколько кликов, чтобы уволить UI

#### <a name="feature-team-goals"></a>Цели команды характеристики
 Не позволяйте пользователю отклонить пользовательский интерфейс, не увидев при этом текста объяснения.

#### <a name="anti-pattern"></a>Антишаблон
 Команда, вставляющая видеоссылки в различные места в рамках&times;VS UI, решила против общей схемы «закрытия кнопок и инструментария, как указано в UX, и вместо этого реализовала ссылку drop-down и «Don't show again».

#### <a name="example-video-links-in-team-explorer"></a>Пример: Видеоссылки в Team Explorer
Принуждение пользователя читать пояснительный текст перед увольнением пользовательского интерфейса является антишаблоном в Visual Studio. Правильно разработанные, видеоссылки должны отображать инструмент с дополнительной информацией&times;о нависнуть, и нажав на " должны уволить сообщение без необходимости дальнейшего взаимодействия.

 ![Пояснительный текст анти&#45;шаблон &#45; неверным](../../extensibility/ux-guidelines/media/incorrectuseofmultipleclicks.png "Incorrectuseofmultipleclicks")<br />Неправильный шаблон видеосвязи

Вместо простой кнопки закрытия (одним щелчком мыши), пользователь вынужден использовать два клика, чтобы просто уволить пользовательский интерфейс в каждом месте, где появляются видеоссылки.

Правильный дизайн для этой ситуации заключается в том, чтобы следовать шаблону, обычному для Internet Explorer, Office и Visual Studio: на нависнуть пользователь может увидеть описание инструментария и одним щелчком мыши скрывает пользовательский интерфейс.

 ![Пояснительный текст анти&#45;шаблон &#45; правильным](../../extensibility/ux-guidelines/media/explanatorytextanti-pattern-correct.png "Пояснительноетекстанти-шаблон-правильное")<br />Правильный шаблон видеосвязи

### <a name="using-command-bars-for-settings"></a>Использование командных баров для настроек

**Рисунок А** представляет этот антишаблон: поместить настройку под кнопку команды, которая применяется не только к команде. В этом эскизе, Есть команды, кроме Start Debugging - как просмотр в браузере, начать без отладки, и шаг в - что будет уважать выбранную настройку.

![Рисунок A: Команда бар анти-шаблон](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figurea.png "Commandbaranti-шаблон-FigureA")<br />Рисунок A: Команда бар анти-шаблон

Немного лучше, но все еще нежелательно, ставит настройки этого типа в панели инструментов, как показано на **рисунке B**. В то время как раздельные кнопки занимают меньше места и, следовательно, улучшение по сравнению с падением падения, оба проекта по-прежнему используют панель инструментов для продвижения то, что на самом деле не команда.

![Рисунок B: Лучше, но все же команда бар анти-шаблон](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figureb.png "Commandbaranti-шаблон-РисунокB")<br />Рисунок B: Лучше, но все же команда бар анти-шаблон

При правильном подходе, показанном на **рисунке C,** параметр привязан к серии команд. Глобальная настройка не устанавливается, и мы просто переключаемся между четырьмя командами. Это единственная ситуация, в которой команды в панели инструментов являются приемлемыми.

![Рисунок C: Правильное использование шаблона панели команд Visual Studio](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figurec.png "Commandbaranti-шаблон-Рисунок")<br />Рисунок C: Правильное использование шаблона панели команд Visual Studio

### <a name="control-anti-patterns"></a>Контроль антишаблонов
 Некоторые антишаблоны просто неправильное использование или представление управления или группы элементов управления.

#### <a name="underlining-used-as-a-group-label-not-a-hyperlink"></a>Подчеркивание, используемое в качестве группового ярлыка, а не гиперссылки
 Подчеркивая текст следует использовать только для гиперссылок.

 **Плохо:**\
 ![Подчеркнутый текст, который не является гиперссылкой, является антишаблоном Visual Studio.](../../extensibility/ux-guidelines/media/0102-g_grouplabelincorrect.png "0102-g_GroupLabelIncorrect")<br />Подчеркнутый текст, который не является гиперссылкой, является антишаблоном Visual Studio.

 **Хорошо:**\
 ![Стилизованный правильно, текст без гиперссылки отображается без украшений в шрифте среды.](../../extensibility/ux-guidelines/media/0102-h_grouplabelcorrect.png "0102-h_GroupLabelCorrect")<br />Стилизованный правильно, текст без гиперссылки отображается без украшений в шрифте среды.

#### <a name="clicking-on-a-check-box-results-in-a-pop-up-dialog"></a>Нажав на флажок приводит к всплывающем диалогу
 Нажав на флажок "Включить удаленный рабочий стол для всех ролей" в мастере "Опубликовать приложение Windows Azure" сразу же приводит сяпкие диалог, антишаблон Visual Studio. Кроме того, поле флажка не заполняется флажкой после выбранного, другого взаимодействия антишаблона.

 ![Воспитание диалога после нажатия флажка является противоупометкой Visual Studio.](../../extensibility/ux-guidelines/media/0102-i_checkboxpopup.png "0102-i_CheckboxPopup")<br />Воспитание диалога после нажатия флажка является противоупометкой Visual Studio.

### <a name="hyperlink-anti-patterns"></a>Антишаблоны гиперссылки
 Следующий пример содержит два антишаблона:

1. Передний план, поворачивая красный на нависать означает, что правильный общий цвет из службы шрифта не используется.

2. "Узнать больше" не является подходящим текстом для ссылки на концептуальную тему. Цель пользователя не узнать больше, это понять последствия их выбора.

   ![Игнорирование цветовой службы и использование "Узнать больше" для гиперссылок являются Visual Studio анти-шаблоны.](../../extensibility/ux-guidelines/media/0102-j_hyperlinkincorrect.png "0102-j_HyperlinkIncorrect")<br />Игнорирование цветовой службы и использование "Узнать больше" для гиперссылок являются Visual Studio анти-шаблоны.

**Лучшее решение:** Задайте вопрос, который пользователь будет задавать, нажав на ссылку. Пример:

- Как работают службы Windows Azure?

- Когда мне нужен проект мобильных служб Windows Azure?

#### <a name="using-click-here-for-links"></a>Использование "Нажмите здесь" для ссылок
 Гиперссылки должны быть самоописательными. Это анти-шаблон для использования "Нажмите здесь" или любой аналогичный вариант.

 **Плохо:** "Нажмите здесь для получения инструкций о том, как создать новый проект".

 **Хорошо:** «Как создать новый проект?»
