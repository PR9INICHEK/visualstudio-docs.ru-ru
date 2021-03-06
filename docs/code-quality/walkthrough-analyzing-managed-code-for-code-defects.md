---
title: Пошаговое руководство по анализу управляемого кода для дефектов кода | Документация Майкрософт
ms.date: 01/29/2018
ms.topic: conceptual
helpviewer_keywords:
- code analysis [Visual Studio]
- managed code, analyzing
author: mikadumont
ms.author: midumont
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ab1e0b890d6241742770ed38ff61fc1c2c0ed2f4
ms.sourcegitcommit: 08c144d290da373df841f04fc799e3133540a541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72535703"
---
# <a name="walkthrough-use-static-code-analysis-to-find-code-defects"></a>Пошаговое руководство. Использование статического анализа кода для поиска дефектов кода

В этом пошаговом руководстве вы проанализируете управляемый проект на предмет дефектов кода, используя прежний анализ кода.

В этой статье описывается процесс использования устаревшего анализа для анализа сборок управляемого кода .NET на соответствие рекомендациям по проектированию .NET.

## <a name="create-a-class-library"></a>Создание библиотеки классов

1. Откройте Visual Studio и создайте новый проект на основе шаблона **библиотеки классов (.NET Framework)** .

1. Назовите проект **кодеаналисисманажеддемо**.

1. После создания проекта откройте файл *Class1.CS* .

1. Замените существующий текст в Class1.cs следующим кодом:

   ```csharp
   using System;

   namespace testCode
   {
       public class demo : Exception
       {
           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int item { get { return _item; } }
       }
   }
   ```

1. Сохраните файл Class1.cs.

## <a name="analyze-the-project-for-code-defects"></a>Анализ проекта на предмет дефектов кода

1. Выберите проект Кодеаналисисманажеддемо в **Обозреватель решений**.

2. В меню **Проект** выберите пункт **Свойства**.

   Отобразится страница свойств Кодеаналисисманажеддемо.

3. Перейдите на вкладку **анализ кода** .

::: moniker range="vs-2017"

4. Убедитесь, что выбран **параметр Включить анализ кода при сборке** .

5. В раскрывающемся списке **выполнить этот набор правил** выберите параметр **Майкрософт все правила**.

::: moniker-end

::: moniker range=">=vs-2019"

4. Убедитесь, что в разделе **анализаторы двоичных файлов** выбран параметр **выполнять при сборке** .

5. В раскрывающемся списке **активные правила** выберите **Microsoft ALL Rules (все правила**).

::: moniker-end

6. В меню **файл** выберите команду **Сохранить выбранные элементы**, а затем закройте страницы свойств.

7. В меню **Сборка** выберите команду **построить кодеаналисисманажеддемо**.

    Предупреждения сборки проекта Кодеаналисисманажеддемо отображаются в окнах **Список ошибок** и **вывод** .

## <a name="correct-the-code-analysis-issues"></a>Устранение проблем с анализом кода

1. В меню **вид** выберите **Список ошибок**.

    В зависимости от выбранного профиля разработчика может потребоваться указать **другие окна** в меню **вид** , а затем выбрать **Список ошибок**.

1. В **обозревателе решений** выберите **Показать все файлы**.

1. Разверните узел Свойства, а затем откройте файл *AssemblyInfo.CS* .

1. Чтобы исправить предупреждения, используйте следующие советы.

   [CA1014: Пометьте сборки с помощью CLSCompliantAttribute](../code-quality/ca1014.md): добавьте код `[assembly: CLSCompliant(true)]` в конец файла AssemblyInfo.cs.

   [CA1032: реализуйте стандартные конструкторы исключений](../code-quality/ca1032.md): добавьте конструктор `public demo (String s) : base(s) { }` к классу `demo`.

   [CA1032: реализуйте стандартные конструкторы исключений](../code-quality/ca1032.md): добавьте конструктор `public demo (String s, Exception e) : base(s, e) { }` к классу `demo`.

   [CA1032: реализуйте стандартные конструкторы исключений](../code-quality/ca1032.md): добавьте конструктор `protected demo (SerializationInfo info, StreamingContext context) : base(info, context) { }` в демонстрацию класса. Также необходимо добавить оператор `using` для <xref:System.Runtime.Serialization?displayProperty=fullName>.

   [CA1032: реализуйте стандартные конструкторы исключений](../code-quality/ca1032.md): добавьте конструктор `public demo () : base() { }` к классу `demo`.

   [CA1709: идентификаторы должны иметь правильный регистр](../code-quality/ca1709.md): измените регистр пространства имен `testCode` на `TestCode`.

   [CA1709: идентификаторы должны иметь правильный регистр](../code-quality/ca1709.md): измените имя члена на `Demo`.

   [CA1709: идентификаторы должны иметь правильный регистр](../code-quality/ca1709.md): измените имя члена на `Item`.

   [CA1710: идентификаторы должны иметь правильные суффиксы](../code-quality/ca1710.md): измените имя класса и его конструкторов на `DemoException`.

   [CA2237: Mark Types ISerializable with SerializableAttribute](../code-quality/ca2237.md): добавьте атрибут `[Serializable ()]` в класс `demo`.

   [CA2210: сборки должны иметь допустимые строгие имена](../code-quality/ca2210.md): знак "кодеаналисисманажеддемо" с ключом строгого имени:

   1. В меню **проект** выберите **Свойства кодеаналисисманажеддемо**.

      Отобразятся свойства проекта.

   1. Перейдите на вкладку **Подписывание** .

   1. Установите флажок **подписать сборку** .

   1. В списке **выберите имя строки файл ключей** выберите **\<New >** .

      Откроется диалоговое окно **Создание ключа строгого имени** .

   1. В качестве **имени файла ключа**введите **тесткэй**.

   1. Введите пароль и нажмите кнопку **ОК**.

   1. В меню **файл** выберите команду **Сохранить выбранные элементы**, а затем закройте страницы свойств.

   После выполнения всех изменений файл Class1.cs должен выглядеть следующим образом:

   ```csharp
   using System;
   using System.Runtime.Serialization;

   namespace TestCode
   {
       [Serializable()]
       public class DemoException : Exception
       {
           public DemoException () : base() { }
           public DemoException(String s) : base(s) { }
           public DemoException(String s, Exception e) : base(s, e) { }
           protected DemoException(SerializationInfo info, StreamingContext context) : base(info, context) { }

           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int Item { get { return _item; } }
       }
   }
   ```

1. Перестройте проект.

## <a name="exclude-code-analysis-warnings"></a>Исключить предупреждения анализа кода

1. Для каждого из оставшихся предупреждений выполните следующие действия.

    1. Выберите предупреждение в **Список ошибок**.

    1. В контекстном меню (контекстное меню) выберите **подавлять** > **в файле подавления**.

1. Перестройте проект.

     Проект строится без предупреждений или ошибок.

## <a name="see-also"></a>См. также

[Анализ кода для управляемого кода](../code-quality/code-analysis-for-managed-code-overview.md)
