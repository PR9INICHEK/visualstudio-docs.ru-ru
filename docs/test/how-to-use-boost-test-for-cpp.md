---
title: Использование Boost.Test для C++
description: Используйте Boost.Test для создания модульных тестов в Visual Studio.
ms.date: 01/29/2020
ms.topic: how-to
author: corob-msft
ms.author: corob
manager: markl
ms.workload:
- cplusplus
ms.openlocfilehash: 34c593469a586d1314c7ee52f3aeb3ab6faf334c
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85287276"
---
# <a name="how-to-use-boosttest-for-c-in-visual-studio"></a>Использование Boost.Test для C++ в Visual Studio

В Visual Studio 2017 и более поздних версиях адаптер теста Boost.Test интегрирован в среду IDE Visual Studio. Это компонент рабочей нагрузки **Разработка классических приложений на C++** .

![Адаптер теста для Boost.Test](media/cpp-boost-component.png)

Если у вас не установлена рабочая нагрузка **Разработка классических приложений на C++** , откройте **Установщик Visual Studio**. Выберите рабочую нагрузку **Разработка классических приложений на C++** , а затем нажмите кнопку **Изменить**.

## <a name="install-boost"></a>Установка Boost

Для Boost.Test требуется [Boost](https://www.boost.org/). Если у вас не установлен Boost, рекомендуем воспользоваться диспетчером пакетов Vcpkg.

1. Следуйте инструкциям в статье [vcpkg: диспетчер пакетов C++ для Windows](/cpp/vcpkg), чтобы установить диспетчер vcpkg (если у вас его еще нет).

1. Установка динамической или статической библиотеки Boost.Test:

    - Запустите `vcpkg install boost-test`, чтобы установить динамическую библиотеку Boost.Test.

       -ИЛИ-

    - Запустите `vcpkg install boost-test:x86-windows-static`, чтобы установить статическую библиотеку Boost.Test.

1. Выполните `vcpkg integrate install`, чтобы настроить в Visual Studio библиотеку и пути включения для заголовков и двоичных файлов Boost.

Вы можете выбрать способ настройки тестов в своем решении в Visual Studio: Вы можете включить тестовый код в тестируемый проект или создать отдельный тестовый проект для проведения тестов. Оба варианта имеют свои преимущества и недостатки.

## <a name="add-tests-inside-your-project"></a>Добавление тестов в проект

В Visual Studio 2017 версии 15.6 и более поздних можно добавить шаблон элемента для тестов в проект. Тесты и код находятся в одном проекте. Для создания тестовой сборки потребуется создать отдельную конфигурацию сборки. И вам нужно будет следить за тем, чтобы в сборках отладки и выпуска тестов не было.

В Visual Studio 2017 версии 15.5 для Boost.Test нет предварительно настроенного тестового проекта или шаблонов элементов. Используйте инструкции для создания и настройки отдельного тестового проекта.

### <a name="create-a-boosttest-item"></a>Создание элемента Boost.Test

1. Чтобы создать *CPP*-файл для тестов, щелкните правой кнопкой мыши узел проекта в **обозревателе решений** и выберите пункт **Добавить** > **Новый элемент**.

1. В диалоговом окне **Добавление нового элемента** последовательно разверните узлы **Установлено** > **Visual C++**  > **Тест**. Выберите **Boost.Test** и затем **Добавить**, чтобы добавить *Test.cpp* в проект.

   ![Шаблон элемента Boost.Test](media/boost_test_item_template.png)

Новый файл *Test.cpp* содержит пример метода теста. В этот файл можно включить собственные файлы заголовков и записать тесты для приложения.

Этот тестовый файл также использует макросы для определения новой подпрограммы `main` для конфигураций тестов. Если выполнить сборку проекта сейчас, выводится ошибка LNK2005, например "_main уже определен в main.obj".

### <a name="create-and-update-build-configurations"></a>Создание и изменение конфигураций сборки

1. Чтобы создать конфигурацию теста, в строке меню выберите **Сборка** > **Диспетчер конфигураций**. В диалоговом окне **Диспетчер конфигураций** выберите в раскрывающемся списке **Активная конфигурация решения** пункт **Создать**. В диалоговом окне **Создание конфигурации решения** введите имя, например "Debug UnitTests". В поле **Копировать параметры из** выберите **Отладка**, а затем нажмите кнопку **ОК**.

1. Исключите тестовый код из конфигураций отладки и выпуска: В **обозревателе решений** щелкните правой кнопкой мыши файл Test.cpp и выберите пункт **Свойства**. В диалоговом окне **Страницы свойств** откройте раскрывающийся список **Конфигурация** и выберите **Все конфигурации**. Выберите **Свойства конфигурации** > **Общие** и откройте раскрывающийся список для свойства **Исключено из сборки**. Выберите **Да**, а затем нажмите кнопку **Применить**, чтобы сохранить изменения.

1. Чтобы включить код теста в конфигурацию "Debug UnitTests", в диалоговом окне **Страницы свойств** выберите **Debug UnitTests** в раскрывающемся списке **Конфигурация**. Выберите **Нет** в свойстве **Исключено из сборки** и нажмите кнопку **ОК** для сохранения изменений.

1. Исключите основной код из конфигурации "Debug UnitTests". В **обозревателе решений** щелкните правой кнопкой мыши файл, содержащий функцию `main`, и выберите пункт **Свойства**. В диалоговом окне **Страницы свойств** откройте раскрывающийся список **Конфигурация** и выберите **Debug UnitTests**. Выберите **Свойства конфигурации** > **Общие** и откройте раскрывающийся список для свойства **Исключено из сборки**. Выберите **Да**, а затем нажмите кнопку **ОК**, чтобы сохранить изменения.

1. Выберите конфигурацию решения **Debug UnitTests**, а затем создайте проект, чтобы **обозреватель тестов** смог обнаружить этот метод.

При условии, что создаваемое имя конфигурации начинается со слова "Debug" или "Release", соответствующие библиотеки Boost.Test подбираются автоматически.

Шаблон элемента использует вариант Boost.Test с одним заголовком, но вы можете изменить путь в #include, чтобы указать автономный вариант библиотеки. Дополнительные сведения см. в разделе [Добавление директив include](#add-include-directives).

## <a name="create-a-separate-test-project"></a>Создание отдельного тестового проекта

Во многих случаях для тестов проще использовать отдельный проект. Вам не нужно будет создавать специальную конфигурацию теста для своего проекта. Или исключите тестовые файлы из сборок отладки и выпуска.

### <a name="to-create-a-separate-test-project"></a>Создание отдельного тестового проекта

1. В **обозревателе решений** щелкните узел решения правой кнопкой мыши и выберите пункты **Добавить** > **Новый проект**.

1. В диалоговом окне **Добавить новый проект** выберите **C++** , **Windows** и **Консоль** в раскрывающихся списках фильтров. Выберите шаблон **Консольное приложение** и нажмите кнопку **Далее**.

1. Присвойте проекту имя и нажмите кнопку **Создать**.

1. Удалите функцию `main` из *CPP*-файла.

1. Если вы используете версию Boost.Test с одним заголовком или динамическую версию библиотеки, перейдите к разделу [Добавление директив #include](#add-include-directives). Если вы используете статическую версию библиотеки, вам нужно выполнить некоторые дополнительные настройки:

   1\. Чтобы изменить файл проекта, сначала выгрузите его. В **обозревателе решений** щелкните узел проекта правой кнопкой мыши и выберите пункт **Выгрузить проект**. Затем щелкните правой кнопкой мыши узел проекта и выберите **Изменить <имя\>.vcxproj**.

   2\. Добавьте две строки в группу свойств **Глобальные**, как показано ниже:

    ```xml
    <PropertyGroup Label="Globals">
    ....
        <VcpkgTriplet>x86-windows-static</VcpkgTriplet>
        <VcpkgEnabled>true</VcpkgEnabled>
    </PropertyGroup>
    ```

   В. Сохраните и закройте *\*VCXPROJ*-файл и затем перезагрузите проект.

   Г. Чтобы открыть диалоговое окно **Страницы свойств**, щелкните узел проекта правой кнопкой мыши и выберите пункт **Свойства**.

   Д. Разверните узел **C/C++**  > **Создание кода**, а затем выберите элемент **Библиотека времени выполнения**. Выберите **/MTd** в качестве статической библиотеки времени выполнения для отладки или **/MT** в качестве статической библиотеки времени выполнения для выпуска.

   f. Разверните узел **Компоновщик** > **Система**. Убедитесь, что для параметра **SubSystem** задано значение **Консоль**.

   ж. Нажмите кнопку **ОК**, чтобы закрыть окно страниц свойств.

## <a name="add-include-directives"></a>Добавление директив include

1. В *CPP*-файле теста добавьте необходимые директивы `#include`, чтобы типы и функции программы были доступны коду теста. Если вы используете отдельный тестовый проект, как правило, программа находится в иерархии папок на том же уровне. При вводе `#include "../"` открывается окно IntelliSense, в котором можно выбрать полный путь к файлу заголовка.

   ![Добавление директив #include](media/cpp-gtest-includes.png)

   Можно использовать автономную библиотеку с:

   ```cpp
   #include <boost/test/unit_test.hpp>
   ```

   Или использовать версию с одним заголовком с:

   ```cpp
   #include <boost/test/included/unit_test.hpp>
   ```

   Затем определите `BOOST_TEST_MODULE`.

Приведенного ниже примера достаточно для обнаружения теста в **обозревателе тестов**.

```cpp
#define BOOST_TEST_MODULE MyTest
#include <boost/test/included/unit_test.hpp\> //single-header
#include "../MyProgram/MyClass.h" // project being tested
#include <string>

BOOST_AUTO_TEST_CASE(my_boost_test)
{
    std::string expected_value = "Bill";

    // assume MyClass is defined in MyClass.h
    // and get_value() has public accessibility
    MyClass mc;
    BOOST_CHECK(expected_value == mc.get_value());
}
```

## <a name="write-and-run-tests"></a>Написание и запуск тестов

Все готово к написанию и выполнению тестов Boost. Сведения о макросах тестов см. в [документации по библиотеке Boost Test](https://www.boost.org/doc/libs/1_71_0/libs/test/doc/html/index.html). Сведения об обнаружении, выполнении и группировании тестов с помощью **обозревателя тестов** см. в статье [Выполнение модульных тестов с помощью обозревателя тестов](run-unit-tests-with-test-explorer.md).

## <a name="see-also"></a>См. также

- [Написание модульных тестов для C/C++](writing-unit-tests-for-c-cpp.md)
