---
title: Кодировка и символы разрыва строки
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.Encoding
helpviewer_keywords:
- line breaks
- encoding
- Visual Studio, encoding
- editors, line breaks
- line break characters
- Visual Studio, line break characters
ms.assetid: 8f9b3ffc-7b8d-44f4-87cb-dc29105be12d
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6448b553c1da9e697bca3860cb8507727c99cc08
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "75588594"
---
# <a name="encodings-and-line-endings"></a>Кодировки и окончания строк

В Visual Studio следующие символы интерпретируются как разрывы строк:

- CR LF: возврат каретки + перевод строки, символы Юникода 000D + 000A

- LF: перевод строки, символ Юникода 000A

- NEL: следующая строка, символ Юникода 0085

- LS: разделитель строки, символ Юникода 2028

- PS: разделитель абзаца, символ Юникода 2029

Для текста, который копируется из других приложений, сохраняется исходная кодировка и символы разрыва строки. Например, при копировании текста из Блокнота и вставке его в текстовый файл в Visual Studio текст имеет те же параметры, которые применялись в Блокноте.

При открытии файла, который содержит разные символы разрыва строки, может появиться диалоговое окно с запросом о том, следует ли нормализовать несогласованные символы разрыва строки и какой тип разрыва строки выбрать.

## <a name="advanced-save-options"></a>Дополнительные параметры сохранения

Чтобы определить тип символов разрыва строки, можно использовать параметры в диалоговом окне **Файл** > **Дополнительные параметры сохранения**. Кроме того, с помощью этих параметров можно изменить кодировку файла.

![Диалоговое окно "Дополнительные параметры сохранения"](media/line_endings.png)

> [!NOTE]
> Если в меню **Файл** пункт **Дополнительные параметры сохранения** отсутствует, его можно добавить. В меню **Сервис** выберите пункт **Настроить**, а затем перейдите на вкладку **Команды**. В раскрывающемся списке **Строка меню** выберите пункт **Файл**, а затем нажмите кнопку **Добавить команду**. В диалоговом окне **Добавление команды** в разделе **Категории** выберите **Файл**, а затем в списке **Команды** выберите элемент **Дополнительные параметры сохранения**. Нажмите кнопку **ОК**, а затем кнопку **Переместить вниз**, чтобы переместить команду в любое место в меню. Чтобы закрыть диалоговое окно **Настройки**, нажмите кнопку **Закрыть**. Дополнительные сведения см. в разделе [Настройка меню и панелей инструментов](../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md#customizing_menu).
>
> Кроме того, чтобы открыть диалоговое окно **Дополнительные параметры сохранения**, можно выбрать пункт меню **Файл** > **Сохранить \<файл\> как**. В диалоговом окне **Сохранить файл как** щелкните треугольник раскрывающегося списка рядом с кнопкой **Сохранить** и выберите пункт **Сохранить с кодировкой**.

## <a name="see-also"></a>См. также

- [Возможности редактора кода](../ide/writing-code-in-the-code-and-text-editor.md)
