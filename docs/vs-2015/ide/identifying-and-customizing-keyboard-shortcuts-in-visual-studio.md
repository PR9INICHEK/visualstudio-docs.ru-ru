---
title: Определение и настройка сочетаний клавиш в Visual Studio | Документы Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Environment.Keyboard
helpviewer_keywords:
- keyboard shortcuts [Visual Studio], customizing
- importing shortcut keys [Visual Studio]
- shortcut key combinations [Visual Studio]
- commands [Visual Studio], shortcut keys
- custom shortcut keys [Visual Studio]
- customizing keyboard shortcuts [Visual Studio]
- exporting shortcut keys [Visual Studio]
ms.assetid: d2774be2-60a4-4d6f-95f1-79d0d9e55b56
caps.latest.revision: 30
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 00ed1bd4a3aa9cbf13df36a91e871af498a7e22b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47571431"
---
# <a name="identifying-and-customizing-keyboard-shortcuts-in-visual-studio"></a>Определение и настройка сочетаний клавиш в Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [определение и Настройка сочетаний клавиш в Visual Studio](https://docs.microsoft.com/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).  
  
Вы можете определить сочетания клавиш для команд Visual Studio, настроить эти сочетания клавиш и экспортировать их для других пользователей. Многие сочетания клавиш всегда вызывают одни и те же команды, в то время как поведение других сочетаний клавиш может быть различным в зависимости от следующих условий:  
  
-   параметры среды по умолчанию, которые были выбраны при первом запуске Visual Studio (например, "Обычные параметры среды разработки" или "Visual C#");  
  
-   настраивались ли сочетания клавиш пользователем;  
  
-   контекст в момент нажатия сочетания клавиш. Например, клавиша F2 вызывает команду Edit.EditCell при использовании конструктора параметров и команду File.Rename при использовании Team Explorer.  
  
 Независимо от настроенных параметров и контекста сочетания клавиш можно всегда найти и изменить в диалоговом окне **Параметры**. Кроме того, в разделе [Сочетания клавиш по умолчанию для часто используемых команд](../ide/default-keyboard-shortcuts-for-frequently-used-commands-in-visual-studio.md) можно найти сочетания клавиш по умолчанию для нескольких десятков команд, а полный список сочетаний клавиш по умолчанию (для режима "Обычные параметры разработки") приведен в разделе [Сочетания клавиш по умолчанию](../ide/default-keyboard-shortcuts-in-visual-studio.md).  
  
 **Содержание раздела**  
  
