---
title: "Создание конструктора — создание кода (Visual Basic) | Документация Майкрософт"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2280cfa-a9ec-4b56-9d94-c8fd384db980
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 891a33b74927d45434c4614dc4c5d7f1533ba4c0
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2018
---
# <a name="generate-a-constructor-in-visual-basic"></a>Создание конструктора в Visual Basic
**Что?** Вы можете немедленно создавать код для нового конструктора в классе. 

**Когда?** Вы представляете новый конструктор и хотите правильно его объявить автоматически.  

**Зачем?** Вы можете объявить конструктор до его использования. Но этот компонент автоматически создаст его с соответствующими параметрами. 

**Как?**

1. Поместите курсор в строку с красной волнистой линией. Она указывает, что вы использовали конструктор, который еще не существует.

   ![Выделенный код](media/constructor-highlight-vb.png)

1. Затем выполните одно из следующих действий:
   * **Клавиатура**
     * Нажмите клавиши **CTRL+.**, чтобы активировать меню **Быстрые действия и рефакторинг**. Затем выберите во всплывающем окне предварительного просмотра пункт **Generate constructor in '*TypeName*'** (Создать конструктор в "TypeName").
   * **Мышь**
     * Щелкните правой кнопкой мыши и выберите меню **Быстрые действия и рефакторинг**. Затем выберите во всплывающем окне предварительного просмотра пункт **Generate constructor in '*TypeName*'** (Создать конструктор в "TypeName").
     * Наведите указатель мыши на красную волнистую линию и щелкните ![значок лампочки,](media/bulb-vb.png) который отображается.
     * Нажмите кнопку ![значок лампочки,](media/bulb-vb.png) который отображается в левом поле, если текстовый курсор уже находится в строке выбора с красной волнистой линией.

   ![Создание конструктора — предварительный просмотр](media/constructor-preview-vb.png)

   >[!TIP]
   >Щелкните ссылку [**Просмотреть изменения**](../../ide/preview-changes.md) в нижней части окна предварительного просмотра, чтобы просмотреть все изменения перед выбором.

1. Конструктор будет создан автоматически со всеми параметрами с учетом его использования.

   ![Результат создания конструктора](media/constructor-result-vb.png)
 
## <a name="see-also"></a>См. также

[Создание кода](../code-generation-in-visual-studio.md)  
[Просмотр изменений](../../ide/preview-changes.md)