---
title: Как использовать файл ресурсов для указания локализованных имен, свойств и разрешений | Документация Майкрософт
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], localize strings
- BDC [SharePoint development in Visual Studio], localize strings
- BDC [SharePoint development in Visual Studio], resource file
- Business Data Connectivity service [SharePoint development in Visual Studio], resource strings
- BDC [SharePoint development in Visual Studio], properties
- Business Data Connectivity service [SharePoint development in Visual Studio], properties
- Business Data Connectivity service [SharePoint development in Visual Studio], resource file
- BDC [SharePoint development in Visual Studio], resource strings
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a87cc8a3eb8f98ea19a87e93c37aae5303151ecf
ms.sourcegitcommit: f9e44f5ab6a1dfb56c945c9986730465e1adb6fc
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2020
ms.locfileid: "86015397"
---
# <a name="how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions"></a>Как использовать файл ресурсов для указания локализованных имен, свойств и разрешений
  С помощью файла ресурсов можно предоставлять локализованные имена, определять свойства и применять разрешения к объектам, определенным в модели подключения к бизнес-данным (BDC). Чтобы указать эти сведения, добавьте элемент **ресурса подключения к бизнес-данным** в проект, содержащий элемент **модели подключения к бизнес-данным** . Затем задайте имена, свойства и разрешения, редактируя XML-код для файла ресурсов.

### <a name="to-add-a-bdc-resource-file-to-a-sharepoint-project"></a>Добавление файла ресурсов BDC в проект SharePoint

1. В **Обозреватель решений**разверните папку для проекта SharePoint, а затем выберите папку, СОДЕРЖАЩУЮ модель BDC.

2. В строке меню выберите **проект**  >  **Добавить новый элемент**.

3. Разверните узел **SharePoint** , а затем выберите узел **2010** .

4. В диалоговом окне **Добавление нового элемента** выберите **элемент ресурса подключения к бизнес-данным**.

5. В поле **имя** укажите имя файла ресурсов, а затем нажмите кнопку **Добавить** .

     Файл ресурсов с расширением .bdcr добавляется в проект и открывается для редактирования.

6. Добавьте XML-код, чтобы определить локализованные имена, свойства и разрешения, которые необходимо применить к модели подключения к бизнес-данным.

     Дополнительные сведения об определении этих элементов см. в разделе [модель и файлы ресурсов](/previous-versions/office/developer/sharepoint-2010/aa674515(v=office.14)).

## <a name="see-also"></a>См. также раздел
- [Как добавить существующий файл модели BDC в проект SharePoint](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)
- [Создание модели подключения к бизнес-данным](../sharepoint/creating-a-business-data-connectivity-model.md)
- [Как создать модель BDC](../sharepoint/how-to-create-a-bdc-model.md)
- [Как включить пользовательскую сборку в компонент BDC](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)
- [Интеграция бизнес-данных в SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)
