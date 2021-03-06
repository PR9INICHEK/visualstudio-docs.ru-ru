---
title: Окна Установки Основы (ru) Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Windows Installer, VSPackages
- VSPackages, Windows Installer basics
ms.assetid: 497e479b-add8-4644-870a-917f15306b97
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aeea0b17a3c234bb7670642fb9ae0a442c9d60cd
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "80703417"
---
# <a name="windows-installer-basics"></a>Основные сведения об установщике Windows
Установка Windows устанавливает и удаляет приложения или программные продукты на компьютере пользователя, выполняя эти задачи в единицах, называемых компонентами установки Windows (иногда называемыми WIC или просто компонентами). GUID определяет каждый WIC, который является основной единицей установки и учета ссылок для установок с помощью установки Windows.

 Для полной документации windows Installer см. [Windows Installer](/previous-versions/2kt85ked(v=vs.120))

## <a name="authoring-a-vspackage"></a>Автор VSPackage
 Установка Windows использует пакеты установки, которые содержат информацию, которую windows Installer необходимо установить, удалить или отремонтировать продукт и запустить пользовательский интерфейс настройки (UI). Каждый пакет установки включает в себя файл .msi, который содержит базу данных установки, сводный информационный поток и потоки данных для различных частей установки. Чтобы использовать установщик, необходимо автор установки. Поскольку установщик организует установки вокруг концепции компонентов и хранит информацию об установке в реляционной базе данных, процесс авторизации пакета установки в целом влечет за собой следующие шаги:

1. Планируйте настройку, чтобы поддерживать ваши версии и стратегии.

2. Определите функции, которые будут представлены пользователям.

3. Организуйте VSPackage и зависимости в компоненты.

4. Заполните базу данных установки информацией.

5. Проверка пакета установки.

   Эта документация касается прежде всего первого и третьего этапов процесса. Во время этих шагов вы организуете свои функции VSPackage в WICs, так [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]что вы можете кадр вашей версии и обслуживания стратегии для учета последующих версий . Остальные три шага подробно описаны в документации Windows Installer в платформе SDK.

## <a name="key-terms"></a>Основные понятия
 Ниже приведены определения ключевых терминов, связанных с технологией установки Windows.

 Файлы ресурсов, ключи реестра, ярлыки и т.д., которые могут быть установлены на компьютер. Эти ресурсы логически сгруппированы в компоненты установки Windows.

 Компонент установки Windows (WIC) Основной блок установки, представляющий логическую группировку связанных ресурсов, которые установлены и не установлены в качестве единого устройства. Компоненты установки Windows идентифицируются с помощью уникального идентификатора компонентов, или GUID. Кроме того, Windows Installer поддерживает подсчет ссылок на уровне WIC. Для максимальной гибкости версий включите в данный WIC не более одного основного ресурса, например DLL. Обратите внимание, что после того, как вы идентифицируете и заселяют WIC, привите ему GUID и развернете его, вы не сможете изменить его состав. Для получения дополнительной информации [см.](/windows/desktop/Msi/organizing-applications-into-components)

 Пакет (Пакет Redist) Единица развертывания, состоящая из файла .msi и внешних исходных файлов, на которые этот файл может указать. Пакет содержит всю информацию, необходимую для запуска uI и установки или удаления приложения.

 .msi File A COM-структурированный файл хранения, содержащий инструкции и данные, необходимые для установки приложения. Каждый пакет содержит по крайней мере один файл .msi. Файл .msi содержит базу данных установки, сводный информационный поток и, возможно, один или несколько преобразований и внутренние исходные файлы. Файлы, которые должны быть установлены, могут быть либо сжаты в шкаф и храниться в потоке в файле .msi или храниться, сжаты или не сжаты, за пределами файла .msi на исходной среде. Для получения дополнительной [информации](/windows/desktop/Msi/windows-installer-file-extensions)см.

## <a name="windows-installer-rules-enforcement"></a>Обеспечение соблюдения правил установки Windows
 Два набора правил определяют развертывание ресурсов через компоненты установки. Один набор правил поддерживается самим установщиком Windows, в то время как вы должны применять второй набор в качестве автора установки.

> [!NOTE]
> Соблюдение правил установки Windows происходит только при запуске проверки файла .msi. Тем не менее, вы предупреждены рассматривать эти правила как лучшие практики. Для получения дополнительной информации см. [Package Validation](/windows/desktop/Msi/package-validation) [Validating an Installation Database](/windows/desktop/Msi/validating-an-installation-database)

#### <a name="installer-enforced-rules"></a>Правила, применяемые установщиком

- Все файлы в данном компоненте должны быть установлены в один и тот же каталог. И наоборот, файлы, установленные на отдельные папки, должны принадлежать отдельным компонентам.

- На один компонент может быть только один ключевой путь. Ключевым путем является просто ключ файла или реестра, представляющий весь компонент.

#### <a name="component-provider-responsibilities"></a>Обязанности компонента-поставщика

- Любые два ресурса, которые могут поставляться отдельно в последующих версиях, должны существовать в отдельных компонентах. Ресурсы должны быть сгруппированы в один и тот же компонент только тогда, когда вы уверены, что эти ресурсы никогда не будут поставляться отдельно. На самом деле, рекомендуется, чтобы все первичные ресурсы (DLLs, например) всегда существовали в отдельных WICs. Для получения дополнительной информации [см.](/windows/desktop/Msi/defining-installer-components)

- Ни один из версий ресурса никогда не должен поставляться в более чем одном WIC.

## <a name="see-also"></a>См. также
- [Что произойдет, если правила компонента будут нарушены?](/windows/desktop/Msi/what-happens-if-the-component-rules-are-broken)
