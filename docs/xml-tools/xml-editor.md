---
title: Редактор XML
ms.date: 11/04/2016
ms.topic: overview
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 64f36255a03939c649a91b4a91d15958475be3b5
ms.sourcegitcommit: ca777040ca372014b9af5e188d9b60bf56e3e36f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85815023"
---
# <a name="xml-editor"></a>Редактор XML

Редактор XML в Visual Studio построен на основе текстового редактора и включает дополнительную поддержку языков на базе XML. Если открыть XML-файл в Visual Studio, он откроется в редакторе XML.

Редактор XML включает следующие возможности.

- Проверка синтаксиса XML 1.0.

- Проверка правильности по схеме во время ввода.

- Поддержка XML-фрагментов, включая фрагменты, сформированные схемой.

- Поддержка определения типа документа (DTD).

- Поддержка схем на языке XSD.

- Создание схемы XML из экземпляра XML-документа.

- Преобразование определения DTD или XDR-схемы в XML-схему.

- Проверка синтаксиса XSLT.

- Структурирование документов, позволяющее разворачивать и сворачивать элементы.

- Интеграция с [обозревателем XML-схем](../xml-tools/xml-schema-explorer.md). Обеспечивает иерархическое представление XML-схем.

Редактор XML вызывается для распространенных расширений файлов, таких как *XML*, *XSD*, *XSL* и *CONFIG*. Также это приложение вызывается для неизвестных расширений имен файлов, если есть основания полагать, что файл содержит код XML.

## <a name="xslt-intellisense"></a>XSLT IntelliSense

Функция [XSLT IntelliSense](../xml-tools/xml-editor-intellisense-features.md) позволяет автоматически заполнять имена наборов атрибутов; режимы шаблонов и имена; а также имена параметров для указанного режима или именованного шаблона.

## <a name="xslt-profiler"></a>Профилировщик XSLT

[Профилировщик XSLT](../xml-tools/xslt-profiler.md) создает подробные отчеты о производительности XSLT, помогающие измерять, оценивать и выявлять проблемы в XSLT-коде, связанные с производительностью. Профилировщик XSLT также содержит полезные подсказки по оптимизации таблиц стилей XSL и XSLT.

## <a name="xslt-hierarchy"></a>Иерархия XSLT

[Средство управления иерархией XSLT](../xml-tools/walkthrough-using-xslt-hierarchy.md) позволяет добавлять точки останова во включенные таблицы стилей и/или встроенные правила шаблона.

## <a name="see-also"></a>См. также

- [Параметры редактора XML — форматирование](../ide/reference/options-text-editor-xml-formatting.md)
- [Параметры редактора HTML — прочее](../ide/reference/options-text-editor-xml-miscellaneous.md)
- [Возможности редактора кода](../ide/writing-code-in-the-code-and-text-editor.md)
- [Справочник по XML-стандартам](https://msdn.microsoft.com/79c78508-c9d0-423a-a00f-672e855de401)
- [Средства XML в Visual Studio](../xml-tools/xml-tools-in-visual-studio.md)
