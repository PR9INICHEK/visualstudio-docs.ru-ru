---
title: Обновление MDF-файлов
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- SQL Server Express
- SQL Server LocalDB
- LocalDB
- SQLEXPRESS
- upgrading SQLExpress to SQLExpress
- upgrading to LocalDB
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: d35611dcc7b6067cf6d6166aff521ef291b8dfcd
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85281127"
---
# <a name="upgrade-mdf-files"></a>Обновление MDF-файлов

В этом разделе описываются варианты обновления файла базы данных (*MDF*) после установки более новой версии Visual Studio. Он содержит инструкции по следующим задачам.

- Обновление файла базы данных для использования более новой версии SQL Server Express LocalDB

- Обновление файла базы данных для использования более новой версии SQL Server Express

- Работа с файлом базы данных в Visual Studio, сохраняя совместимость с более ранней версией SQL Server Express или LocalDB

- Сделать SQL Server Express ядром СУБД по умолчанию

Visual Studio можно использовать для открытия проекта, содержащего файл базы данных (*MDF*), который был создан с помощью более ранней версии SQL Server Express или LocalDB. Однако, чтобы продолжить разработку проекта в Visual Studio, необходимо, чтобы эта версия SQL Server Express или LocalDB была установлена на том же компьютере, что и Visual Studio, или необходимо обновить файл базы данных. Если обновить файл базы данных, вы не сможете получить к нему доступ с помощью более старых версий SQL Server Express или LocalDB.

Также может появиться запрос на обновление файла базы данных, созданного с помощью более ранней версии SQL Server Express или LocalDB, если версия файла несовместима с экземпляром SQL Server Express или LocalDB, установленным в настоящий момент. Чтобы устранить эту проблему, Visual Studio предложит вам обновить файл.

> [!IMPORTANT]
> Рекомендуется создать резервную копию файла базы данных перед обновлением.

> [!WARNING]
> При обновлении *MDF* -файла, созданного в LocalDB 2014 (V12) 32 bit до LocalDB 2016 (V13) или более поздней версии, вы не сможете открыть этот файл еще раз 32 в версии LocalDB, которая не будет доступна.

Перед обновлением базы данных учитывайте следующие критерии.

- Не обновляйте, если вы хотите работать с проектом в более старой и более поздней версии Visual Studio.

- Не обновляйте, если приложение будет использоваться в средах, использующих SQL Server Express, а не LocalDB.

- Не обновляйте, если приложение использует удаленные соединения, так как LocalDB не принимает их.

- Не обновляйте приложение, если оно зависит от службы IIS (IIS).

- Если вы хотите тестировать приложения базы данных в изолированной среде, но не хотите администрировать базу данных, рассмотрите возможность обновления.

### <a name="to-upgrade-a-database-file-to-use-the-localdb-version"></a>Обновление файла базы данных для использования версии LocalDB

1. В **Обозреватель сервера**нажмите кнопку **подключиться к базе данных** .

2. В диалоговом окне **Добавление соединения** укажите следующие сведения.

    - **Источник данных**:`Microsoft SQL Server (SqlClient)`

    - **Имя сервера**:

        - Чтобы использовать версию по умолчанию: `(localdb)\MSSQLLocalDB` .  В зависимости от того, какая версия Visual Studio установлена и когда был создан первый экземпляр LocalDB, будет указываться либо ProjectV12, либо ProjectV13. Узел **MSSQLLocalDB** в **Обозреватель объектов SQL Server** показывает, на какую версию указывает.

        - Для использования конкретной версии: `(localdb)\ProjectsV12` или `(localdb)\ProjectsV13` , где V12 — LocalDB 2014, а V13 — LocalDB 2016.

    - **Присоединить файл базы данных**: физический путь к первичному *MDF* -файлу.

    - **Логическое имя**: имя, которое вы хотите использовать с файлом.

3. Нажмите кнопку **OK**.

4. При появлении запроса нажмите кнопку **Да** , чтобы обновить файл.

    База данных обновлена, подключена к ядру СУБД LocalDB и больше не совместима с более старой версией LocalDB.

Можно также изменить соединение SQL Server Express, чтобы использовать LocalDB, открыв контекстное меню подключения и выбрав пункт **изменить подключение**. В диалоговом окне **изменение соединения** измените имя сервера на `(LocalDB)\MSSQLLocalDB` . В диалоговом окне **Дополнительные свойства** убедитесь, что для параметра **Пользовательский экземпляр** задано значение **false**.

### <a name="to-upgrade-a-database-file-to-use-the-sql-server-express-version"></a>Обновление файла базы данных для использования SQL Server Express версии

1. В контекстном меню подключения к базе данных выберите **изменить подключение**.

2. В диалоговом окне **изменение соединения** нажмите кнопку **Дополнительно** .

3. В диалоговом окне **Дополнительные свойства** нажмите кнопку **ОК** , не изменяя имя сервера.

    Файл базы данных обновляется в соответствии с текущей версией SQL Server Express.

### <a name="to-work-with-the-database-in-visual-studio-but-retain-compatibility-with-sql-server-express"></a>Для работы с базой данных в Visual Studio, сохраняя совместимость с SQL Server Express

- В Visual Studio откройте проект, не обновляя его.

  - Чтобы запустить проект, нажмите клавишу **F5** .

  - Чтобы изменить базу данных, откройте *MDF* файл в **Обозреватель решений**и разверните узел в **Обозреватель сервера** для работы с базой данных.

### <a name="to-make-sql-server-express-the-default-database-engine"></a>Создание SQL Server Express ядра СУБД по умолчанию

1. В строке меню выберите **Сервис**  >  **Параметры**.

2. В диалоговом окне **Параметры** разверните узел Параметры **инструментов базы данных** и выберите подключения к **данным**.

3. В текстовом поле **SQL Server имя экземпляра** укажите имя экземпляра SQL Server Express или LocalDB, который требуется использовать. Если экземпляр не имеет имя, укажите `.\SQLEXPRESS or (LocalDB)\MSSQLLocalDB` .

4. Нажмите кнопку **OK**.

    SQL Server Express будет ядром СУБД по умолчанию для приложений.

## <a name="see-also"></a>См. также

- [Доступ к данным в Visual Studio](accessing-data-in-visual-studio.md)
