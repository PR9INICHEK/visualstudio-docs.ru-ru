---
title: Практическое руководство. Тестирование и отладка визуализатора | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- visualizers, testing
- visualizers, debugging
- debugging [Visual Studio], visualizers
ms.assetid: 5cc12ce8-c819-48e4-b487-98d403001b28
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1a81a8d094999585620ab6ab412c3b0610caf517
ms.sourcegitcommit: c076fe12e459f0dbe2cd508e1294af14cb53119f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2020
ms.locfileid: "85348903"
---
# <a name="how-to-test-and-debug-a-visualizer"></a>Практическое руководство. тестирование и отладку визуализатора
После написания визуализатора необходимо выполнить отладку и протестировать его.

Одним из способов проверки визуализатора является установка его в Visual Studio и вызов из окна отладчика. (См. [Практическое руководство. Установка визуализатора](../debugger/how-to-install-a-visualizer.md).) При этом понадобится второй экземпляр Visual Studio для присоединения к визуализатору, запущенному на первом отладчике, и его отладки.

Более простой способ отладки визуализатора — запуск визуализатора из тестового драйвера. API визуализатора позволяет легко создать такой драйвер, который называется *узлом разработки визуализатора*.

### <a name="to-create-a-visualizer-development-host"></a>Чтобы создать узел разработки визуализатора

1. В класс отладчика следует включить статический метод, который создает объект <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerDevelopmentHost> и вызывает его метод показа.

    ```csharp
    public static void TestShowVisualizer(object objectToVisualize)
    {
        VisualizerDevelopmentHost myHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));
        myHost.ShowVisualizer();
    }
    ```

    Параметры, используемые для создания узлов, это объект данных, который будет показан в визуализаторе (`objectToVisualize`) и тип класса отладчика.

2. Добавьте следующий оператор для вызова `TestShowVisualizer`. Если визуализатор был создан в библиотеке классов, необходимо создать исполняемый файл для вызова библиотеки классов и поместить в него этот оператор:

    ```csharp
    DebuggerSide.TestShowVisualizer(myString);
    ```

    Более полный пример см. в разделе [Практическое руководство. Написание визуализатора на C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md).

## <a name="see-also"></a>См. также
- [Пошаговое руководство: Написание визуализатора на C#](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)
- [Практическое руководство. Установка визуализатора](../debugger/how-to-install-a-visualizer.md)
- [Создание настраиваемых визуализаторов](../debugger/create-custom-visualizers-of-data.md)
