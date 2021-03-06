---
title: Просмотр подключений SharePoint с помощью обозреватель сервера | Документация Майкрософт
ms.date: 02/02/2017
ms.topic: overview
f1_keywords:
- VS.SharePointTools.SharePointExplorer.SharePointConnection
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, browsing SharePoint sites
- SharePoint development in Visual Studio, SharePoint Connections
- SharePoint Connections [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: baf580ace98ab14032de1e9a3edf18af2b2cfee8
ms.sourcegitcommit: f9e44f5ab6a1dfb56c945c9986730465e1adb6fc
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2020
ms.locfileid: "86016354"
---
# <a name="browse-sharepoint-connections-by-using-server-explorer"></a>Просмотр подключений SharePoint с помощью обозреватель сервера
  Теперь можно просматривать локальные подключения SharePoint в **Обозреватель сервера**. Используя эту технику вы можете осуществлять переход по компонентам сайта SharePoint, расположенным в системе. Компоненты сайта SharePoint, такие как определения списков и типы содержимого, отображаются в узле с именем **подключения SharePoint** в древовидном представлении **Обозреватель сервера**. Чтобы отобразить **Обозреватель сервера**, в строке меню выберите **вид**  >  **Обозреватель сервера**. В древовидном представлении можно не только просматривать компоненты сайта SharePoint, но и использовать контекстное меню для удаления элементов, просмотра их свойств и обновления древовидного представления.

> [!IMPORTANT]
> Просматривать сайт SharePoint может только администратор коллекции сайтов SharePoint, запустивший Visual Studio в качестве пользователя с правами системного администратора. В противном случае сайт отображается в **Обозреватель сервера**, но нельзя развернуть его узел. Чтобы проверить, являетесь ли вы администратором семейства веб-сайтов, откройте сайт в веб-браузере, откройте меню **действия сайта** , выберите **разрешения сайта**, а затем на странице **разрешения: сайт группы** выберите команду **Администраторы семейства веб-сайтов** в группе **Управление** на ленте. Ваше имя появится в текстовом поле, если вы являетесь администратором семейства веб-сайтов. Если команда **Администраторы семейства узлов** не отображается в группе Управление на ленте, вы не являетесь администратором семейства веб-сайтов, и вам необходимо получить соответствующие разрешения у администратора сайта.

## <a name="server-explorer-nodes"></a>Узлы обозреватель сервера
 Каждый компонент сайта SharePoint представлен узлом в древовидном представлении **Обозреватель сервера** в разделе **подключения SharePoint**. Например, сайты SharePoint по умолчанию включают тип содержимого «обсуждение», который представляет тип обсуждения, отображаемый на странице « **обсуждения** » сайта SharePoint. Тип содержимого обсуждения содержит несколько полей. Чтобы просмотреть эти поля в **Обозреватель сервера**, разверните узел **ContentTypes** , а затем узел **обсуждения** . Под ним находятся несколько узлов полей, например текст, тема обсуждения и заголовок.

## <a name="node-shortcut-menu-commands"></a>Команды контекстного меню узла
 Для каждого узла имеется контекстное меню, доступ к которому можно получить, щелкнув правой кнопкой мыши узел или выбрав его, а затем нажав клавиши **SHIFT** + **F10** . К командам узла могут относиться следующие:

|Имя команды|Описание|
|------------------|-----------------|
|Обновить|Обновляет представление в виде дерева, отражая все изменения, которые могли произойти с момента последнего отображения узла.|
|Удалить|Удаляет выбранный узел из представления в виде дерева. **Примечание.**  Эта команда доступна только для подключений SharePoint, перечисленных в узле " **подключения SharePoint** ".|
|Свойства|Отображает доступные свойства для выбранного узла в окне **Свойства** . Свойства доступны только для чтения, а не для каждого узла есть связанные с ним свойства.|
|Добавление подключения|Позволяет указать сайт SharePoint, который требуется просмотреть. Доступно на узле **подключения SharePoint** и на узлах дочерних сайтов.|
|Просмотреть в браузере|Отображает выбранный список в веб-браузере. Эта команда доступна в некоторых списках в узле **списки** , который содержится в **списках и библиотеках**.|

## <a name="related-topics"></a>См. также

|Заголовок|Описание|
|-----------|-----------------|
|[Как добавлять или удалять подключения SharePoint](../sharepoint/how-to-add-or-remove-sharepoint-connections.md)|Описание действий, необходимых для добавления нового сайта SharePoint в узел " **подключения SharePoint** " в **Обозреватель сервера**.|

## <a name="see-also"></a>См. также раздел
- [Разработка решений SharePoint](../sharepoint/developing-sharepoint-solutions.md)
