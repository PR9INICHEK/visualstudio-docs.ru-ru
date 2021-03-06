---
title: Разработка структуры решения моделирования
ms.date: 11/04/2016
ms.topic: how-to
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cc4eba7dc4d185cbd8eb4f1b073fce8b0c9fb07e
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85545045"
---
# <a name="structure-your-modeling-solution"></a>Разработка структуры решения моделирования

Для эффективного использования моделей в проекте разработки члены команды должны иметь возможность одновременной работы с моделями различных частей проекта. В этом разделе предлагается схема разделения приложения на различные части, соответствующие слоям в общей схеме слоев.

Чтобы быстро начать работу над проектом или подпроектом, полезно иметь шаблон проекта, соответствующий выбранной структуре проекта. В этом разделе описывается, как создать и использовать такой шаблон.

В этом разделе предполагается, что вы работаете над достаточно крупным проектом, для которого требуются несколько членов команды или даже, возможно, несколько команд. Код и модели проекта хранятся в системе управления версиями, такой как [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)]. По крайней мере некоторые члены команды используют Visual Studio для разработки моделей, а другие могут просматривать модели с помощью других версий Visual Studio.

Чтобы узнать, какие версии Visual Studio поддерживают все средства и функции моделирования, см. раздел [Поддержка версий для инструментов архитектуры и моделирования](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="solution-structure"></a>Структура решения

В среднем или крупном проекте структура команды соответствует структуре приложения. Каждая команда использует решение Visual Studio.

### <a name="to-divide-an-application-into-layers"></a>Разделение приложения на слои

1. Структура решений должна основываться на структуре приложения, например веб-приложения, приложения службы или классического приложения. Различные распространенные архитектуры обсуждаются в разделе [Application архетипов (рекомендации по архитектуре приложений Майкрософт](/previous-versions/msp-n-p/ee658107(v=pandp.10))).

2. Создайте решение Visual Studio, которое будет вызывать архитектурное решение. Это решение будет использоваться для создания общей структуры системы. Оно будет содержать только модели без кода.

   Добавьте схему зависимостей в это решение. На схеме зависимостей нарисуйте архитектуру, выбранную для приложения. Например, на схеме могут отображаться следующие слои и зависимости между ними: "Презентация", "Бизнес-логика" и "Данные".

4. Создайте отдельное решение Visual Studio для каждого слоя на схеме зависимостей архитектуры.

   Эти решения будут использоваться для разработки кода слоев.

5. Создание моделей, представляющих структуры слоев, и основные понятия, общие для всех слоев. Разместите модели таким образом, чтобы все модели были видны из решения "Архитектура", а с каждого слоя были видны соответствующие модели.

   Эту задачу можно выполнить, используя любую из описанных ниже процедур. В первом варианте для каждого слоя создается отдельный проект моделирования; во втором варианте создается один проект моделирования, совместно используемый в слоях.

#### <a name="use-a-separate-modeling-project-for-each-layer"></a>Использование отдельного проекта моделирования для каждого слоя

1. Создайте проект моделирования в каждом решении слоя.

   Эта модель будет содержать диаграммы, описывающие требования и структуру этого слоя. Он также может содержать схемы зависимостей, отображающие вложенные слои.

   Теперь имеются модели для каждого слоя и модель для архитектуры приложения. Каждая модель содержится в своем собственном решении. Это позволяет членам команды одновременно работать над слоями.

2. В решение "Архитектура" добавьте проект моделирования для каждого решения слоя. Для этого откройте решение "Архитектура". В **Обозреватель решений**щелкните правой кнопкой мыши узел решения, наведите указатель на пункт Добавить и выберите пункт **существующий проект**. Перейдите в проект моделирования (MODELPROJ) в решении для одного слоя.

   Каждая модель теперь видна в двух решениях: в своем "домашнем" решении и в решении "Архитектура".

3. В проект моделирования каждого слоя добавьте диаграмму зависимостей. Начните с копии схемы зависимостей архитектуры. Можно удалить части, не являющиеся зависимостями схемы зависимостей.

   Можно также добавить схемы зависимостей, представляющие подробную структуру этого слоя.

   Эти схемы используются для проверки кода, разрабатываемого в данном слое.

4. В решении "Архитектура" отредактируйте требования и модели структуры для всех слоев с помощью Visual Studio.

   В решении каждого слоя разработайте код для этого слоя в соответствии с моделью. Если вы планируете выполнять разработку без использования одного и того же компьютера для обновления модели, можно прочитать модель и разработать код, используя версии Visual Studio, в которых нельзя создавать модели. В этих версиях можно также создать код на основе модели.

   Этот метод гарантирует отсутствие взаимных помех, вызванных одновременным редактированием моделей слоев разными разработчиками.

   Однако использование отдельных моделей затрудняет ссылки на общие концепции. Каждая модель должна иметь собственную копию элементов, через которые она зависит от других слоев и архитектуры. Схема зависимостей на каждом слое должна синхронизироваться с диаграммой зависимостей архитектуры. Сложно поддерживать синхронизацию при изменении таких элементов, хотя для этой цели можно разработать специальные средства.

#### <a name="use-a-separate-package-for-each-layer"></a>Использовать отдельный пакет для каждого слоя

1. В решение для каждого слоя добавьте проект моделирования "Архитектура". В **Обозреватель решений**щелкните правой кнопкой мыши узел решения, наведите указатель на пункт **Добавить**и выберите пункт **существующий проект**. Теперь один проект моделирования доступен из каждого решения: из проекта "Архитектура" и из проекта разработки для каждого слоя.

2. В общей модели создайте пакет для каждого слоя: в **Обозреватель решений**выберите проект моделирования. В **обозревателе моделей UML**щелкните правой кнопкой мыши корневой узел модели, наведите указатель на пункт **Добавить**и выберите **пакет**.

   Каждый пакет будет содержать диаграммы, описывающие требования и структуру соответствующего слоя.

3. При необходимости добавьте локальные схемы зависимостей для внутренней структуры каждого слоя.

   Этот метод позволяет элементам структуры каждого слоя ссылаться напрямую на те слои и общую архитектуру, от которых они зависят.

   Хотя одновременная работа над различными пакетами может приводить к некоторым конфликтам, ими достаточно просто управлять, так как пакеты хранятся в отдельных файлах.

## <a name="create-architecture-templates"></a>Создание шаблонов архитектуры

На практике вы не создаете все решения Visual Studio одновременно, но добавляете их по мере выполнения проекта. Возможно, вы также используете ту же структуру решения в будущих проектах. Для упрощения быстрого создания новых решений можно создать шаблон решения или проекта. Шаблон можно перенаправить в расширение интеграции Visual Studio Integration Extension (VSIX), упрощающее распространение и установку на другие компьютеры.

Например, если часто используются решения со слоями "Представление", "Бизнес" и "Данные", можно настроить шаблон, который будет создавать решения с такой структурой.

### <a name="to-create-a-solution-template"></a>Создание шаблона решения

1. [Скачайте и установите мастер экспорта шаблонов](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.ExportTemplateWizard).

2. Создайте структуру решения, которую требуется использовать в качестве отправной точки для будущих проектов.

3. В меню **Файл** выберите команду **Export Template as VSIX**(Экспорт шаблона как VSIX).

   Откроется **Мастер экспорта шаблона как VSIX** .

4. Следуя инструкциям в мастере, выберите проекты, которые требуется включить в шаблон, укажите имя и описание шаблона, а также укажите расположение выходных файлов.

## <a name="watch-a-video"></a>Посмотрите видео

[Организация моделей и управление ими](https://channel9.msdn.com/blogs/clinted/uml-with-vs-2010-part-9-organizing-and-managing-your-models)

## <a name="see-also"></a>См. также

- [Использование моделей в процессе разработки](../modeling/use-models-in-your-development-process.md)
- [Руководство по средствам проектирования архитектуры Visual Studio](../modeling/visual-studio-architecture-tooling-guidance.md)
