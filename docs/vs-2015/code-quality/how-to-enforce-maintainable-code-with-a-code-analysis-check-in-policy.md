---
title: 'Практическое: обеспечение простоты поддержки кода с политику возврата с анализом кода | Документация Майкрософт'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- code analysis, check-in policies
ms.assetid: d1b3b04f-4dd9-40e6-b2d4-b414d33fb647
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 97b321fe5a72c6f3ace680476340eca48f7ed309
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47570252"
---
# <a name="how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy"></a>Практическое руководство. Обеспечение простоты поддержки кода с помощью политики возврата с анализом кода
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [как: принудительное применение поддерживаемого кода с политикой анализа кода возврата](https://docs.microsoft.com/visualstudio/code-quality/how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy).  
  
Разработчики могут использовать средство метрики кода для измерения сложности и удобства поддержки кода, но они не могут вызывать метрики кода как часть политики возврата. Тем не менее команда может включить правила анализа кода, проверка соответствия кода стандартам метрик кода и принудительное применение правил с помощью политик возврата. Дополнительные сведения о метриках кода см. в разделе [значения метрик кода](../code-quality/code-metrics-values.md).  
  
 Разработчики могут включить глубина наследования, Связанность классов, индекс удобства поддержки и сложность правил для обеспечения простоты поддержки кода с помощью политик возврата анализа кода. Все четыре этих правил можно найти в категории «Правила удобства поддержки» в редактор политики анализа кода.  
  
 Администраторы системы управления версиями для [!INCLUDE[esprfound](../includes/esprfound-md.md)] можно добавить правила удобства поддержки кода анализа требования политик возврата. Возврата политиками разработчиков запустить анализ кода на основе этих правил изменений перед запуском процесса возврата.  
  
### <a name="to-open-the-code-analysis-policy-editor"></a>Чтобы открыть редактор политики анализа кода  
  
1.  В **Team Explorer**, щелкните правой кнопкой мыши командный проект, нажмите кнопку **параметры командного проекта**, а затем нажмите кнопку **системы управления версиями**.  
  
     **Системы управления версиями** откроется диалоговое окно.  
  
2.  На **политики возврата** , а щелкните **добавить**.  
  
     **Добавления политики возврата** откроется диалоговое окно.  
  
3.  В **политики возврата** выберите **анализа кода** флажок и нажмите кнопку **ОК**.  
  
     **Редактор политики анализа кода** откроется диалоговое окно.  
  
### <a name="to-enable-code-analysis-maintainability-rules"></a>Чтобы включить правила удобства поддержки анализа кода  
  
1.  В **редактор политики анализа кода** диалогового **параметры правил**, разверните **правила удобства поддержки** узла.  
  
2.  Установите флажки для перечисленных ниже правил:  
  
    -   Глубина наследования: **CA1501 AvoidExcessiveInheritance** -пороговое значение: предупреждение в более чем 5 уровней вложенности  
  
    -   Сложность: **CA1502 AvoidExcessiveComplexity** -пороговое значение: предупреждение в более чем 25  
  
    -   Индекс удобства поддержки: **CA1505 под названием AvoidUnmaintainableCode** -пороговое значение: предупреждение в менее 20  
  
    -   Взаимозависимости классов: **CA1506 AvoidExcessiveClassCoupling** -пороговое значение: предупреждение при более чем 80 для класса и более чем 30 для метода  
  
    -   Кроме того, если требуется запретить построение при нарушении правила, выберите **обрабатывать предупреждения как ошибки** флажок рядом с описанием правила.  
  
3.  Нажмите кнопку **ОК**. Новая политика возврата теперь применяется для будущих возвратов.  
  
## <a name="see-also"></a>См. также  
 [Значения метрик кода](../code-quality/code-metrics-values.md)   
 [Создание и использование политик возврата с анализом кода](../code-quality/creating-and-using-code-analysis-check-in-policies.md)


