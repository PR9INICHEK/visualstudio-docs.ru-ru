---
title: Свойства соединителей
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, connectors
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a7bf5492d7da845b65904959cb57737fd438c28b
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85532279"
---
# <a name="properties-of-connectors"></a>Свойства соединителей
Соединители представляют доменные отношения в созданном конструкторе.

 Дополнительные сведения см. [в разделе Определение доменного языка](../modeling/how-to-define-a-domain-specific-language.md). Дополнительные сведения об использовании этих свойств см. [в разделе Настройка и расширение предметно-](../modeling/customizing-and-extending-a-domain-specific-language.md)ориентированного языка.

 У соединителей есть свойства, перечисленные в следующей таблице.

|Свойство.|Описание|По умолчанию|
|-|-|-|
|Цвет|Цвет данного соединителя.|Черный|
|Тип штриха|Стиль штриха для линии этого соединителя ("Сплошная", "тире", "точка", "Дашдот", "Дашдотдот" или "Настраиваемая").|Сплошная|
|Конечный стиль источника|Конечный стиль источника для этого соединителя (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond или None).|Отсутствуют|
|Конечный конечный стиль|Целевой конечный стиль для этого соединителя (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond или None).|Отсутствуют|
|Цвет текста|Цвет, используемый для декораторов текста, связанных с этим соединителем.|Черный|
|Thickness|Толщина линии для данного соединителя, измеренная в дюймах.|0,03125|
|Модификатор доступа|Уровень доступа класса ( `public` или `internal` ).|Общедоступные|
|Настраиваемые атрибуты|Используется для добавления атрибутов в класс исходного кода, созданного из этого соединителя.|\<none>|
|Создает двойное производное|При `True` этом создается как базовый класс, так и разделяемый класс (для поддержки настройки с помощью переопределений). Дополнительные сведения см. [в разделе Переопределение и расширение созданных классов](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Имеет настраиваемый конструктор|Если `True` задано значение, в исходном коде будет указан пользовательский конструктор. Дополнительные сведения см. [в разделе Переопределение и расширение созданных классов](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Модификатор наследования|Описывает тип наследования класса исходного кода, созданного из соединителя ( `none` `abstract` или `sealed` ).|нет|
|Базовый соединитель|Базовый класс этого соединителя.|(нет)|
|name|Имя этого соединителя.|Текущее имя|
|Пространство имен|Пространство имен, связанное с этим соединителем.|Текущее пространство имен|
|Тип подсказки|Как определена подсказка (фиксированная, переменная или нет). Если параметр является фиксированным, то в `Fixed Tooltip Text` качестве подсказки используется значение свойства. Если переменная, то подсказка определена в пользовательском коде.|\<none>|
|Примечания|Неформальные примечания, связанные с этим соединителем.|\<none>|
|Стиль маршрутизации|Стиль, используемый для маршрутизации соединителя. `Rectilinear`При необходимости соединитель поворачивается в правый угол, а `Straight` соединитель — нет.|Rectilinear|
|Представленный цвет как свойство<br /><br /> Предоставленный стиль штриха как свойство<br /><br /> Доступная толщина как свойство<br /><br /> Отображение цвета текста|Если значение `True` равно, пользователь может задать указанное свойство фигуры. Чтобы установить это, щелкните правой кнопкой мыши определение фигуры и выберите пункт **добавить предоставленный**.|False|
|Описание|Используется для документирования созданного конструктора.|\<none>|
|Отображаемое имя|Имя, которое будет отображаться в созданном конструкторе для этого соединителя.|\<none>|
|Исправлен текст подсказки|Текст, используемый для фиксированной подсказки.|\<none>|
|Ключевое слово Help|Ключевое слово, используемое для индексации справки F1 для этого элемента.|\<none>|

## <a name="see-also"></a>См. также

- [Глоссарий средств предметно-ориентированных языков](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)