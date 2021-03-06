---
title: Начало работы с языковой службы и редактор расширения (ru) Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - extensions
ms.assetid: 6b151891-c06d-40b1-9867-42298caa8492
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7894efc477e0c406cf8e85f4d3d31df4f2ef97c5
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "80711312"
---
# <a name="get-started-with-language-service-and-editor-extensions"></a>Начало работы с языковой службой и расширением редактора
Вы можете использовать расширение редактора для добавления функций языкового сервиса, таких как описание, соответствие скобки, IntelliSense и лампочки на свой собственный язык программирования или к любому типу контента. Вы также можете настроить внешний вид и поведение редактора Visual Studio, например, окраску текста, поля, украшения и другие визуальные элементы. Вы также можете определить свой собственный тип содержимого и указать внешний вид и поведение текстовых представлений, в которых отображается содержимое.

 Чтобы начать писать расширения редактора, используйте шаблоны проекта редактора, которые установлены как часть Визуальной студии SDK. Visual Studio SDK представляет собой загружаемый набор инструментов, которые облегчают разработку расширений Visual Studio, либо с помощью VSPackages, либо с помощью управляемой рамки расширения (MEF).

> [!NOTE]
> Для получения дополнительной информации о Визуальной студии SDK, [см.](../extensibility/visual-studio-sdk.md)

 Мы рекомендуем вам узнать о следующих концепциях и технологиях, прежде чем писать свои собственные расширения редактора.

## <a name="the-windows-presentation-foundation-wpf-and-editor-extensions"></a>Презентационный фонд Windows (WPF) и расширение редактора
 Пользовательский интерфейс редактора Visual Studio (UI) реализован с помощью Фонда презентации Windows (WPF). WPF обеспечивает богатый визуальный опыт и последовательную модель программирования, которая отделяет визуальные аспекты кода от бизнес-логики. При создании расширений редактора можно использовать множество элементов и функций WPF. Для получения дополнительной [Windows Presentation Foundation](/dotnet/framework/wpf/index)информации см.

## <a name="the-managed-extensibility-framework-mef-and-editor-extensions"></a>Рамочная система управляемой расширения (MEF) и расширение редактора
 Редактор Visual Studio использует Рамочную управляемость (MEF) для управления своими компонентами и расширениями. MEF также позволяет разработчикам более легко создавать расширения для принимающего приложения, такого как Visual Studio. В этих рамках вы определяете расширение в соответствии с контрактом MEF и экспортируете его в качестве компонентной части MEF. Приложение хоста управляет компонентными частями, находя их, регистрируя их и убедившись, что они применяются к правильному контексту.

> [!NOTE]
> Для получения дополнительной информации о MEF в редакторе, [см.](../extensibility/managed-extensibility-framework-in-the-editor.md)

## <a name="visual-studio-editor-extension-points-and-extensions"></a>Пункты расширения редактора Visual Studio и расширения
 Точки расширения редактора — это компоненты MEF, которые можно настроить и расширить. В некоторых случаях вы расширяете точку расширения, внедряя интерфейс и экспортируя его вместе с правильными метаданными. В других случаях вы просто объявить расширение и экспортировать его в качестве конкретного типа.

 Ниже приведены некоторые из основных видов расширения редактора:

- Поля и прокрутки

- Теги

- Украшения

- Параметры

- IntelliSense

  Для получения дополнительной информации о точках расширения редактора [см.](../extensibility/language-service-and-editor-extension-points.md)

## <a name="deploying-editor-extensions"></a>Развертывание расширения редактора
 В Visual Studio вы развертываете расширения редактора, добавляя файл метаданных под названием *source.extension.vsixmanifest* к решению, создавая решение, а затем добавляя копию двоичных файлов и манифест в папку, которая известна Visual Studio. Файл манифеста определяет основные факты о расширении (например, имя, автор, версия и тип содержимого). Для получения дополнительной информации о файле VSIX манифест атакжем развертывания расширений [см.](../extensibility/shipping-visual-studio-extensions.md)

 При установке расширения на компьютере, включите бинарные файлы и манифест в подфон папки, которая известна Visual Studio.

> [!WARNING]
> Вам не придется беспокоиться о деталях манифестов и местоположений развертывания, если вы используете один из шаблонов расширяемости редактора, которые включены в Visual Studio. Шаблоны содержат все необходимое для регистрации и развертывания расширения.

## <a name="run-extensions-in-the-experimental-instance"></a>Запуск расширений в экспериментальном экземпляре
 Вы можете изолировать рабочую версию Visual Studio, разрабатывая расширение, развернув ее в следующей экспериментальной папке (на Windows Vista и Windows 7):

 *«%LOCALAPPDATA% »Визуальнаястудия\\»10.0Эксп(Расширения» (Компания)\\«Расширение»*

 где *%LOCALAPPDATA%* — это имя зарегистрированного пользователя, *компания* — это название компании, которой принадлежит расширение, а *ExtensionID* — идентификатор расширения.

 При развертывании расширения в экспериментальном месте оно работает в режиме отладки. Второй экземпляр Visual Studio запущен, и называется **Microsoft Visual Studio - Экспериментальная инстанция**.

## <a name="manage-extensions"></a>Управление расширениями
 Расширения для Visual Studio перечислены в **расширениях и обновлениях** (в меню **Инструментов).** Если вы тестируете расширение в экспериментальном экземпляре, оно перечислено в **Extensions and Updates** в экспериментальном экземпляре, но не перечислено в экземпляре разработки.

 Для получения дополнительной информации смотрите [поиск и использование расширений Visual Studio](../ide/finding-and-using-visual-studio-extensions.md).

## <a name="use-templates-to-create-editor-extensions"></a>Используйте шаблоны для создания расширений редактора
 Шаблоны редактора можно использовать для создания расширений MEF, которые настраивают классификаторы, украшения и поля. Существуют шаблоны как для проектов с c-, так и для Visual Basic. Для получения дополнительной информации [см. Создать расширение с шаблоном элемента редактора](../extensibility/creating-an-extension-with-an-editor-item-template.md).

 Вы также можете использовать шаблон проекта VSIX для создания расширений. Этот шаблон предоставляет только элементы, необходимые для развертывания любого вида расширения, и включает файл *source.extension.vsixmanifest,* требуемые ссылки на сборку и файл проекта, который включает задачи сборки, которые позволяют развернуть расширение. Для получения дополнительной [VSIX project template](../extensibility/vsix-project-template.md)информации см.

 Вы также можете создать компоненты редактора MEF из расширения пакета Visual Studio. Подробности смотрите следующие пошаговые материалы:

- [Прохождение: Использование команды оболочки с расширением редактора](../extensibility/walkthrough-using-a-shell-command-with-an-editor-extension.md)

- [Прохождение: Использование ключа ярлыка с расширением редактора](../extensibility/walkthrough-using-a-shortcut-key-with-an-editor-extension.md)

## <a name="see-also"></a>См. также
- [Языковой сервис и точки расширения редактора](../extensibility/language-service-and-editor-extension-points.md)
