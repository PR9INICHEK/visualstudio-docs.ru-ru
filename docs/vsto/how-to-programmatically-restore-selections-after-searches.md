---
title: Как программным способом восстановить выделенные элементы после поиска
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- searches, restoring selection after
- documents [Office development in Visual Studio], restoring selections
- selections, restoring after a search
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 30daa81c33070db3f9418b45b84b4acc6e243dc9
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85547099"
---
# <a name="how-to-programmatically-restore-selections-after-searches"></a>Как программным способом восстановить выделенные элементы после поиска
  При поиске и замене текста в документе может потребоваться восстановить исходный фрагмент пользователя после завершения поиска.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 Код в примере процедуры использует два <xref:Microsoft.Office.Interop.Word.Range> объекта. В одном из них хранится текущее значение <xref:Microsoft.Office.Interop.Word.Selection> , а в качестве диапазона поиска используется весь документ.

## <a name="to-restore-the-users-original-selection-after-a-search"></a>Восстановление исходного фрагмента пользователя после поиска

1. Создание <xref:Microsoft.Office.Interop.Word.Range> объектов для документа и текущего выделения.

    [!code-vb[Trin_VstcoreWordAutomation#83](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#83)]
    [!code-csharp[Trin_VstcoreWordAutomation#83](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#83)]

2. Выполните операцию поиска и замены.

    [!code-vb[Trin_VstcoreWordAutomation#84](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#84)]
    [!code-csharp[Trin_VstcoreWordAutomation#84](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#84)]

3. Выберите начальный диапазон для восстановления исходного выбора пользователя.

    [!code-vb[Trin_VstcoreWordAutomation#85](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#85)]
    [!code-csharp[Trin_VstcoreWordAutomation#85](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#85)]

   В следующем примере показан полный метод.

## <a name="example"></a>Пример
 [!code-vb[Trin_VstcoreWordAutomation#82](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#82)]
 [!code-csharp[Trin_VstcoreWordAutomation#82](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#82)]

## <a name="see-also"></a>См. также раздел
- [Руководство. Программный поиск и замена текста в документах](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)
- [Как программно задать параметры поиска в Word](../vsto/how-to-programmatically-set-search-options-in-word.md)
- [Пошаговое руководство. Программный перебор найденных элементов в документах](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)
- [Необязательные параметры в решениях Office](../vsto/optional-parameters-in-office-solutions.md)
