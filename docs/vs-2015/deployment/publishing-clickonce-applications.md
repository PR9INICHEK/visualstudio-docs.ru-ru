---
title: Публикация приложений ClickOnce | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.Options
- Microsoft.VisualStudio.Publish.ClickOnceProvider.PublishWizard.Help
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- ClickOnce applications, publishing
- applications [Visual Studio], ClickOnce deployment
- deploying applications [ClickOnce], publishing ClickOnce applications
ms.assetid: eb6dfe79-f54c-4331-8e36-073688e70973
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 209aac56f4648554ce619cbe31cef19a8ab1fed7
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85531798"
---
# <a name="publishing-clickonce-applications"></a>Публикация ClickOnce-приложений
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

При первой публикации приложения [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] установка свойств публикации выполняется с помощью мастера публикации. В мастере доступно только несколько свойств. Для всех остальных свойств устанавливаются значения по умолчанию.  
  
 Последующие изменения свойств публикации выполняются на странице **Публикация** в **конструкторе проектов**.  
  
## <a name="publish-wizard"></a>мастер публикации  
 Мастер публикации можно использовать для настройки основных параметров для публикации приложения. В число этих свойств входят следующие.  
  
- Расположение папки публикации — место, куда Visual Studio будет копировать файлы (локальный компьютер, общий сетевой файловый ресурс, FTP-сервер или веб-узел)  
  
- Расположение папки установки — место, откуда пользователи будут выполнять установку (общий сетевой файловый ресурс, FTP-сервер, веб-узел, компакт- или DVD-диск)  
  
- Доступность в оперативном или автономном режиме — возможность конечного пользователя обращаться к приложению при наличии или отсутствии подключения к сети  
  
- Частота обновления — периодичность проверки на наличие новых обновлений.  
  
  Дополнительные сведения см. в разделе [инструкции. Публикация приложения ClickOnce с помощью мастера публикации](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
## <a name="publish-page"></a>Страница "Публикация"  
 Страница **Публикация****конструктора проектов** используется для настройки свойств развертывания ClickOnce. В следующей таблице приводится список разделов.  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Как указать, где Visual Studio копирует файлы](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)|Содержит сведения о выборе расположения, в котором Visual Studio размещает файлы приложения и манифесты.|  
|[Как указать расположение, из которого будут устанавливаться конечные пользователи.](../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)|Содержит сведения о выборе расположения для загрузки и установки приложения пользователями.|  
|[Как указать режим установки ClickOnce: автономный или оперативный](../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)|Содержит сведения о настройке режима доступности приложения — оперативного или автономного.|  
|[Практическое руководство. Установка версии публикации приложения ClickOnce](../deployment/how-to-set-the-clickonce-publish-version.md)|Содержит сведения об установке свойства **Версия публикации** для ClickOnce, которое определяет, будет ли публикуемое приложение рассматриваться как обновление.|  
|[Как автоматически увеличивать версию публикации ClickOnce](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)|Содержит сведения об автоматическом увеличении номера редакции свойства **PublishVersion** при каждой публикации приложения.|  
  
 Дополнительные сведения см. в разделе [Публикация страницы в конструкторе проектов](../ide/reference/publish-page-project-designer.md) .  
  
