---
title: "Оболочка Visual Studio (интегрированная) | Документы Microsoft"
ms.custom: 
ms.date: 02/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, integrated mode features
- Shell [Visual Studio], integrated mode features
ms.assetid: 0b40d495-f17f-4bb9-ace8-b365a7172784
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 74fa1e1d23725af1041d9c635a768b7667b3b888
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-shell-integrated"></a>Оболочка Visual Studio (интегрированная)
Оболочка Visual Studio интегрированы включает интегрированной среды разработки (IDE), отладчик и интеграции системы управления версиями. Язык программирования, не включается. Тем не менее интегрированная оболочка предоставляют платформу, которая позволяет добавлять языков программирования.  
  
 Оболочка Visual Studio интегрированы фактически представляет собой соединение Visual Studio изолированной оболочки, а также дополнительные установки, который включения определенных компонентов интегрированная оболочка.  Интегрированная оболочка приложения должен включать оба изолированной оболочки распространяемого пакета из [распространяемый пакет оболочки Microsoft Visual Studio (изолированной)](http://go.microsoft.com/fwlink/?LinkId=616022) и распространяемый пакет интегрированная оболочка из [(интегрированный) распространяемый пакет оболочки Microsoft Visual Studio](http://go.microsoft.com/fwlink/?LinkId=616021).  
  
> [!NOTE]
>  Чтобы получить доступ к изолированной и интегрированная оболочка распространяемые пакеты, будет предложено заполните опрос краткое клиента.  После заполнения опроса, вы будете перенаправлены на страницу Visual Studio подключиться с помощью ссылки для загрузки распространяемого пакета.  Можно найти ссылки для загрузки при последующих посещениях сайта Visual Studio подключиться согласно **программы &#124; 2015 ИНТЕГРАЦИИ и ИЗОЛИРОВАННОЙ ОБОЛОЧКИ VISUAL STUDIO** вкладки.  
  
 При установке приложения интегрированная оболочка на том же компьютере, как полная версия Visual Studio компоненты приложения будут встроены непосредственно в Visual Studio.  
  
## <a name="features-in-the-integrated-shell"></a>Функции в интегрированной оболочке  
  
|||  
|-|-|  
|Область функции|Функция|  
|Языковая поддержка|— None|  
|IDE|<ul><li>Параметры<br /><br /> <ul><li>Создание параметров</li><li>Импорт и экспорт параметров</li><li>Сброс параметров</li></ul></li><li>**Панель элементов** интеграции</li><li>**Список задач** интеграции</li><li>Интеграция справки</li><li>**Параметры** диалоговое окно</li><li>Управление шрифты и цвета</li><li>**Выходные данные** окна</li><li>**Команда** окна</li><li>Управление окнами</li><li>Команды, меню и сочетания клавиш</li><li>Среда выполнения доменный язык (DSL)</li></ul>|  
|Система работы с проектами и типами проектов|-Решений и решений папок<br />— Диспетчер конфигураций решение<br />-Элемент управления<br />-Одиночных проектов и многопроектных решений<br />-Конструктор приложений (свойства проекта упрощенный)<br />-Добавление веб-ссылки<br />— Добавление ссылки на службу<br />Одиночных проектов<br />— Типы проектов веб-сайта<br />-Проекты веб приложений|  
|Построить|-Настраиваемые этапы построения в интегрированной среде разработки<br />-Предварительной компиляции для защиты интеллектуальной собственности (IP)<br />-Подписывание кода<br />     MSBuild|  
|Редактор|-Кода, просмотр средства (единый поиск, определение источника, наследования)<br />-Навигация по коду<br />-IntelliSense<br />-Смарт-теги<br />-Рефакторинга<br />-Автоматическое форматирование<br />-Фильтрация IntelliSense<br />-   **Определение кода** окна|  
|Designer|-Windows Presentation Foundation конструктора<br />-Windows Forms в конструкторе<br />-Веб-конструктор и редактор HTML|  
|Данные|-   **Обозреватель серверов** (упрощенное письмо: только данные). См. примечание 1.<br />-   **Источники данных** окна<br />-Полный набор элементов данных<br />-XML редактор<br />-Данные привязки к локальному источнику данных (. MDF или. MDB)<br />-Привязать данные объект<br />-Привязка данных веб-службе<br />-Привязать данные на локальном сервере баз данных<br />— Привязать данные удаленный сервер базы данных<br />-DDL средства для удаленных данных<br />-   **Обозреватель серверов** расширяемости ([!INCLUDE[vsipsdk](../includes/vsipsdk_md.md)] образцы)|  
|Отладчик|-Локальной отладки. См. Примечание 2.<br />-Отладки управляемого кода<br />-Локальной отладки<br />-Присоединения локального процесса<br />-Присоединения удаленного процесса<br />-Анонимного делегата<br />-Домены приложений<br />-ASPX отладки<br />-Атрибуты<br />-Прервать выполнение Func eval<br />-Точки останова<br />-Точка останова ограничения<br />-Стек вызовов<br />-   **Команда** окна<br />-Отладка между потоками<br />-Советы данных<br />-Визуализатор данных<br />-Поддержка отладчика помощников по отладке управляемого (кода MDA)<br />-Поддержка отладчика метод передачи типа<br />-Поддержка DTEEvents инициирует событие OTB<br />-JMC пошаговым<br />-Тест AppID отладчика (DBGCLR)<br />-Профиль отладчика<br />-Отладчика средства и параметры<br />-Отладка итератора<br />-Вычисление выражений во время разработки<br />-Средство оценки выражений C#<br />-Дизассемблированный код<br />-Изменить и продолжить<br />-Выражение оценки windows (Контрольные значения, локальные переменные, видимые)<br />-Помощник по исправлению ошибок<br />-Исключения<br />— Выполнение<br />– Универсальные шаблоны<br />-Получение исходного кода<br />-Отладка/кластера HPC<br />-Интегрированные отладки нескольких языков<br />-Отладка взаимодействия<br />-Отладка just-in-time<br />-Локальной отладки<br />-Отладки управляемого кода<br />-Ручное управление (окно процессы)<br />-Памяти<br />-Поддержка минидампа<br />— Модули<br />-Отладка процессов<br />-Отладка машинного кода<br />-Поддержка нового ядра отладки<br />-Отладка оптимизированного кода<br />-Windows output фильтрации<br />-Обработка размещения для отладки управляемого кода<br />-Процессов<br />-"Быстрая проверка"<br />-Регистры<br />-Регистров в стек<br />-Удаленной отладки<br />-Возвращаемые значения<br />-Отладка скриптов<br />-Поддержка службы источника<br />-Безопасности<br />Side-by-side<br />-SQL<br />-Сервер символов<br />-Точки трассировки<br />-Поток<br />-Визуализации<br />-Отладчик extensible Stylesheet Language преобразований (XSLT)|  
|Поддержка 64-разрядных|-64-разрядная отладка управляемого и машинного кода, все языки<br />-поддерживает собственный x64|  
|Управление исходным кодом (SCC)|— Базовый SCC интеграции. См. Примечание 3.<br />-Средства и параметры проверки|  
|Расширение среды|-Использование пакетов VSPackage и MEF|  
  
## <a name="notes"></a>Примечания  
  
#### <a name="1-data-tools"></a>1. Data Tools  
 Интегрированная оболочка включает средств разработки баз данных, такие как поддержка расширяемости данных и упрощенный **обозревателе решений**. Однако SQL Server Express, SQL Reporting и Crystal Reports не включаются в интегрированной оболочке.  
  
#### <a name="2-debugging-support"></a>2. Поддержка отладки  
 Интегрированная оболочка содержит тот же механизм отладки, которое включено в версии Visual Studio Community. Ядро отладки включает общие отладчик для управляемого кода, а также связанные функции, такие, как выполнить присоединение, установить точку останова, изменить и продолжить и другим пользователям. Однако ядро отладки не поддерживает отладку базы данных SQL Server.  
  
 Несмотря на то что поддержки для отладка машинного кода включен в пакет basic отладчик, не может расширить его, чтобы поддерживать дополнительные языки.  
  
#### <a name="3-source-code-control-integration"></a>3. Интеграции управления исходным кодом  
 Интегрированная оболочка предоставляет API-интерфейсы для реализации управления исходным кодом (SCC), а также для предоставления компоненты интеграции на основе MSSCCI общие системы управления версиями.  
  
 Хотя SCC интеграции не регулярного функция профессионального выпуска Visual Studio, интеграция SCC предоставляется в интегрированной оболочке.  
  
#### <a name="4-build-support"></a>4. Поддержка построения  
 Интегрированная оболочка обеспечивает поддержку построения. Можно найти сведения о сборках в [Справочник по MSBuild](../../msbuild/msbuild-reference.md).  
  
## <a name="features-not-included-in-the-integrated-shell"></a>Компоненты, не включенные в интегрированной оболочке  
 Ниже приведен список возможностей, которые не включены в интегрированной оболочке:  
  
-   Конструктор классов  
  
-   [Защита preEmptive - Dotfuscator](../../ide/dotfuscator/index.md)  
  
-   Возможности языка  
  
-   VSHost  
  
-   Никакие языки Visual Studio или их шаблоны связанных проектов или шаблоны элементов проекта, включенные в интегрированной оболочке. Для примеров фрагментов кода Visual Basic включены не зависящие от языка реализации других возможностей.  
  
## <a name="see-also"></a>См. также  
 [Пакет SDK для Visual Studio](../visual-studio-sdk.md)