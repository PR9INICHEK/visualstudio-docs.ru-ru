---
title: "Краткое руководство. Создание первого веб-приложения Python с помощью Visual Studio | Документы Майкрософт"
ms.custom: 
ms.date: 12/1/2017"
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
ms.devlang: python
author: kraigb
ms.author: kraigb
manager: ghogen
dev_langs: python
ms.workload: python
ms.openlocfilehash: bf0a6e187a98a03d3beed33537fe5244ecd5d35d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-use-visual-studio-to-create-your-first-python-web-app"></a>Краткое руководство. Создание первого веб-приложения Python с помощью Visual Studio

В рамках этого краткого (на 5–10 минут) знакомства с возможностями интегрированной среды разработки (IDE) Visual Studio вы создадите простое веб-приложение Python. Установите Visual Studio бесплатно [здесь](http://www.visualstudio.com), если еще не сделали это.

## <a name="create-the-project"></a>Создание проекта

1. Откройте Visual Studio 2017.

1. В верхней строке меню выберите **Файл > Создать > Проект...**.

1. В левой области диалогового окна **Новый проект** разверните узел **Другие языки**, а затем выберите **Python**. В средней области выберите **Веб-проект**, присвойте проекту имя, например HelloPython, а затем нажмите кнопку **ОК**.

    Если вы не видите шаблон проекта Python, закройте диалоговое окно **Новый проект** и в верхней строке меню выберите **Сервис > Получить средства и компоненты...**, чтобы открыть Visual Studio Installer. Выберите рабочую нагрузку **Разработка на Python**, а затем элемент **Изменить**.

    ![Рабочая нагрузка разработки Python в установщике Visual Studio](../python/media/installation-python-workload.png)

1. Новый проект откроется в **обозревателе решений** в правой области. Проект пока пуст, так как он не содержит других файлов.

    ![Созданный пустой проект в обозревателе решений](media/quickstart-python-01-empty-project.png)

## <a name="install-the-falcon-library"></a>Установка библиотеки Falcon

Веб-приложения на Python почти всегда используют одну из множества доступных библиотек Python для обработки низкоуровневых процессов, таких как маршрутизация веб-запросов и формирование ответов. Рабочая нагрузка разработки на Python в Visual Studio предоставляет [различные шаблоны для веб-приложений](../python/template-web.md), которые основаны на библиотеках Bottle, Flask и Django.

Однако в этом кратком руководстве используется другая библиотека, [Falcon](https://falconframework.org/). Это позволит рассмотреть процедуру установки пакета и создания веб-приложения с нуля. Для простоты далее библиотека Falcon устанавливается в глобальной среде по умолчанию.

1. Разверните в проекте узел **Окружения Python**, чтобы увидеть среду по умолчанию для проекта.

    ![Среда по умолчанию в обозревателе решений](media/quickstart-python-02-default-environment.png)

1. Щелкните среду правой кнопкой мыши и выберите команду **Установить пакет Python...**. Эта команда открывает вкладку **Пакеты** в окне **Окружения Python**. В поле поиска введите "falcon" и выберите результат **"pip install falcon" from PyPI**. Подтвердите запросы на права администратора и наблюдайте за ходом выполнения в окне **Вывод** в Visual Studio.

    ![Установка библиотеки Falcon](media/quickstart-python-03-install-package.png)

1. После установки библиотека появится в среде в **обозревателе решений**. Это означает, что ее можно использовать в коде Python.

    ![Установленная библиотека Falcon](media/quickstart-python-04-package-installed.png)

Обратите внимание на то, что вместо установки библиотек в глобальной среде разработчики обычно создают "виртуальную среду", в которой устанавливаются библиотеки для определенного проекта. Многие шаблоны проектов Python в Visual Studio включают в себя файл `requirements.txt` со списком библиотек, от которых зависит шаблон. При создании проекта на основе одного из таких шаблонов автоматически создается виртуальная среда, в которой устанавливаются библиотеки. Дополнительные сведения см. в разделе [Виртуальные среды](../python/python-environments.md#virtual-environments) в статье "Среды Python".

## <a name="add-a-code-file"></a>Добавление файла кода

Теперь можно добавить немного кода на Python, чтобы реализовать простейшее веб-приложение.

1. В **обозревателе решений** щелкните правой кнопкой мыши проект и выберите пункты **Добавить > Новый элемент…**. В открывшемся диалоговом окне выберите элемент **Пустой файл Python**, присвойте файлу имя `hello.py` и нажмите кнопку **ОК**. Файл автоматически откроется в редакторе кода Visual Studio. (Как правило, команда **Добавить > Новый элемент...** — это отличный способ добавления различных файлов в проект, так как шаблоны элементов часто предоставляют полезный стандартный код.)

1. Скопируйте и вставьте или введите следующий код в файл `hello.py`:

    ```python
    import falcon
    api = falcon.API()

    # In Falcon, define a class for each resource; the on_get 
    # method then handles any GET requests.

    class HelloResource:
        def on_get(self, req, resp):
            resp.status = falcon.HTTP_200  # 200 is the default
            resp.body = "Hello, Python!"

    # Resources are represented by long-lived class instances
    hello = HelloResource()

    # Instruct Falcon to route / and /hello to the HelloResource
    api.add_route('/', hello)
    api.add_route('/hello', hello)

    if __name__ == "__main__":
        from wsgiref.simple_server import make_server

        # Run the web server on localhost:8080
        print("Starting web app server")
        srv = make_server('localhost', 8080, api)
        srv.serve_forever()
    ```

Дополнительные сведения о библиотеке Falcon см. в [кратком руководстве по Falcon](https://falcon.readthedocs.io/en/stable/user/quickstart.html) (falcon.readthedocs.io).

## <a name="run-the-application"></a>Запуск приложения

1. В **обозревателе решений** щелкните правой кнопкой мыши файл `hello.py` и выберите пункт **Задать как файл запуска**. Эта команда задает файл кода как запускаемый в Python при выполнении приложения.

1. В **обозревателе решений** щелкните проект "Hello Python" правой кнопкой мыши и выберите пункт **Свойства**. Затем перейдите на вкладку **Отладка** и присвойте свойству **Номер порта** значение `8080`. Благодаря этому среда Visual Studio будет запускать браузер, используя порт `localhost:8080`, а не произвольный порт.

1. Выберите команду **Отладка > Запуск без отладки** (CTRL+F5), чтобы сохранить изменения в файлах и запустить приложение.

1. Появится командное окно с сообщением "Запускается сервер веб-приложения", а затем в окне браузера откроется узел `localhost:8080`, и вы увидите сообщение "Hello, Python!" В командном окне также отображается запрос GET. (Если в командном окне отображается только интерактивная оболочка Python или если это окно появляется на экране и сразу исчезает, убедитесь в том, что файл `hello.py` был задан в качестве запускаемого в шаге 1 выше.)

1. Закройте командное окно, чтобы остановить приложение.

## <a name="next-steps"></a>Следующие шаги

Поздравляем с завершением этого краткого руководства, в котором вы получили основные сведения о работе с Python в интегрированной среде разработки Visual Studio. Чтобы перейти к более полному учебнику по работе с Python в Visual Studio, включая использование интерактивного окна, отладку, визуализацию данных и работу с Git, нажмите кнопку ниже.

> [!div class="nextstepaction"]
> [Учебник. Начало работы с Python в Visual Studio](../python/vs-tutorial-01-01.md)

- Сведения о [шаблонах веб-приложений Python в Visual Studio](../python/template-web.md)
- Дополнительные сведения об [интегрированной среде разработки Visual Studio](../ide/visual-studio-ide.md)
- Сведения об использовании [отладчика Visual Studio](../debugger/debugger-feature-tour.md)