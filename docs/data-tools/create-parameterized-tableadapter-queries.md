---
title: Создание параметризованных запросов адаптера таблицы TableAdapter
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- TableAdapters, parameterized queries
- data [Visual Studio], searching data
- queries [Visual Studio], creating
- TableAdapters, searching data
- queries [Visual Studio], TableAdapters
ms.assetid: 104d1d19-b5a9-4071-b81e-1b3af08e9c7b
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: a2b94e10dd09d26a17a7574db97880567f7725cd
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85282609"
---
# <a name="create-parameterized-tableadapter-queries"></a>Создание параметризованных запросов адаптера таблицы TableAdapter

Параметризированный запрос возвращает данные, удовлетворяющие условиям предложения WHERE в запросе. Например, можно параметризировать список клиентов, чтобы отображать только клиентов из определенного города, добавив `WHERE City = @City` в конец инструкции SQL, возвращающей список клиентов.

Параметризованные запросы TableAdapter создаются в **Конструктор наборов данных**. Их также можно создать в приложении Windows с помощью команды **параметризовать данные источника** в меню **данные** . Команда **параметризовать данные источника** создает элементы управления в форме, где можно ввести значения параметров и выполнить запрос.

> [!NOTE]
> При создании параметризованного запроса используйте нотацию параметра, относящуюся к базе данных, для которой выполняется кодирование. Например, источники данных Access и OleDb используют вопросительный знак "?" для обозначения параметров, поэтому предложение WHERE должно иметь следующий вид: `WHERE City = ?`.

## <a name="create-a-parameterized-tableadapter-query"></a>Создание параметризованного запроса TableAdapter

### <a name="to-create-a-parameterized-query-in-the-dataset-designer"></a>Порядок создания параметризованного запроса в Конструкторе наборов данных

- Создайте новый адаптер таблицы, добавив предложение WHERE с требуемыми параметрами в инструкцию SQL. Дополнительные сведения см. в разделе [Создание и настройка адаптеров таблиц](../data-tools/create-and-configure-tableadapters.md).

     -или-

- Добавьте запрос в существующий адаптер таблицы, добавив предложение WHERE с требуемыми параметрами в инструкцию SQL.

### <a name="to-create-a-parameterized-query-while-designing-a-data-bound-form"></a>Порядок создания параметризованного запроса при разработке формы с привязкой к данным

1. Выберите на форме элемент управления, который уже привязан к набору данных. Дополнительные сведения см. [в разделе привязка Windows Forms элементов управления к данным в Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md).

2. В меню **данные** выберите команду **Добавить запрос**.

3. Заполните диалоговое окно **Построитель условий поиска**, добавив предложение WHERE с требуемыми параметрами в инструкцию SQL.

### <a name="to-add-a-query-to-an-existing-data-bound-form"></a>Добавление запроса в существующую форму с привязкой к данным

1. Откройте форму в **конструкторе Windows Forms**.

2. В меню **данные** выберите команду **Добавить запрос** или **смарт-теги данных**.

    > [!NOTE]
    > Если команда **Добавить запрос** в меню **Данные отсутствует**, выберите на форме элемент управления, отображающий тот источник данных, в который вы хотите добавить параметризацию. Например, если форма отображает данные в элементе управления <xref:System.Windows.Forms.DataGridView>, выберите его. Если форма отображает данные в отдельных элементах управления, выберите любой элемент управления с привязкой к данным.

3. В области **Выбор таблицы источника данных** выберите таблицу, в которую необходимо добавить параметризацию.

4. Введите имя в поле **Имя нового запроса**, если вы создаете запрос.

     -или-

     Выберите запрос в поле **Имя существующего запроса**.

5. В **текстовом поле запрос** введите запрос, который принимает параметры.

6. Нажмите кнопку **ОК**.

     Элемент управления для ввода параметра и кнопка **Загрузка** добавляются на форму в элемент управления <xref:System.Windows.Forms.ToolStrip>.

### <a name="query-for-null-values"></a>Запрос значений NULL

Параметрам TableAdapter могут быть присвоены значения NULL, если требуется запросить записи, не имеющие текущего значения. Например, рассмотрим следующий запрос, имеющий `ShippedDate` параметр в своем `WHERE` предложении:

```sql
SELECT CustomerID, OrderDate, ShippedDate
FROM Orders
WHERE (ShippedDate = @ShippedDate) OR (ShippedDate IS NULL)
```

Если бы это был запрос к TableAdapter, можно запросить все заказы, которые не были отгружены, с помощью следующего кода:

[!code-csharp[VbRaddataTableAdapters#8](../data-tools/codesnippet/CSharp/create-parameterized-tableadapter-queries_1.cs)]
[!code-vb[VbRaddataTableAdapters#8](../data-tools/codesnippet/VisualBasic/create-parameterized-tableadapter-queries_1.vb)]

Чтобы разрешить запрос принимать значения NULL:

1. В **Конструктор наборов данных**выберите запрос TableAdapter, который должен принимать значения параметров NULL.

2. В окне **Свойства** выберите **Параметры**, а затем нажмите кнопку с многоточием (**...**), чтобы открыть **Редактор коллекции параметров**.

3. Выберите параметр, допускающий значения NULL, и задайте для свойства **AllowDbNull** значение `true` .

## <a name="see-also"></a>См. также

- [Заполнение наборов данных с помощью адаптеров таблицы](../data-tools/fill-datasets-by-using-tableadapters.md)
