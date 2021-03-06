---
title: Свойства фигур изображений
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.selectimagedialog
- vs.dsltools.dsldesigner.imageshape
helpviewer_keywords:
- Domain-Specific Language, image shape
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 13a9fc3c2d9c7f3f30f035eed036d2a9fb63d667
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85520853"
---
# <a name="properties-of-image-shapes"></a>Свойства фигур изображений

Для указания способа отображения классов домена в созданном конструкторе можно использовать фигуры изображений. Определите фигуру изображения, задав `Image` свойству класса предопределенный файл изображения. Поддерживаются следующие форматы:

- .gif

- .jpg

- JPEG

- BMP

- . WMF

- .emf

- .png

По умолчанию файлы ресурсов конструктора, такие как файлы изображений, находятся в папке **Resources** в проекте **DSL** .

Дополнительные сведения см. [в разделе Определение доменного языка](../modeling/how-to-define-a-domain-specific-language.md). Дополнительные сведения об использовании этих свойств см. [в разделе Настройка и расширение предметно-](../modeling/customizing-and-extending-a-domain-specific-language.md)ориентированного языка.

Формы изображений имеют свойства, перечисленные в следующей таблице.

|Свойство.|Описание|По умолчанию|
|-|-|-|
|Цвет заливки|Цвет заливки этой фигуры.|White|
|Режим градиента заливки|Режим градиента заливки этой фигуры.|Горизонтальное масштабирование|
|Имеет точки соединения по умолчанию|Если `True` значение равно, то в созданном конструкторе фигура будет использовать верхнюю, нижнюю, левую и правую точки соединения.|False|
|Цвет контура|Цвет контура этой фигуры.|Черный|
|Стиль штриха в контуре|Стиль штриха контура этой фигуры (сплошная, Штрихпунктирная, точка, Дашдот, Дашдотдот или пользовательская).|Сплошная|
|Толщина контура|Толщина контура этой фигуры.|0,03125|
|Цвет текста|Цвет, используемый для декораторов текста, связанных с этой фигурой.|Черный|
|Модификатор доступа|Модификатор доступа геометрической фигуры (открытый или внутренний).|Общедоступные|
|Настраиваемые атрибуты|Используется для добавления атрибутов в класс исходного кода, созданного из этой фигуры.|\<none>|
|Создает двойное производное|При `True` этом создается как базовый класс, так и разделяемый класс (для поддержки настройки с помощью переопределений). Дополнительные сведения см. [в разделе Переопределение и расширение созданных классов](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Имеет настраиваемый конструктор|Если `True` задано значение, в исходном коде будет указан пользовательский конструктор. Дополнительные сведения см. [в разделе Переопределение и расширение созданных классов](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Модификатор наследования|Описывает тип наследования класса исходного кода, созданного из фигуры изображения ( `none` `abstract` или `sealed` ).|нет|
|Базовая фигура изображения|Базовый класс этой фигуры.|(нет)|
|name|Имя этой фигуры.|Текущее имя|
|Пространство имен|Пространство имен, связанное с этой фигурой.|Текущее пространство имен|
|Тип подсказки|Место, где определена подсказка (фиксированная, переменная или нет). Если параметр является фиксированным, то в `Fixed Tooltip Text` качестве подсказки используется значение свойства. Если переменная, то подсказка определена в пользовательском коде.|нет|
|Примечания|Неформальные примечания, связанные с этой фигурой.|\<none>|
|Начальная высота|Начальная высота этой фигуры в дюймах.|1|
|Начальная ширина|Начальная ширина этой фигуры в дюймах.|1.5|
|Предоставленный цвет заливки как свойство<br /><br /> Предоставленный режим градиента заливки<br /><br /> Раскрытие цвета контура как свойства<br /><br /> Раскрытие стиля штриха в качестве свойства<br /><br /> Доступная толщина контура в качестве свойства<br /><br /> Отображение цвета текста|Если значение `True` равно, пользователь может задать указанное свойство фигуры. Чтобы установить это, щелкните правой кнопкой мыши определение фигуры и выберите пункт **добавить предоставленный**.|False|
|Описание|Используется для документирования созданного конструктора.|\<none>|
|Отображаемое имя|Имя, которое будет отображаться в созданном конструкторе для этой фигуры.|\<none>|
|Исправлен текст подсказки|Текст, используемый для фиксированной подсказки.|\<none>|
|Ключевое слово Help|Ключевое слово, используемое для индексации справки F1 для этого элемента.|\<none>|
|Образ —|Путь к файлу изображения, используемому для этой фигуры.|\<none>|

## <a name="see-also"></a>См. также

- [Глоссарий средств предметно-ориентированных языков](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)