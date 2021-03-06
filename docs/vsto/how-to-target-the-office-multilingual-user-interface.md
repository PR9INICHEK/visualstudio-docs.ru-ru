---
title: Как ориентироваться на многоязыковой пользовательский интерфейс Office
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- globalization [Office development in Visual Studio], user interface targeting
- MUI [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], localization
- Multilingual User Interface [Office development in Visual Studio]
- localization [Office development in Visual Studio], user interface targeting
- Office applications [Office development in Visual Studio], globalization
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5217f2d6cf67eced00c0c84b9bacda94573c5a09
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85537505"
---
# <a name="how-to-target-the-office-multilingual-user-interface"></a>Как ориентироваться на многоязыковой пользовательский интерфейс Office
  Многоязыковой интерфейс пользователя (MUI) — это Microsoft Office функция, которая дает возможность пользователю изменять язык ПОЛЬЗОВАТЕЛЬСКОГО интерфейса. Например, конечный пользователь, работающий в пользовательском интерфейсе на английском языке, может изменить язык пользовательского интерфейса на испанский.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 Если приложение будет использоваться людьми, использующими множество языков Office, можно добавить код для автоматического изменения языка строк пользовательского интерфейса в соответствии с языком, используемым Office на компьютере пользователя (если у пользователя установлены правильные ресурсы).

## <a name="to-check-the-current-office-ui-setting"></a>Проверка текущего параметра пользовательского интерфейса Office

1. Используйте <xref:System.Threading.Thread.CurrentUICulture%2A> свойство текущего потока. Задайте язык строк пользовательского интерфейса в соответствии с языком, используемым версией Office, которая в настоящее время выполняется на компьютере пользователя.

     [!code-vb[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#10)]
     [!code-csharp[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#10)]

## <a name="see-also"></a>См. также
- [Пошаговое руководство. Назначение приложений Office через основные сборки взаимодействия](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)
- [Позднее связывание в решениях Office](../vsto/late-binding-in-office-solutions.md)