### <a name="application-files-dialog-box"></a>Диалоговое окно "Файлы приложения"  
 В этом диалоговом окне можно указать, способ категоризации файлов проекта для публикации, динамической загрузки и обновления. В нем находится таблица со списком файлов проекта, которые не исключены по умолчанию или имеют группу загрузки.  
  
 Чтобы исключить файлы, пометьте файлы как файлы данных или необходимые компоненты и создайте группы файлов для условной установки в пользовательском интерфейсе Visual Studio, см. раздел [как указать, какие файлы публикуются с помощью ClickOnce](../deployment/how-to-specify-which-files-are-published-by-clickonce.md). Можно также пометить файлы данных с помощью средства Mage.exe. Дополнительные сведения см. в разделе [инструкции. Включение файла данных в приложение ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
### <a name="prerequisites-dialog-box"></a>Диалоговое окно «Необходимые компоненты»  
 В этом диалоговом окне определяются установленные необходимые компоненты, а также способ их установки. Дополнительные сведения см. [в разделе инструкции. Установка необходимых компонентов с помощью приложения ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md) и [необходимых компонентов](../ide/reference/prerequisites-dialog-box.md).  
  
### <a name="application-updates-dialog-box"></a>Диалоговое окно "Обновления приложения"  
 В этом диалоговом окне определяется способ проверки установкой приложения наличия обновлений. Дополнительные сведения см. [в разделе руководство. Управление обновлениями для приложения ClickOnce](../deployment/how-to-manage-updates-for-a-clickonce-application.md).  
  
### <a name="publish-options-dialog-box"></a>Диалоговое окно "Параметры публикации"  
 В диалоговом окне "Параметры публикации" задаются параметры развертывания приложения.  
  
|Заголовок|Описание|
|-|-|  
|[Как изменить язык публикации для приложения ClickOnce](../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)|Содержит сведения об указании языка и региональных параметров, соответствующих локализованной версии.|  
|[Как указать имя меню "Пуск" для приложения ClickOnce](../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)|Содержит сведения об изменении отображаемого имени для приложения ClickOnce.|  
|[Практическое руководство. Задание ссылки на веб-страницу технической поддержки](../deployment/how-to-specify-a-link-for-technical-support.md)|Содержит сведения о задании свойства **URL-адрес службы поддержки**, которое определяет веб-страницу или общий ресурс, где пользователи могут получить сведения о приложении.|  
|[Как указать URL-адрес поддержки для отдельных необходимых компонентов в развертывании ClickOnce](../deployment/how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment.md)|Демонстрирует процесс изменения манифеста приложения вручную для включения отдельных URL-адресов службы поддержки для каждого необходимого предварительного условия.|  
|[Как указать страницу публикации для приложения ClickOnce](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)|Содержит сведения о создании и публикации веб-страницы по умолчанию (publish.htm) вместе с приложением.|  
|[Как настроить веб-страницу ClickOnce по умолчанию](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)|Содержит сведения о настройке веб-страницы, которая автоматически создается и публикуется вместе с приложением.|  
|[Практическое руководство. Включение автозапуска при установке с компакт-диска](../deployment/how-to-enable-autostart-for-cd-installations.md)|Содержит сведения о включении функции автозапуска для автоматического запуска приложения ClickOnce при вставке носителя.|  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Практическое руководство. Создание ассоциаций файлов для приложения ClickOnce](../deployment/how-to-create-file-associations-for-a-clickonce-application.md)|Содержит сведения о добавлении поддержки расширения имени файла в приложение ClickOnce.|  
|[Инструкции. Получение сведений о строке запроса в приложении ClickOnce в сети](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)|Демонстрирует извлечение параметров, передаваемых в URL-адрес, используемый для запуска приложения ClickOnce.|  
|[Практическое руководство. Отключение активации ClickOnce-приложений по URL-адресу при помощи конструктора](../deployment/how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer.md)|Содержит сведения о принудительном запуске приложения из меню **Пуск** с помощью конструктора.|  
|[Практическое руководство. Отключение активации по URL-адресу приложений ClickOnce](../deployment/how-to-disable-url-activation-of-clickonce-applications.md)|Содержит сведения о принудительном запуске приложения из меню **Пуск**.|  
|[Пошаговое руководство. Загрузка сборок по запросу с помощью API развертывания ClickOnce в конструкторе](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md)|Содержит сведения о загрузке сборок приложения только при их первом использовании с помощью конструктора.|  
|[Пошаговое руководство. Загрузка сборок по требованию с помощью API развертывания ClickOnce](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Содержит сведения о загрузке сборок приложения только при их первом использовании приложением.|  
|[Пошаговое руководство. Загрузка вспомогательных сборок по требованию с помощью интерфейса API технологии развертывания ClickOnce](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Содержит сведения о пометке вспомогательных сборок как необязательных и загрузке только тех сборок, которые необходимы клиентскому компьютеру для использования текущих параметров культуры.|  
|[Разбор примера: развертывание вручную приложения ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)|Содержит сведения об использовании служебных программ .NET Framework для развертывания приложения ClickOnce.|  
|[Пошаговое руководство. Развертывание вручную приложения ClickOnce, которое не требует повторного подписания и сохраняет сведения о фирменной символике](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-app-no-re-signing-required?view=vs-2015)|Содержит сведения об использовании служебных программ .NET Framework для развертывания приложения ClickOnce без повторной подписи манифестов.|  
|[NIB: как оптимизировать приложение для определенного типа ЦП.](https://msdn.microsoft.com/294a75d2-4279-4b72-8298-2bea05be907a)|Содержит сведения о процессе публикации 64-разрядного процессора путем изменения свойства **Целевой ЦП** или **Целевая платформа** в проекте.|  
|[Пошаговое руководство. Включение запуска приложения ClickOnce в нескольких версиях .NET Framework](https://msdn.microsoft.com/7f4383af-ed87-4853-b4d4-02a3967a5fd9)|Содержит сведения об установке и запуске приложения ClickOnce на нескольких версиях платформы .NET Framework.|  
|[Пошаговое руководство. Создание пользовательского установщика для приложения ClickOnce](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md)|Содержит сведения о создании настраиваемого установщика для установки приложения ClickOnce.|  
|[Как опубликовать приложение WPF с включенными стилями оформления](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md)|Содержит пошаговые инструкции для устранения ошибки, которая появляется при попытке публикации приложения WPF с включенными визуальными стилями.|  
  
## <a name="see-also"></a>См. также  
 [Безопасность и развертывание ClickOnce](../deployment/clickonce-security-and-deployment.md)   
 [Справочные сведения ClickOnce](../deployment/clickonce-reference.md)
