---
title: Практическое руководство. Проверка параметров свойства IIS | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- IIS, property settings
- debugging Web applications, troubleshooting
- IIS administration tool
- Web applications, setting properties
- properties [debugger], setting with IIS administration tool
ms.assetid: 9efc50bf-02fb-4750-9b3e-f03c38f10d8b
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ac2ce4f823d82d8a0d8569e15c4ba8920d91d36c
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65686834"
---
# <a name="how-to-verify-iis-property-settings"></a>Практическое руководство. проверку параметров свойства IIS
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Можно задать свойства для веб-приложения с помощью средства администрирования IIS. Чтобы приложение выполнялось, эти свойства должны быть заданы правильно. Поэтому проверка этих параметров часто является необходимым шагом в устранении неполадок.  
  
> [!NOTE]
> Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-check-iis-settings-for-the-web-application"></a>Проверка параметров IIS для веб-приложения  
  
1. Откройте **Администрирование** окна: На **запустить** последовательно выберите пункты **программы**, а затем нажмите кнопку **Администрирование**. Если пункт **Администрирование** не появляется в меню **Программы**, то следует искать его в **панели управления**.  
  
    - В операционной системе Windows 2000 выберите пункт **Диспетчер служб Интернета**.  
  
    - В Windows XP выберите пункт **Службы IIS**.  
  
    - В Windows Server 2003 дважды щелкните пункт **Управление сервером**.  
  
         Откроется окно **Управление сервером**. В пункте **Сервер приложения** щелкните пункт **Управление этим сервером приложения**.  
  
         Откроется окно **Сервер приложения**. В левой области откройте узел **Диспетчер служб IIS**.  
  
2. В диалоговом окне выберите дерево элемента управления узлами для своего компьютера. Щелкните узел **Веб-сайты** и выберите узел веб-приложения. Это может быть как узел веб-сайта, являющийся одноуровневым **веб-сайтом по умолчанию**, так и узел виртуального каталога, находящегося под существующим узлом веб-сайта.  
  
3. Щелкните правой кнопкой мыши веб-приложение и в контекстном меню выберите пункт **Свойства**.  
  
4. Проверьте параметры безопасности для веб-приложения:  
  
    1. В окне веб-приложения **Свойства** щелкните вкладку **Безопасность каталога** и выберите пункт **Правка**.  
  
    2. В диалоговом окне **Методы проверки подлинности** выберите пункты **Разрешить анонимный доступ** и **Встроенная проверка подлинности Windows** (если не установлены).  
  
    3. Нажмите кнопку **OK**, чтобы закрыть диалоговое окно **Методы проверки подлинности**.  
  
5. Для приложения сервера ATL необходимо проверить, связана ли команда DEBUG с расширением ISAPI. Дополнительные сведения см. в разделе [Практическое руководство. Связать команда DEBUG с расширением](https://msdn.microsoft.com/50d261d3-4bd4-41c0-b44e-3591086f121e).  
  
6. Убедитесь, что виртуальному каталогу для приложения [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] задано имя приложения в компонентах **Диспетчер служб IIS**, **Диспетчер служб Интернета** или **Службы IIS**.  
  
    1. В окне **Свойства** веб-приложения выберите вкладку **Каталог**, если приложение находится в виртуальном каталоге, или вкладку **Корневой каталог**, если приложение находится на веб-сайте.  
  
    2. Убедитесь, что имя в пункте **Локальный путь** соответствует имени каталога, в котором приложение было развернуто.  
  
    3. В окне **Параметры приложения** введите имя корневого каталога, который содержит приложение.  
  
    4. Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно **Свойства**.  
  
7. Для приложения [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] щелкните вкладку **ASP.NET** и убедитесь, что указана правильная версия [!INCLUDE[vstecasp](../includes/vstecasp-md.md)].  
  
8. Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно **Свойства**.  
  
9. Нажмите кнопку **OK**, чтобы закрыть диалоговое окно **Диспетчер служб IIS**, **Диспетчер служб Интернета** или **Службы IIS**.  
  
## <a name="see-also"></a>См. также  
 [Устранение неполадок](../debugger/debugging-web-applications-troubleshooting.md)
