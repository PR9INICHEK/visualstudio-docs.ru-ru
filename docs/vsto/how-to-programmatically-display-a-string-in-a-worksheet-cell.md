---
title: Руководство. программное отображение строки в ячейке листа
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- text [Office development in Visual Studio], adding to worksheets
- worksheets, displaying text in cells
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ed93451942ccb0376c78ebb0e99b269a658131de
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85545929"
---
# <a name="how-to-programmatically-display-a-string-in-a-worksheet-cell"></a>Руководство. программное отображение строки в ячейке листа
  В этом примере показано, как программным способом отобразить текст в ячейке. Чтобы отобразить текст в ячейке, используйте либо <xref:Microsoft.Office.Tools.Excel.NamedRange> элемент управления, либо собственный объект диапазона Excel.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="use-a-namedrange-control"></a>Использование элемента управления NamedRange
 В этом примере используется <xref:Microsoft.Office.Tools.Excel.NamedRange> элемент управления с именем `message` . Элемент управления должен быть добавлен в настройку на уровне документа во время разработки. Следующий код должен быть помещен в класс листа, а не в `ThisWorkbook` класс.

### <a name="to-display-text-in-a-namedrange-control"></a>Отображение текста в элементе управления NamedRange

1. Присвойте <xref:Microsoft.Office.Tools.Excel.NamedRange> элементу управления значение **Hello World**.

     [!code-csharp[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#68)]
     [!code-vb[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#68)]

## <a name="use-a-native-excel-range"></a>Использовать собственный диапазон Excel
 Следующий код создает новый диапазон программным способом, а затем присваивает ему значение.

### <a name="to-display-text-in-an-excel-range"></a>Отображение текста в диапазоне Excel

1. Получите диапазон в ячейке **a1** `Sheet1` и задайте для него значение **Hello World**.

     [!code-csharp[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#69)]
     [!code-vb[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#69)]

## <a name="see-also"></a>См. также раздел
- [Пошаговое руководство. получение данных с помощью формы Windows](../vsto/walkthrough-collecting-data-using-a-windows-form.md)
- [Устранение неполадок решений Office](../vsto/troubleshooting-office-solutions.md)
- [Элемент управления NamedRange](../vsto/namedrange-control.md)
- [Глобальный доступ к объектам в проектах Office](../vsto/global-access-to-objects-in-office-projects.md)
- [Необязательные параметры в решениях Office](../vsto/optional-parameters-in-office-solutions.md)
