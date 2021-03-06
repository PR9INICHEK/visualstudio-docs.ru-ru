---
title: Синхронно автозагруженные расширения
ms.date: 12/11/2019
ms.topic: conceptual
ms.assetid: 822e3cf8-f723-4ff1-8467-e0fb42358a1f
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ab62d235fd6ed4e47e765fc23868acd5c56efcb2
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "80699373"
---
# <a name="synchronously-autoloaded-extensions"></a>Синхронно автозагруженные расширения

Синхронно автоматически загруженные расширения оказывают негативное влияние на производительность Visual Studio и должны быть преобразованы в использование асинхронной автоматической нагрузки вместо. По умолчанию Visual Studio 2019 блокирует синхронно автоматически загруженные пакеты из любого расширения и уведомляет пользователя.

![Предупреждение о совместимости расширения](media/extension-compatibility-warning-16-1.png.png)

Вы можете:

- Нажмите на **Разрешить синхронную автозагрузку,** чтобы расширения для автоматической загрузки. Чтобы изменить эту настройку в опциях Visual Studio, нажмите «Среда», затем нажмите «Расширения», а затем выберите флажок «Разрешить синхронную автозагрузку расширений». 

- Нажмите на **производительность управления,** чтобы открыть [диалог менеджера производительности,](#performance-manager-dialog) который показывает проблемы с производительностью с расширениями и окнами инструментов.

- Нажмите на **Кнопку Не показывать это сообщение для текущих расширений,** чтобы отклонить уведомление и предотвратить будущие уведомления от существующих установленных расширений. Если вы добавите новое расширение, которое синхронизируется с автозагрузкой, это уведомление будет отображаться снова. Вы будете продолжать получать уведомления о других функциях Visual Studio.

## <a name="performance-manager-dialog"></a>Диалог менеджера производительности

![диалог менеджера производительности](media/performance-manager.png)

Все расширения, синхронизированные с любыми пакетами в любых пользовательских сеансах, отображаются во вкладке **Deprecated AI.**

* Нажмите на **более подробную информацию об этой проблеме,** чтобы собрать больше информации об утомленных AI.
* Свяжитесь с поставщиками расширений для получения прогресса миграции.

## <a name="specify-synchronous-autoload-settings-using-group-policy"></a>Укажите параметры синхронных автонагрузок с помощью групповой политики

Администраторы могут включить групповую политику для обеспечения синхронной автоматической загрузки. Для этого задайте политику на основе реестра в следующем разделе:

**HKEY_LOCAL_MACHINE-SOFTWARE-Политика,Microsoft/VisualStudio-SynchronousAutoload**

Вход и **разрешено**

Значение — (DWORD)
* **0** - синхронная автозагрузка не допускается
* **1** синхронная автозагрузка разрешена

## <a name="extension-authors"></a>Авторы расширения
Авторы расширения могут найти инструкции для переноса пакетов на асинхронную автозагрузку при [переходе в AsyncPackage.](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/AsyncPackageMigration)

## <a name="see-also"></a>См. также
Более подробную информацию о настройках синхронной автоматической загрузки можно узнать на [странице](https://devblogs.microsoft.com/visualstudio/updates-to-synchronous-autoload-of-extensions-in-visual-studio-2019/) Visual Studio 2019.