-   [Определение сочетания клавиш](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md#bkmk_identify)  
  
-   [Настройка сочетания клавиш](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md#bkmk_assign)  
  
-   [Совместное использование пользовательских сочетаний клавиш](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md#bkmk_transfer)  
  
 Если сочетание клавиш назначено команде в глобальном контексте и ни в каких других контекстах, это сочетание будет всегда вызвать данную команду. Однако сочетание клавиш можно назначить одной команде в глобальном контексте и другой команде в более узком контексте. При использовании такого сочетания клавиш в конкретном контексте вызывается команда для данного контекста, а не для глобального контекста.  
  
> [!NOTE]
>  Имена и расположение команд меню и параметров в диалоговых окнах могут зависеть от пользовательских настроек и выпуска Visual Studio. Этот раздел основан на конфигурации **Обычные параметры разработки**.  
  
##  <a name="bkmk_identify"></a> Определение сочетания клавиш  
  
1.  В строке меню выберите **Сервис**, **Параметры**.  
  
2.  Разверните пункт **Среда** и выберите элемент **Клавиатура**.  
  
     ![Отображение сочетаний клавиш в диалоговом окне "Параметры"](../ide/media/optionskeyboard.png "OptionsKeyboard")  
  
3.  В поле **Показать команды, содержащие** введите полное имя команды без пробелов или его часть.  
  
     Например, можно найти команды **solutionexplorer**.  
  
4.  В списке выберите нужную команду.  
  
     Например, можно выбрать **View.SolutionExplorer**.  
  
5.  Если команда имеет сочетание клавиш, оно отображается в списке **Сочетание клавиш для выбранной команды**.  
  
     ![Просмотр сочетания клавиш для определенной команды](../ide/media/viewshortcut.png "ViewShortcut")  
  
##  <a name="bkmk_assign"></a> Настройка сочетания клавиш  
  
1.  В строке меню выберите **Сервис**, **Параметры**.  
  
2.  Разверните папку **Среда** и выберите элемент **Клавиатура**.  
  
     ![Отображение сочетаний клавиш в диалоговом окне "Параметры"](../ide/media/optionskeyboard.png "OptionsKeyboard")  
  
3.  В поле **Показать команды, содержащие** введите полное имя команды без пробелов или его часть.  
  
     Например, можно найти команды **solutionexplorer**.  
  
4.  Выберите из списка команду, которой нужно назначить сочетание клавиш.  
  
5.  В списке **Область действия** выберите функциональную область, в которой будет использоваться данное сочетание клавиш.  
  
     Чтобы использовать сочетание в любом контексте, выберите **Глобальная**. Вы можете выбрать любое сочетание клавиш, которое не используется в другом редакторе (например, как глобальное). В противном случае будет использование сочетание клавиш редактора.  
  
    > [!NOTE]
    >  В **глобальном** контексте нельзя назначать сочетания клавиш, включающие следующие клавиши: PRINT SCRN/SYS RQ, SCROLL LOCK, PAUSE/BREAK, TAB, CAPS LOCK, INSERT, HOME, END, PAGE UP, PAGE DOWN, клавиша с логотипом Windows, клавиша меню приложения, клавиши со стрелками, ВВОД, NUM LOCK, DELETE или CLEAR на цифровой клавиатуре, а также CTRL+ALT+DELETE.  
  
6.  В поле **Введите сочетание клавиш** введите требуемое сочетание клавиш.  
  
    > [!NOTE]
    >  Вы можете создать сочетание клавиш, состоящее из буквы и клавиши ALT, CTRL или из обеих этих клавиш. Кроме того, можно создать сочетание клавиш, состоящее из клавиши SHIFT и буквы с клавишей ALT, CTRL или обеими этими клавишами.  
  
     Если сочетание клавиш уже назначено другой команде, оно отображается в поле **Сочетание клавиш в настоящий момент используется для**. В этом случае нажмите клавишу BACKSPACE, чтобы удалить сочетание клавиш, прежде чем пробовать другое сочетание.  
  
     ![Укажите другое сочетание клавиш для команды](../ide/media/reassignshortcut.png "ReassignShortcut")  
  
7.  Нажмите кнопку **Назначить**.  
  
    > [!NOTE]
    >  Если вы задали для команды другое сочетание клавиш, нажали кнопку **Назначить**, а затем кнопку **Отмена**, диалоговое окно закрывается, но изменение не отменяется.  
  
##  <a name="bkmk_transfer"></a> Совместное использование пользовательских сочетаний клавиш  
 Вы можете поделиться своими сочетаниями клавиш, экспортировав их в файл, а затем передав этот файл другим пользователям, чтобы они импортировали данные из него.  
  
#### <a name="to-export-only-keyboard-shortcuts"></a>Экспорт сочетаний клавиш  
  
1.  В строке меню выберите **Сервис**, **Импорт и экспорт параметров**.  
  
2.  Выберите команду **Экспортировать выбранные параметры среды** и нажмите кнопку **Далее**.  
  
3.  В области **Выберите параметры для экспорта** снимите флажок **Все параметры**, разверните узел **Параметры**, а затем узел **Среда**.  
  
4.  Установите флажок **Клавиатура** и нажмите кнопку **Далее**.  
  
     ![Экспорт только настроенных сочетаний клавиш](../ide/media/exportshortcuts.png "ExportShortcuts")  
  
5.  В полях **Выберите имя для файла параметров** и **Сохранить файл параметров в этом каталоге** оставьте значения по умолчанию или укажите другие значения, а затем нажмите кнопку **Готово**.  
  
     По умолчанию сочетания клавиш сохраняются в файле в папке %USERPROFILE%\Documents\Visual Studio 2013\Settings. Имя файла содержит дату экспорта параметров и имеет расширение .vssettings.  
  
#### <a name="to-import-only-keyboard-shortcuts"></a>Импорт сочетаний клавиш  
  
1.  В строке меню выберите **Сервис**, **Импорт и экспорт параметров**.  
  
2.  Выберите команду **Импортировать выбранные параметры среды** и нажмите кнопку **Далее**.  
  
3.  Выберите параметр **Нет, импортировать новые значения, перезаписав мои текущие параметры**, а затем нажмите кнопку **Далее**.  
  
4.  В окне **Мои параметры** выберите файл, содержащий нужные сочетания клавиш, или нажмите кнопку **Обзор**, чтобы найти нужный файл.  
  
5.  Нажмите кнопку **Далее**.  
  
6.  В области **Выберите параметры для импорта** снимите флажок **Все параметры**, разверните узел **Параметры**, а затем узел **Среда**.  
  
7.  Установите флажок **Клавиатура** и нажмите кнопку **Готово**.  
  
     ![Импорт только настроенных сочетаний клавиш](../ide/media/importshortcuts.png "ImportShortcuts")  
  
## <a name="see-also"></a>См. также  
 [Специальные возможности Visual Studio](../ide/reference/accessibility-features-of-visual-studio.md)


