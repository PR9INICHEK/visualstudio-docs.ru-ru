---
title: Средства Visual Studio для контейнеров с ASP.NET Core и React.js
author: ghogen
description: Сведения об использовании средств Visual Studio для контейнеров и Docker для Windows
ms.author: ghogen
ms.date: 05/14/2020
ms.technology: vs-azure
ms.topic: quickstart
ms.openlocfilehash: f7dfc0aa1346c4e888f64f7cd8f23add3056c070
ms.sourcegitcommit: d20ce855461c240ac5eee0fcfe373f166b4a04a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "84182796"
---
# <a name="quickstart-use-docker-with-a-react-single-page-app-in-visual-studio"></a>Краткое руководство. Использование Docker с одностраничным приложением React в Visual Studio

В Visual Studio можно легко собирать, отлаживать и запускать контейнерные приложения ASP.NET Core, в том числе с кодом JavaScript на стороне клиента (например, одностраничное приложение React.js), и публиковать их в Реестре контейнеров Azure (ACR), Docker Hub, Службе приложений Azure или вашем реестре контейнеров. В этой статье мы опубликуем приложение в ACR.

## <a name="prerequisites"></a>Предварительные требования

::: moniker range="vs-2017"
* [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
* [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) с рабочей нагрузкой **Веб-разработка**, **Средства Azure** и (или) **Кроссплатформенная разработка .NET Core**
* Для публикации в Реестр контейнеров Azure требуется подписка Azure. [Зарегистрируйтесь для получения бесплатной пробной версии](https://azure.microsoft.com/offers/ms-azr-0044p/).
* [Node.js](https://nodejs.org/en/download/)
* Для контейнеров Windows, Windows 10 версии 1903 или более поздней, используйте образы "Docker", о которых идет речь в этой статье.
::: moniker-end
::: moniker range=">=vs-2019"
* [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads) с рабочей нагрузкой **Веб-разработка**, **Средства Azure** и (или) **Кроссплатформенная разработка .NET Core**.
* [Средства разработки .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2) для разработки с использованием .NET Core 2.2.
* Для публикации в Реестр контейнеров Azure требуется подписка Azure. [Зарегистрируйтесь для получения бесплатной пробной версии](https://azure.microsoft.com/offers/ms-azr-0044p/).
* [Node.js](https://nodejs.org/en/download/)
* Для контейнеров Windows, Windows 10 версии 1903 или более поздней, используйте образы "Docker", о которых идет речь в этой статье.
::: moniker-end

## <a name="installation-and-setup"></a>Установка и настройка

Чтобы установить Docker, сначала ознакомьтесь с разделом [Docker для Windows: что следует знать перед установкой](https://docs.docker.com/docker-for-windows/install/#what-to-know-before-you-install). Затем установите [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows).

## <a name="create-a-project-and-add-docker-support"></a>Создание проекта и добавление поддержки Docker

::: moniker range="vs-2017"
1. Создайте проект, используя шаблон **Веб-приложение ASP.NET Core**.
1. Выберите **React.js**. Вы не можете выбрать **Включить поддержку Docker**, но не беспокойтесь, эту поддержку можно добавить после создания проекта.

   ![Снимок экрана: новый проект React.js](media/container-tools-react/vs2017/new-react-project.png)

1. Щелкните правой кнопкой мыши узел проекта и выберите **Добавить** > **Поддержка Docker**, чтобы добавить файл Dockerfile в проект.

   ![Добавление поддержки Docker](media/container-tools-react/vs2017/add-docker-support.png)

1. Выберите тип контейнера и нажмите **OK**.
::: moniker-end
::: moniker range=">=vs-2019"
1. Создайте проект, используя шаблон **Веб-приложение ASP.NET Core**.
1. Выберите **React.js** и нажмите кнопку **Создать**. Вы не можете выбрать **Включить поддержку Docker**, но не беспокойтесь, эту поддержку можно добавить позже.

   ![Снимок экрана: новый проект React.js](media/container-tools-react/vs2019/new-react-project.png)

1. Щелкните правой кнопкой мыши узел проекта и выберите **Добавить** > **Поддержка Docker**, чтобы добавить файл Dockerfile в проект.

   ![Добавление поддержки Docker](media/container-tools-react/vs2017/add-docker-support.png)

1. Выберите тип контейнера.
::: moniker-end

Следующий шаг зависит от того, используете ли вы контейнеры Linux или контейнеры Windows.

## <a name="modify-the-dockerfile-linux-containers"></a>Изменение файла Dockerfile (контейнеры Linux)

*Dockerfile* с инструкциями по созданию окончательного образа Docker создается в проекте. См. [справочник по Dockerfile](https://docs.docker.com/engine/reference/builder/) для получения сведений о других доступных в нем командах.

Откройте *Dockerfile* в проекте и добавьте приведенные ниже строки для установки Node.js 10.x в контейнере. Чтобы добавить файлы установки диспетчера пакетов Node.js *npm.exe* в базовый образ, обязательно добавьте следующие строки в первый раздел, а также в раздел `build`.

```Dockerfile
RUN curl -sL https://deb.nodesource.com/setup_10.x |  bash -
RUN apt-get install -y nodejs
```

Теперь файл *Dockerfile* должен выглядеть следующим образом:

```Dockerfile
FROM microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim AS base
WORKDIR /app
EXPOSE 80 
EXPOSE 443
RUN curl -sL https://deb.nodesource.com/setup_10.x |  bash -
RUN apt-get install -y nodejs

FROM microsoft/dotnet:2.2-sdk-stretch AS build
RUN curl -sL https://deb.nodesource.com/setup_10.x |  bash -
RUN apt-get install -y nodejs
WORKDIR /src
COPY ["WebApplication37/WebApplication37.csproj", "WebApplication37/"]
RUN dotnet restore "WebApplication37/WebApplication37.csproj"
COPY . .
WORKDIR "/src/WebApplication37"
RUN dotnet build "WebApplication37.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "WebApplication37.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication37.dll"]
```

Предыдущий *Dockerfile* основан на образе [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) и включает в себя инструкции по изменению базового образа путем сборки проекта и добавления его в контейнер.

Если в диалоговом окне создания проекта установлен флажок **Configure for HTTP** (Настроить для трафика HTTPS), *Dockerfile* предоставляет два порта. Один порт используется для трафика HTTP, другой — для HTTPS. Если флажок не установлен, для трафика HTTP предоставляется один порт (80).

## <a name="modify-the-dockerfile-windows-containers"></a>Изменение файла "Dockerfile" (контейнеры Windows)

Откройте файл проекта двойным щелчком на узле проекта и обновите файл проекта (*.csproj), добавив следующее свойство в качестве дочернего элемента `<PropertyGroup>`:

   ```xml
    <DockerfileFastModeStage>base</DockerfileFastModeStage>
   ```

Обновите файл "Dockerfile", добавив следующие строки. Это скопирует узел и npm в контейнер.

   1. Добавьте ``# escape=` `` в первую строку файла "Dockerfile".
   1. Добавьте следующие строки перед `FROM … base`.

      ```Dockerfile
      FROM mcr.microsoft.com/powershell:nanoserver-1903 AS downloadnodejs
      SHELL ["pwsh", "-Command", "$ErrorActionPreference = 'Stop';$ProgressPreference='silentlyContinue';"]
      RUN Invoke-WebRequest -OutFile nodejs.zip -UseBasicParsing "https://nodejs.org/dist/v10.16.3/node-v10.16.3-win-x64.zip"; `
      Expand-Archive nodejs.zip -DestinationPath C:\; `
      Rename-Item "C:\node-v10.16.3-win-x64" c:\nodejs
      ```

   1. Добавьте следующую строку до и после `FROM … build`.

      ```Dockerfile
      COPY --from=downloadnodejs C:\nodejs\ C:\Windows\system32\
      ```

   1. Теперь весь файл "Dockerfile" должен выглядеть примерно так:

      ```Dockerfile
      # escape=`
      #Depending on the operating system of the host machines(s) that will build or run the containers, the image specified in the FROM statement may need to be changed.
      #For more information, please see https://aka.ms/containercompat
      FROM mcr.microsoft.com/powershell:nanoserver-1903 AS downloadnodejs
      RUN mkdir -p C:\nodejsfolder
      WORKDIR C:\nodejsfolder
      SHELL ["pwsh", "-Command", "$ErrorActionPreference = 'Stop';$ProgressPreference='silentlyContinue';"]
      RUN Invoke-WebRequest -OutFile nodejs.zip -UseBasicParsing "https://nodejs.org/dist/v10.16.3/node-v10.16.3-win-x64.zip"; `
      Expand-Archive nodejs.zip -DestinationPath C:\; `
      Rename-Item "C:\node-v10.16.3-win-x64" c:\nodejs

      FROM mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1903 AS base
      WORKDIR /app
      EXPOSE 80
      EXPOSE 443
      COPY --from=downloadnodejs C:\nodejs\ C:\Windows\system32\

      FROM mcr.microsoft.com/dotnet/core/sdk:2.2-nanoserver-1903 AS build
      COPY --from=downloadnodejs C:\nodejs\ C:\Windows\system32\
      WORKDIR /src
      COPY ["WebApplication7/WebApplication37.csproj", "WebApplication37/"]
      RUN dotnet restore "WebApplication7/WebApplication7.csproj"
      COPY . .
      WORKDIR "/src/WebApplication37"
      RUN dotnet build "WebApplication37.csproj" -c Release -o /app/build

      FROM build AS publish
      RUN dotnet publish "WebApplication37.csproj" -c Release -o /app/publish

      FROM base AS final
      WORKDIR /app
      COPY --from=publish /app/publish .
      ENTRYPOINT ["dotnet", "WebApplication37.dll"]
      ```

1. Обновите файл .dockerignore, удалив `**/bin`.

## <a name="debug"></a>Отладка

Выберите пункт **Docker** в раскрывающемся списке отладки на панели инструментов, чтобы начать отладку приложения. Может появиться сообщение с запросом о доверии сертификату. Выберите доверие сертификату, чтобы продолжить.  При первой сборке Docker загружает базовые образы, так что это может занять немного больше времени.

В параметре **Инструменты контейнера** в окне **Вывод** показано, какие действия выполняются. Вы должны увидеть действия по установке, связанные с *npm.exe*.

В браузере отображается домашняя страница приложения.

::: moniker range="vs-2017"
   ![Снимок экрана с запущенным приложением](media/container-tools-react/vs2017/running-app.png)
::: moniker-end
::: moniker range=">=vs-2019"
   ![Снимок экрана с запущенным приложением](media/container-tools-react/vs2019/running-app.png)
::: moniker-end

Попробуйте перейти на страницу *счетчика* и протестировать код на стороне клиента для счетчика, нажав кнопку **Приращение**.

Откройте **консоль диспетчера пакетов** в меню **Сервис** > Диспетчер пакетов NuGet, **Консоль диспетчера пакетов**.

Итоговый образ Docker приложения помечается как *dev*. Образ основан на теге *2.2-aspnetcore-runtime* базового образа *microsoft/dotnet*. Выполните команду `docker images` в окне **Консоль диспетчера пакетов** (PMC). На компьютере отобразятся следующие образы:

```console
REPOSITORY        TAG                     IMAGE ID      CREATED         SIZE
webapplication37  dev                     d72ce0f1dfe7  30 seconds ago  255MB
microsoft/dotnet  2.2-aspnetcore-runtime  fcc3887985bb  6 days ago      255MB
```

> [!NOTE]
> Образ **разработки** не содержит двоичные файлы приложения и другое содержимое, так как конфигурации **отладки** используют подключение томов для обеспечения итеративного редактирования и отладки. Чтобы создать рабочий образ со всем содержимым, используйте конфигурацию **выпуска**.

Выполните команду `docker ps` в PMC. Обратите внимание, что приложение выполняется с помощью контейнера:

```console
CONTAINER ID        IMAGE                  COMMAND               CREATED             STATUS              PORTS                                           NAMES
cf5d2ef5f19a        webapplication37:dev   "tail -f /dev/null"   2 minutes ago       Up 2 minutes        0.0.0.0:52036->80/tcp, 0.0.0.0:44342->443/tcp   priceless_cartwright
```

## <a name="publish-docker-images"></a>Публикация образов Docker

После завершения цикла разработки и отладки приложения можно создать рабочий образ приложения.

1. Выберите в раскрывающемся списке конфигурации значение **Выпуск** и выполните сборку приложения.
1. В **обозревателе решений** щелкните правой кнопкой проект и выберите **Опубликовать**.
1. В диалоговом окне целевой публикации выберите вкладку **Реестр контейнеров**.
1. Выберите **Создать реестр контейнеров Azure** и щелкните **Опубликовать**.
1. Заполните нужные значения в окне **Создать новый реестр контейнеров Azure**.

    | Параметр      | Рекомендуемое значение  | Описание                                |
    | ------------ |  ------- | -------------------------------------------------- |
    | **DNS-префикс** | Глобально уникальное имя | Имя, которое однозначно идентифицирует реестр контейнеров. |
    | **Подписка** | Выберите свою подписку | Подписка Azure, которую нужно использовать. |
    | **[Группа ресурсов](/azure/azure-resource-manager/resource-group-overview)** | myResourceGroup |  Имя группы ресурсов, в которой создается реестр контейнеров. Чтобы создать группу ресурсов, выберите **Создать**.|
    | **[SKU](/azure/container-registry/container-registry-skus)** | Стандартный | Уровень обслуживания в реестре контейнеров  |
    | **Расположение реестра** | Расположение рядом с вами | Выберите расположение в ближайшем [регионе](https://azure.microsoft.com/regions/) или в регионе, расположенном рядом с другими службами, которые будут использовать реестр контейнеров. |

    ![Диалоговое окно "Создание реестра контейнеров Azure" Visual Studio][0]

1. Нажмите кнопку **Создать**.

   ![Снимок экрана с сообщением об успешной публикации](media/container-tools/publish-succeeded.png)

## <a name="next-steps"></a>Следующие шаги

Теперь можно извлечь контейнер из реестра в любой узел, поддерживающий работу образов Docker, например [Экземпляры контейнеров Azure](/azure/container-instances/container-instances-tutorial-deploy-app).

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Разработка с помощью контейнеров в Visual Studio](/visualstudio/containers)
* [Устранение неполадок при разработке с Docker в Visual Studio](troubleshooting-docker-errors.md)
* [Репозиторий GitHub со средствами Visual Studio для контейнеров](https://github.com/Microsoft/DockerTools)

::: moniker range="vs-2017"
[0]:media/hosting-web-apps-in-docker/vs-acr-provisioning-dialog.png
::: moniker-end
::: moniker range=">=vs-2019"
[0]:media/hosting-web-apps-in-docker/vs-acr-provisioning-dialog-2019.png
::: moniker-end