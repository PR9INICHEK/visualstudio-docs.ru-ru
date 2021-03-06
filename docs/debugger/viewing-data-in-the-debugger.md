---
title: Создание пользовательских представлений данных в отладчике | Документация Майкрософт
ms.date: 01/09/2019
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], inspecting programs
- debugger, viewing data
ms.assetid: 13e1105f-f987-402e-9108-ec6ac12be042
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 63dc11736e92013719fcda2bae0ba9599a8835aa
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72569000"
---
# <a name="create-custom-views-of-data-in-the-visual-studio-debugger-c-visual-basic-c"></a>Создание пользовательских представлений данных в отладчике Visual Studio (C#, Visual Basic, C++)

В отладчике [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] предусмотрено множество средств для проверки и изменения состояния программы. Большинство этих средств функционируют только в режиме приостановки.

## <a name="create-custom-views-of-data-in-variable-windows-and-datatips"></a>Создание пользовательских представлений данных в окнах переменных и подсказках DataTip

 Многие [окна отладчика](../debugger/debugger-windows.md), например **Видимые** и **Контрольное значение**, позволяют проверять переменные. Вы можете настроить отображение типов C++, управляемых объектов и собственных типов в окнах переменных отладчика и в подсказках [DataTip](../debugger/view-data-values-in-data-tips-in-the-code-editor.md). Дополнительные сведения см. в статьях [Создание пользовательских представлений для объектов C++](../debugger/create-custom-views-of-native-objects.md) и [Создание настраиваемых представлений управляемых объектов](../debugger/create-custom-views-of-managed-objects.md).

## <a name="create-custom-visualizers"></a>Создание настраиваемых визуализаторов

 Визуализаторы позволяют просмотреть содержимое объекта или переменной более удобным способом. В отладчике Visual Studio визуализатор ссылается на различные окна, которые можно открыть с помощью значка лупы ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Значок визуализатора"). Например, в HTML-визуализаторе HTML-строка отображается в том виде, в каком она была бы показана в браузере. Доступ к визуализаторам можно получить из подсказок DataTip либо окон **Контрольное значение**, **Видимые** или **Локальные**. Визуализаторы также можно открыть из диалогового окна **Быстрая проверка**. Дополнительные сведения см. в статье [Создание настраиваемых визуализаторов](../debugger/create-custom-visualizers-of-data.md).

## <a name="see-also"></a>См. также

- [Первое знакомство с отладчиком](../debugger/debugger-feature-tour.md)
- [Командное окно](../ide/reference/command-window.md)
- [Безопасность отладчика](../debugger/debugger-security.md)
