---
title: Расширение закодированных тестов пользовательского интерфейса и записей действий
ms.date: 11/04/2016
ms.topic: how-to
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: 0f396027025572d953d5ea0265d122e6954c3ad7
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85288578"
---
# <a name="extend-coded-ui-tests-and-action-recordings"></a>Расширение закодированных тестов пользовательского интерфейса и записей действий

Платформа тестирования для закодированных пользовательских интерфейсов и записей действий поддерживает не все пользовательские интерфейсы. Возможно, пользовательский интерфейс, который вы хотите протестировать, не поддерживается. Например, невозможно напрямую создать закодированный тест пользовательского интерфейса или запись действия для электронной таблицы Microsoft Excel. Тем не менее можно создать собственное расширение для платформы закодированных тестов пользовательского интерфейса, которое будет поддерживать определенный пользовательский интерфейс, используя расширяемость такой платформы.

![Архитектура теста пользовательского интерфейса](../test/media/ui_testarch.png)

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

## <a name="sample-extension-to-test-microsoft-excel"></a>Пример расширения для тестирования Microsoft Excel

Эта [публикация блога](https://blogs.msdn.microsoft.com/gautamg/2010/01/05/3-introducing-sample-excel-extension/) содержит ссылку на [пример расширения](https://msdnshared.blob.core.windows.net/media/MSDNBlogsFS/prod.evol.blogs.msdn.com/CommunityServer.Components.PostAttachments/00/09/94/38/24/ExcelPluginSample.zip) для платформы закодированных тестов пользовательского интерфейса. Вы также можете просмотреть всю [серию публикаций блога, посвященную расширяемости закодированных тестов пользовательского интерфейса](https://blogs.msdn.microsoft.com/gautamg/2010/01/05/series-on-coded-ui-test-extensibility/).

> [!NOTE]
> Образец предназначен для использования с Microsoft Excel 2010. Он может поддерживать (или не поддерживать) другие версии Microsoft Excel.

## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>
- [UITestActionFilter](/previous-versions/visualstudio/visual-studio-2012/dd985757(v=vs.110))
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [Использование автоматизации пользовательского интерфейса для тестирования кода](../test/use-ui-automation-to-test-your-code.md)
- [Рекомендации по выполнению закодированных тестов пользовательского интерфейса](../test/best-practices-for-coded-ui-tests.md)
- [Поддерживаемые конфигурации и платформы для закодированных тестов пользовательского интерфейса и записей действий](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
