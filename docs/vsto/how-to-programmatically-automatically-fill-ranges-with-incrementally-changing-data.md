---
title: Программное заполнение постепенно изменяющегося диапазона данных
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Autofill method [Excel]
- filling ranges automatically
- ranges, automatically filling
- workbooks, filling ranges
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 076381c93d11c2d13bdd89ea5c36c0039e15ef71
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85547476"
---
# <a name="how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data"></a>Руководство. программное автоматическое заполнение диапазонов путем постепенного изменения данных
  <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>Метод <xref:Microsoft.Office.Interop.Excel.Range> объекта позволяет автоматически заполнять диапазон на листе значениями. Чаще всего <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> метод используется для хранения инкрементно увеличивающихся или уменьшающихся значений в диапазоне. Поведение можно указать, предоставив необязательную константу из <xref:Microsoft.Office.Interop.Excel.XlAutoFillType> перечисления.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 При использовании необходимо указать два диапазона <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> :

- Диапазон, вызывающий <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> метод, который задает начальную точку заливки и содержит начальное значение.

- Диапазон, который необходимо заполнить, передаваемый в качестве параметра в <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> метод. Этот конечный диапазон должен включать диапазон, содержащий начальное значение.

    > [!NOTE]
    > Нельзя передать <xref:Microsoft.Office.Tools.Excel.NamedRange> элемент управления вместо <xref:Microsoft.Office.Interop.Excel.Range> . Дополнительные сведения см. в разделе [программные ограничения ведущих элементов и элементов управления ведущего приложения](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).

## <a name="example"></a>Пример
 [!code-csharp[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#49)]
 [!code-vb[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#49)]

## <a name="compile-the-code"></a>Компиляция кода
 Первая ячейка диапазона, который необходимо заполнить, должна содержать начальное значение.

 В этом примере необходимо заполнить три региона:

- Столбец B содержит пять дней недели. В качестве начального значения введите **понедельник** в ячейке B1.

- Столбец C включает пять месяцев. В качестве начального значения введите **Январь** в ячейке C1.

- Столбец D включает ряд чисел, увеличивающийся по двум для каждой строки. Для начальных значений введите **4** в ячейке D1 и **6** в ячейке D2.

## <a name="see-also"></a>См. также раздел
- [Работа с диапазонами](../vsto/working-with-ranges.md)
- [Как программно ссылаться на диапазоны листов в коде](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)
- [Руководство. Программное применение стилей к диапазонам в книгах](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)
- [Руководство. программное выполнение вычислений Excel](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)
- [Общие сведения о ведущих элементах и элементах управления ведущего приложения](../vsto/host-items-and-host-controls-overview.md)
- [Необязательные параметры в решениях Office](../vsto/optional-parameters-in-office-solutions.md)
