---
title: Руководство по Visual Studio Enterprise
description: Настройка Visual Studio в корпоративной среде и устранение неполадок.
ms.date: 07/29/2020
ms.custom: seodec18
ms.topic: overview
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: ''
author: ornellaalt
ms.author: ornella
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 3d223d6e1e6ed3bf4b75b1c66bcc0f9dc897cfed
ms.sourcegitcommit: b8ce85a6d9c7fcceaad0fba625202f5ecf8f368c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "87434321"
---
# <a name="visual-studio-enterprise-guide"></a>Руководство по Visual Studio Enterprise
Начните с этой статьи, если вы хотите сэкономить время, настраивая Visual Studio в корпоративной среде. Это корпоративное руководство содержит советы, которые помогут вам установить и обновить Visual Studio в общих корпоративных сценариях, а также устранить возникающие проблемы. Кроме того, вы узнаете, как сообщить о проблеме, если вам нужна помощь. 

## <a name="get-started"></a>Начало работы 
Узнайте, как развернуть Visual Studio на предприятии в подключенных и автономных средах. 

- **Общие сведения о вариантах корпоративного развертывания в подключенных средах.** Руководство администратора [Visual Studio](visual-studio-administrator-guide.md) включает рекомендации для системных администраторов на основе разных сценариев. 

- **[Советы по устранению неполадок.](troubleshooting-installation-issues.md)** Получите справку по установке или обновлению Visual Studio, а также узнайте о том, как сообщить о проблеме, если вам нужна помощь. Эти советы включают пошаговые инструкции, которые помогут устранить большинство проблем с установкой в подключенном и автономном режимах. 

- **[Создание автономной установки Visual Studio.](create-an-offline-installation-of-visual-studio.md)** Если вы не подключены к Интернету или у вас ограниченные возможности подключения, узнайте об альтернативном варианте установки Visual Studio. 

- **[Создание пакетов начального загрузчика.](../deployment/creating-bootstrapper-packages.md)** Узнайте, как создать пользовательские пакеты начального загрузчика путем создания манифестов продукта и пакета. 

- **[Автоматическое применение ключей продуктов при развертывании Visual Studio.](automatically-apply-product-keys-when-deploying-visual-studio.md)** Ключ продукта можно применить программным способом в составе сценария, используемого для автоматизации развертывания Visual Studio. Ключи продуктов можно задать на устройстве программным способом во время установки Visual Studio или после ее завершения. 

## <a name="install-visual-studio"></a>Установка Visual Studio 

Узнайте, как установить Visual Studio в распространенных корпоративных сценариях. 

- **[Использование параметров командной строки для установки Visual Studio.](use-command-line-parameters-to-install-visual-studio.md)** Узнайте, как использовать разные параметры для управления установкой Visual Studio и ее настройки. Автоматизируйте процесс установки или создайте кэш файлов установки для последующего использования. 

- **См. [примеры параметров командной строки для установки Visual Studio](command-line-parameter-examples.md).** Чтобы продемонстрировать варианты использования параметров командной строки для установки Visual Studio на практике, здесь приводится несколько примеров, которые вы можете настроить в соответствии со своими требованиями. 

- **[Установка и использование Visual Studio и служб Azure, расположенных за брандмауэром или прокси-сервером.](install-and-use-visual-studio-behind-a-firewall-or-proxy-server.md)** Если ваша организация использует средства обеспечения безопасности, например брандмауэр или прокси-сервер, значит есть URL-адреса доменов, которые нужно добавить в список разрешений, а также порты и протоколы, которые нужно открыть, чтобы обеспечить оптимальные установку и использование Visual Studio и служб Azure. 

- **[Создание сетевой установки Visual Studio.](create-a-network-installation-of-visual-studio.md)** Кэшируйте файлы для первоначальной установки вместе со всеми обновлениями продуктов в одной папке.  

## <a name="update-visual-studio"></a>Обновление Visual Studio 

Узнайте, как успешно обновить Visual Studio и устранить проблемы с обновлением. 

- **[Обновление сетевой установки Visual Studio.](update-a-network-installation-of-visual-studio.md)** Вы можете обновить макет сетевой установки Visual Studio, включив последнее обновление продукта, чтобы использовать его в качестве точки установки обновлений Visual Studio и обеспечить поддержку уже развернутых установок на клиентских рабочих станциях.

- **[Обновление Visual Studio во время обслуживания.](update-servicing-baseline.md)** Узнайте о преимуществах обновления на базовом уровне и узнайте разницу между дополнительными выпусками и обновлениями для обслуживания. 

- **[Обновление Visual Studio с использованием минимального автономного макета.](update-minimal-layout.md)** Для компьютеров, не подключенных к Интернету, создание минимального макета — самый простой и быстрый способ обновления автономных экземпляров Visual Studio.

- **[Восстановите](repair-visual-studio.md) Visual Studio, чтобы устранить проблемы с обновлением**. Иногда установка Visual Studio может повреждаться. Восстановление позволяет устранить проблемы, возникшие во время установки, во всех операциях установки, включая обновления. 

- **Учитывайте [базовые показатели безопасности Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)** . Microsoft стремится предоставить своим клиентам защищенные операционные системы, такие как Windows 10 и Windows Server, а также предложить им безопасные приложения, например Microsoft Edge. Помимо гарантии безопасности своих продуктов, Microsoft также позволяет точно управлять средой с помощью различных возможностей конфигурации. 

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>См. также 

- [Руководство по повышению производительности при работе в Visual Studio](../ide/productivity-features.md)



