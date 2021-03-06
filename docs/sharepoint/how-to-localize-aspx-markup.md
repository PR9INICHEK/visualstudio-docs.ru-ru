---
title: Как локализовать разметку ASPX | Документация Майкрософт
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- localizing XML [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, localizing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 63bd8ee614a78752069002820689a2cc6c0be783
ms.sourcegitcommit: f9e44f5ab6a1dfb56c945c9986730465e1adb6fc
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2020
ms.locfileid: "86016282"
---
# <a name="how-to-localize-aspx-markup"></a>Как локализовать разметку ASPX
  [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)]страницы (. aspx) обычно используют жестко запрограммированные строковые значения. Для локализации этих строк замените их выражениями, которые ссылаются на локализованные ресурсы.

## <a name="localize-aspx-markup"></a>Локализация разметки ASPX

#### <a name="to-localize-aspx-markup"></a>Локализация разметки ASPX

1. Добавьте отдельные файлы ресурсов: один для языка по умолчанию и по одному для каждого локализованного языка.

     При локализации только разметки, а не кода, добавьте глобальный файл ресурсов проекта. При локализации кода и разметки добавьте элемент проекта файла ресурсов.

    1. Чтобы добавить глобальный файл ресурсов, в **Обозреватель решений**откройте контекстное меню для элемента проекта SharePoint и выберите команду **Добавить**  >  **новый элемент**. В узле SharePoint **2010** выберите шаблон **файл глобальных ресурсов** .

    2. Чтобы добавить файл ресурсов, в **Обозреватель решений**откройте контекстное меню для элемента проекта SharePoint и выберите команду **Добавить**  >  **новый элемент**. В узле **Visual Basic** или **Visual C#** выберите шаблон **файл ресурсов** .

    > [!NOTE]
    > Не забудьте добавить файлы ресурсов в элемент проекта SharePoint, чтобы включить свойство тип развертывания. Это свойство требуется далее в этой процедуре. Если в решении отсутствует элемент проекта SharePoint, можно добавить пустой проект SharePoint и удалить файл *Elements.xml* по умолчанию.

2. Укажите для файла ресурсов языка по умолчанию имя, к которому добавляется расширение *RESX* , например мяппресаурцес. resx. Используйте одно и то же базовое имя для каждого локализованного файла ресурсов, но добавьте язык и региональные параметры [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)] . Например, назовите немецкий локализованный ресурс *MyAppResources.de-de. resx*.

3. Измените значение свойства **тип развертывания** каждого файла ресурсов на **AppGlobalResource** , чтобы они были развернуты в папке App_GlobalResources сервера.

4. Если вы используете ресурсы для локализации кода в дополнение к разметке ASPX, оставьте значение свойства **действие сборки** каждого файла как **внедренный ресурс**. Если вы используете файлы ресурсов только для локализации разметки, при необходимости можно изменить значение свойства для файлов на **содержимое**. Дополнительные сведения см. в разделе [локализация решений SharePoint](../sharepoint/localizing-sharepoint-solutions.md).

5. Откройте каждый файл ресурсов и добавьте локализованные строки, используя одинаковые идентификаторы строк в каждом файле.

6. В [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] разметке для страницы или элемента управления ASPX замените жестко запрограммированные строки значениями, которые используют следующий формат:

    ```aspx-csharp
    <%$Resources:Resource File Name, String ID%>
    ```

     Например, чтобы локализовать текст для элемента управления Label на странице приложения, необходимо изменить:

    ```aspx-csharp
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">
    <asp:Label ID="lbl" runat="server" Text="Label text"></asp:Label>
    </asp:Content>
    ```

     значение

    ```aspx-csharp
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">
    <asp:Label ID="lbl" runat="server" Text="<%$Resources:MyAppResources,String1%>"></asp:Label>
    </asp:Content>
    ```

7. Нажмите клавишу **F5** , чтобы создать и запустить приложение.

8. В SharePoint измените язык интерфейса по умолчанию.

     Локализованные строки появятся в приложении. Для вывода локализованных ресурсов на сервере SharePoint должен быть установлен языковой пакет, соответствующий языку и региональным параметрам файла ресурсов.

## <a name="see-also"></a>См. также раздел
- [Локализация решений SharePoint](../sharepoint/localizing-sharepoint-solutions.md)
- [Практические руководства. Локализация компонента](../sharepoint/how-to-localize-a-feature.md)
- [Как добавить файл ресурсов](../sharepoint/how-to-add-a-resource-file.md)
- [Практические руководства. Локализация кода](../sharepoint/how-to-localize-code.md)
