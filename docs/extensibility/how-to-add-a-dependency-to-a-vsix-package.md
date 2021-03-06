---
title: Как добавить зависимость в пакет VSIX | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 063767f8f50793253c236db5d5b90e1d6db1bff4
ms.sourcegitcommit: 05487d286ed891a04196aacd965870e2ceaadb68
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85905874"
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>Как добавить зависимость в пакет VSIX

Можно настроить развертывание пакета VSIX, устанавливающего все зависимости, которые еще не существуют на целевом компьютере. Для этого включите зависимости VSIX в файл *source. extension. vsixmanifest* .

## <a name="to-add-a-dependency"></a>Добавление зависимости

1. Откройте файл *source. extension. vsixmanifest* в представлении **конструктора** . Перейдите на вкладку **зависимости** и нажмите кнопку **создать**.

2. Чтобы добавить установленное расширение, в диалоговом окне " **Добавление новой зависимости** " выберите **установленное расширение** , а затем в поле **имя**выберите расширение в списке.

3. Чтобы добавить еще не установленный VSIX: в диалоговом окне **Добавление новой зависимости** выберите **файл в файловой системе** , а затем нажмите кнопку **Обзор** , чтобы выбрать VSIX.

## <a name="require-a-specific-visual-studio-release"></a>Требовать конкретный выпуск Visual Studio

Например, если для расширения требуется определенная версия Visual Studio 2017, то она зависит от функции, выпущенной в 15,3, можно указать номер сборки в VSIX **InstallationTarget**. Например, выпуск 15,3 имеет номер сборки "15.0.26730.3". Сопоставление выпусков для номеров сборки можно увидеть [здесь](../install/visual-studio-build-numbers-and-release-dates.md). Обратите внимание, что использование номера выпуска "15,3" не будет работать правильно.

Если для расширения требуется 15,3 или более поздней версии, вы объявили **версию InstallationTarget** как [15.0.26730.3, 16,0):

```xml
<Installation>
  <InstallationTarget Id="Microsoft.VisualStudio.Community" Version="[15.0.26730.3, 16.0)" />
</Installation>
```

Всиксинсталлер обнаружит более ранние версии Visual Studio и сообщит пользователю о необходимости последующего обновления.

## <a name="see-also"></a>Дополнительно

- [Справочник по схеме расширения VSIX 1,0](https://msdn.microsoft.com/library/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)
- [Анатомия пакета VSIX](../extensibility/anatomy-of-a-vsix-package.md)
- [Подготовка расширений для развертывания установщик Windows](../extensibility/preparing-extensions-for-windows-installer-deployment.md)
