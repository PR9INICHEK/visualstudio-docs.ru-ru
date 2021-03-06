---
title: Оболочка Visual Studio (интегрированная) | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio shell, integrated mode features
- Shell [Visual Studio], integrated mode features
ms.assetid: 0b40d495-f17f-4bb9-ace8-b365a7172784
caps.latest.revision: 26
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 907b71d82a3c630bedc48209e735d9cf817432ad
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85543160"
---
# <a name="visual-studio-shell-integrated"></a>Оболочка Visual Studio (интегрированная)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Интегрированная оболочка Visual Studio включает интегрированную среду разработки (IDE), отладчик и интеграцию системы управления версиями. Язык программирования не включен. Однако Интегрированная оболочка предоставляет платформу, которая позволяет добавлять языки программирования.  
  
 Интегрированная оболочка Visual Studio на самом деле является сочетанием изолированной оболочки Visual Studio и дополнительной установки, включающей встроенные компоненты оболочки.  Интегрированное приложение оболочки должно включать в себя как распространяемый пакет изолированной оболочки, так и распространяемый пакет интегрированной оболочки из [распространяемых пакетов оболочки Microsoft Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/isolated-shell/).  
  
> [!NOTE]
> Прежде чем получить доступ к изолированным и интегрированным распространяемым пакетам оболочки, вам будет предложено заполнить краткий опрос клиентов.  После заполнения опроса вы будете перенаправлены на страницу Visual Studio Connect с ссылками для скачивания распространяемых пакетов.  Ссылки для скачивания см. в последующих посещениях сайта Visual Studio Connect в разделе **программы &#124; вкладке интегрированная и изолированная оболочка Visual studio 2015** .  
  
 Если приложение интегрированной оболочки установлено на том же компьютере, что и полная версия Visual Studio, компоненты вашего приложения будут интегрированы непосредственно в Visual Studio.  
  
## <a name="features-in-the-integrated-shell"></a>Функции интегрированной оболочки  
  
