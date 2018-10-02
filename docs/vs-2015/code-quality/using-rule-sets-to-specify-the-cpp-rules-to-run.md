---
title: Использование наборов правил для задания выполняемых правил C++ | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3877e6-5349-4c03-9541-3d5be259f1e8
caps.latest.revision: 7
author: corob-msft
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9466bf421ca5844d3d7083528fb1a27e3c488937
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47559108"
---
# <a name="using-rule-sets-to-specify-the-c-rules-to-run"></a>Использование наборов правил для задания выполняемых правил C++
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [использование наборов правил для задания выполняемых правил C++](https://docs.microsoft.com/visualstudio/code-quality/using-rule-sets-to-specify-the-cpp-rules-to-run).  
  
В [!INCLUDE[vsPreShort](../includes/vspreshort-md.md)] и [!INCLUDE[vsUltShort](../includes/vsultshort-md.md)], можно создавать и изменять пользовательский *набор правил* в соответствии с потребностями конкретного проекта, связанные с анализом кода. Создание набора настраиваемых правил C++, C/C++ проект должен быть открыт в Интегрированной среде разработки Visual Studio. В редакторе набора правил откройте набор стандартных правил и затем добавить или удалить определенные правила и при необходимости изменить действие, которое происходит, когда анализа кода определяет, нарушено правило.  
  
 Чтобы создать новое настраиваемое правило набор, сохраните его с помощью имени файла. Настраиваемый набор правил, автоматически назначается в проект.  
  
## <a name="opening-the-rule-set-editor"></a>Открытие правило установить редактора  
  
#### <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>Чтобы создать настраиваемое правило из одного существующего набора правил  
  
1.  В обозревателе решений откройте контекстное меню для проекта и выберите **свойства**.  
  
2.  На **свойства** вкладке, выберите **анализа кода**.  
  
3.  В **набора правил** стрелку раскрывающегося списка, выполните одно из следующих:  
  
    -   Выберите набор правил, который требуется настроить.  
  
     \- или -  
  
    -   Выберите  **\<Обзор... >** чтобы указать существующий настраиваемый набор правил, если его нет в списке.  
  
4.  Выберите **откройте** для отображения правила в редакторе набора правил.  
  
#### <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>Чтобы изменить правило, задать в редакторе набора правил  
  
-   Чтобы изменить отображаемое имя набора правил в **представление** меню, выберите **окно "Свойства"**. Введите отображаемое имя в **имя** поле. Обратите внимание на то, что отображаемое имя может отличаться от имени файла.  
  
-   Чтобы добавить все правила группы настраиваемый набор правил, установите флажок группы. Чтобы удалить все правила группы, снимите флажок.  
  
-   Чтобы добавить определенное правило настраиваемый набор правил, установите флажок правила. Чтобы удалить правило из набора правил, снимите флажок.  
  
-   Чтобы изменить действие, выполняемое при нарушении правила анализа кода, выберите **действие** поле для правила, а затем выберите один из следующих значений:  
  
     **Предупреждать** -приводит к возникновению предупреждения.  
  
     **Ошибка** -приводит к ошибке.  
  
     **Нет** -отключает правило. Это действие выполняется так же, как удалить правило из набора правил.  
  
#### <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>Для группировки, фильтрации, или изменить поля в редакторе набора правил с помощью панели инструментов редактора набора правил  
  
-   Чтобы развернуть правила во всех группах, выберите **развернуть все**.  
  
-   Чтобы свернуть правила во всех группах, выберите **Свернуть все**.  
  
-   Чтобы изменить поля, правила группируются по, выберите поле из **Group By** списка. Чтобы отобразить несгруппированные правила, выберите  **\<None >**.  
  
-   Чтобы добавить или удалить поля столбцов, правила, выберите **параметры столбцов**.  
  
-   Чтобы скрыть правила, которые не применяются к текущему решению, выберите **скрыть правила, которые не применяются к текущему решению**.  
  
-   Переключение между отображением и скрытием правил, которым назначено действие при возникновении ошибки, выберите **отображаются правила, которые могут вызвать ошибки анализа кода**.  
  
-   Переключение между отображением и скрытием правил, которым назначено действие предупреждение, выберите **отображаются правила, которые могут вызвать предупреждения анализа кода**.  
  
-   Переключение между отображением и скрытием правил, которым назначено **None** действие, выберите **отображаются правила, не включены**.  
  
-   Чтобы добавить или удалить наборы правил по умолчанию для текущего набора правил Майкрософт, выберите **добавить или удалить дочерние наборы правил**.


