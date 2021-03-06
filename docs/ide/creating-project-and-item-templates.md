---
title: Шаблоны для проектов и файлов
ms.date: 01/02/2018
ms.topic: conceptual
helpviewer_keywords:
- templates [Visual Studio], project
- templates [Visual Studio], item
- item templates [Visual Studio]
- project templates [Visual Studio]
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: 2cc932a2407aeb4951bab970a0edc6e2b2a5fcc9
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "79306911"
---
# <a name="project-and-item-templates"></a>Шаблоны проектов и элементов

Шаблоны проектов и элементов предоставляют многократно используемые заглушки, обеспечивающие пользователям определенный базовый код, и структуры, которые можно использовать в своих целях.

## <a name="visual-studio-templates"></a>шаблоны Visual Studio

При установке Visual Studio устанавливается ряд предопределенных шаблонов проектов и элементов. Эти шаблоны, такие как **Веб-приложение ASP.NET** и **Библиотека классов**, доступны для выбора при создании проекта. Шаблоны элементов, такие как файлы кода, XML-файлы, HTML-страницы и таблицы стилей, отображаются в диалоговом окне **Добавление нового элемента**.

Для пользователей эти шаблоны представляют собой отправную точку, с которой можно начать создание новых проектов или расширение текущих проектов. Шаблоны проектов предоставляют файлы, необходимые для конкретного типа проекта, включая стандартные ссылки на сборки, задают свойства проекта и параметры компилятора по умолчанию. По сложности шаблоны элементов могут варьироваться от одного пустого файла с определенным расширением до нескольких файлов исходного кода, которые содержат код заглушек, файлы сведений о конструкторе и внедренные ресурсы.

Вы можете использовать установленные шаблоны, создавать собственные шаблоны, а также скачивать и использовать шаблоны, созданные сообществом. Дополнительные сведения см. в статьях [Практическое руководство. Создание шаблонов проектов](../ide/how-to-create-project-templates.md) и [Практическое руководство. Создание шаблонов элементов](../ide/how-to-create-item-templates.md).

## <a name="contents-of-a-template"></a>Содержимое шаблона

Все шаблоны проектов и элементов, установленные с Visual Studio или созданные пользователем, работают на основе одних и тех же принципов и имеют схожее содержимое. Все шаблоны содержат следующие элементы:

- Файлы, создаваемые при использовании шаблона. Сюда входят файлы с исходным кодом, внедренные ресурсы, файлы проектов и т. д.

::: moniker range="vs-2017"

- Файл *VSTEMPLATE*, который содержит метаданные, необходимые для создания проекта или элемента из шаблона, а также для отображения шаблона в окнах **Новый проект** и **Добавление нового элемента**.

::: moniker-end

::: moniker range=">=vs-2019"

- Файл *VSTEMPLATE*, который содержит метаданные, необходимые для создания проекта или элемента из шаблона, а также для отображения шаблона на странице **Создание проекта** и в диалоговом окне **Добавление нового элемента**.

::: moniker-end

   Дополнительные сведения о *VSTEMPLATE*-файлах см. в статьях о [тегах шаблона](template-tags.md) и [параметрах шаблона](../ide/template-parameters.md).

Если эти файлы сжаты в *ZIP*-файл и помещены в соответствующую папку, Visual Studio автоматически отображает их в следующих расположениях:

::: moniker range="vs-2017"

- Шаблоны проектов отображаются в окне **Новый проект**.

::: moniker-end

::: moniker range=">=vs-2019"

- Шаблоны проектов отображаются на странице **Создание проекта**.

::: moniker-end

- Шаблоны элементов отображаются в окне **Добавление нового элемента**.

Дополнительные сведения о папках шаблонов см. в статье [Практическое руководство. Размещение и упорядочение шаблонов](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Создание шаблонов проектов](../ide/how-to-create-project-templates.md)
- [Практическое руководство. Создание шаблонов элементов](../ide/how-to-create-item-templates.md)
- [Теги шаблона](template-tags.md)
- [Параметры шаблона](../ide/template-parameters.md)
- [Настройка шаблонов](../ide/customizing-project-and-item-templates.md)
- [Пакеты NuGet в шаблонах Visual Studio](/nuget/visual-studio-extensibility/visual-studio-templates)