|Область функций|Компонент|  
|-|-|  
|Поддержка языков|— Нет|  
|IDE|<ul><li>Настройки<br /><br /> <ul><li>Создание параметров</li><li>Импорт и экспорт параметров</li><li>Сброс параметров</li></ul></li><li>Интеграция **панели элементов**</li><li>Интеграция **список задач**</li><li>Интеграция справки</li><li>Диалоговое окно " **Параметры** "</li><li>Управление шрифтами и цветами</li><li>Окно **вывода**</li><li>**Командное** окно</li><li>Управление окнами</li><li>Команды, меню и сочетания клавиш</li><li>Среда выполнения для доменного языка (DSL)</li></ul>|  
|Типы системы проектов и проектов|— Решения и папки решений<br />— Диспетчер конфигурации решений<br />— Управление элементами<br />— Решения с одним проектом и несколькими проектами<br />-Конструктор приложений (упрощенные свойства проекта)<br />-Добавить веб-ссылку<br />— Добавление ссылки на службу<br />-Один проект<br />— Типы проектов веб-сайтов<br />— Проекты веб-приложений|  
|Сборка|— Настраиваемые шаги сборки в интегрированной среде разработки<br />— Предварительная компиляция для защиты интеллектуальной собственности (IP)<br />— Подписывание кода<br />     MSBuild|  
|Редактор|— Средства обзора кода (унифицированный поиск, определение источника, наследование)<br />— Навигация по коду<br />— Технология IntelliSense<br />-Смарттагс<br />-Рефакторинг<br />-Достаточное перечисление<br />— Фильтрация IntelliSense<br />-   Окно **определения кода**|  
|Конструктор|Конструктор Windows Presentation Foundation<br />— Конструктор Windows Forms<br />— Веб-дизайнер и редактор HTML|  
|Данные|-   **Обозреватель сервера** (упрощенные: только данные). См. примечание 1.<br />-   Окно " **Источники данных** "<br />— Полный набор элементов управления данными<br />— Редактор XML<br />-Привязка данных к локальному источнику данных (. MDF или. ФОРМАТЕ<br />-Привязка данных к объекту<br />-Привязка данных к веб-службе<br />-Привязка данных к локальному серверу базы данных<br />-Привязка данных к удаленному серверу базы данных<br />-Средства DDL для удаленных данных<br />-   Расширяемость **Обозреватель сервера** ( [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] примеры)|  
|Отладчик|— Локальная отладка. См. Примечание 2.<br />-Управляемая отладка<br />— Локальная отладка<br />-Присоединение к локальному процессу<br />-Присоединение к удаленному процессу<br />— Анонимный делегат<br />— Домены приложений<br />— Отладка ASPX<br />Атрибуты<br />-Break во время выполнения Func-eval<br />— Точки останова<br />— Ограничения точки останова<br />-Стек вызовов<br />-   **Командное** окно<br />— Отладка между потоками<br />— Советы по данным<br />— Визуализатор данных<br />— Поддержка отладчика для помощников по отладке управляемого кода (MDA)<br />— Поддержка отладчика для сервера пересылки типа<br />-DTEEvents инициирует событие поддержка для OTB<br />-JMCное средство Организации<br />— Тест AppID отладчика (ДБГКЛР)<br />-Профиль отладчика<br />-Средства и параметры отладчика<br />-Итератор отладки<br />— Вычисление выражений во время разработки<br />— Средство оценки выражений C#<br />-Дизассемблированный код<br />-Изменить и продолжить<br />— Окна средства оценки выражений (контрольные значения, локальные переменные, Auto)<br />-Вспомогательное приложение исключения<br />— Исключения<br />Выполнение<br />– Универсальные шаблоны<br />-Получение правильного источника<br />— Отладка HPC/кластера<br />— Интегрированная многоязыковая отладка<br />— Отладка взаимодействия<br />— JIT-отладка<br />— Локальная отладка<br />-Управляемая отладка<br />— Ручное управление (окно процессов)<br />— Память<br />— Поддержка минидампа<br />-Modules<br />— Отладка с несколькими процессами<br />— Отладка в машинном код<br />-Новая поддержка модуля отладки<br />— Отладка оптимизированного кода<br />— Фильтрация окон вывода<br />— Размещение процессов для управляемой отладки<br />— Процессы<br />— Быстрая проверка<br />— Регистры<br />— Регистры в стеке<br />— Удаленная отладка<br />— Возвращаемые значения<br />— Отладка скриптов<br />— Поддержка исходной службы<br />— Безопасность<br />-Side-to-side<br />-SQL<br />— Сервер символов<br />-Точки трассировки<br />-Thread<br />— Визуализации<br />— Отладчик XSLT (Extensible Stylesheet Transform)|  
|Поддержка 64-разрядных версий|-64-разрядная отладка для управляемого и машинного кода, все языки<br />— собственная поддержка x64|  
|Управление исходным кодом (SCC)|— Базовая интеграция SCC. См. Примечание 3.<br />— Проверка средств и параметров|  
|Расширение среды|— Использование пакетов VSPackage и компонентов MEF|  
  
## <a name="notes"></a>Примечания  
  
#### <a name="1-data-tools"></a>1. средства для данных  
 Интегрированная оболочка включает средства разработки баз данных, такие как поддержка расширяемости данных и упрощенные **Обозреватель решений**. Однако SQL Server Express, SQL Reporting и Crystal Reports не включены в интегрированную оболочку.  
  
#### <a name="2-debugging-support"></a>2. Поддержка отладки  
 Интегрированная оболочка содержит тот же модуль отладки, который входит в состав версии Visual Studio Community. Модуль отладки включает в себя общий отладчик для управляемого кода, а также связанные функции, такие как запуск, присоединение, Установка точки останова, изменение и продолжение и другие. Однако модуль отладки не поддерживает SQL Server отладки базы данных.  
  
 Несмотря на то, что поддержка отладки в машинном код включена в базовый пакет отладчика, ее нельзя расширить для поддержки дополнительных языков.  
  
#### <a name="3-source-code-control-integration"></a>3. Интеграция системы управления версиями исходного кода  
 Интегрированная оболочка предоставляет интерфейсы API для реализации управления исходным кодом (SCC) и для предоставления общих компонентов интеграции системы управления версиями на основе MSSCCI.  
  
 Хотя интеграция SCC не является обычной функцией выпуска Pro Visual Studio, в интегрированной оболочке предусмотрена интеграция SCC.  
  
#### <a name="4-build-support"></a>4. Поддержка сборки  
 Интегрированная оболочка обеспечивает поддержку сборки. Сведения о сборках можно найти в [справочнике по MSBuild](../msbuild/msbuild-reference.md).  
  
## <a name="features-not-included-in-the-integrated-shell"></a>Функции, не входящие в интегрированную оболочку  
 Ниже приведен список функций, не включенных в интегрированную оболочку:  
  
- Конструктор классов  
  
- PreEmptive Protection — Dotfuscator  
  
- Возможности языка  
  
- VSHost  
  
- В интегрированной оболочке отсутствуют языки Visual Studio, связанные с ними шаблоны проектов или шаблоны элементов проектов. Некоторые реализации других функций для конкретного языка не включены, например Visual Basic фрагменты кода.  
  
## <a name="see-also"></a>См. также  
 [Обзор расширения Visual Studio](https://msdn.microsoft.com/library/3e9078d7-2763-4cc4-8e20-fac69d747f59)
