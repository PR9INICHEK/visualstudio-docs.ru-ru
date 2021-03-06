---
title: Добавление пользовательских XML-частей в документы с помощью надстроек VSTO
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- PowerPoint [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- custom XML parts [Office development in Visual Studio], adding
- documents [Office development in Visual Studio], custom XML parts
- application-level add-ins [Office development in Visual Studio], custom XML parts
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 92c00ea69069b7374f5f595cc6f198aac23d1f91
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85538298"
---
# <a name="how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins"></a>Инструкции. Добавление пользовательских XML-частей в документы с помощью надстроек VSTO
  XML-данные можно сохранить в следующих типах документов, создав пользовательскую XML-часть в надстройке VSTO:

- книга Microsoft Office Excel;

- документ Microsoft Office Word;

- презентация Microsoft Office PowerPoint.

  Дополнительные сведения см. в разделе [Общие сведения о пользовательских XML-частях](../vsto/custom-xml-parts-overview.md).

  **Область применения.** Сведения этого раздела относятся к проектам уровня приложения для Excel, PowerPoint и Word. Дополнительные сведения см. в разделе [доступность функций по типам приложений Office и проектов](../vsto/features-available-by-office-application-and-project-type.md).

## <a name="to-add-a-custom-xml-part-to-an-excel-workbook"></a>Добавление пользовательской XML-части в книгу Excel

1. Добавьте новый объект <xref:Microsoft.Office.Core.CustomXMLPart> в коллекцию <xref:Microsoft.Office.Interop.Excel._Workbook.CustomXMLParts%2A> в книге. Объект <xref:Microsoft.Office.Core.CustomXMLPart> содержит XML-строку, которую требуется сохранить в книге.

     Следующий пример кода добавляет пользовательскую XML-часть в указанную книгу.

     [!code-vb[Trin_AddCustomXmlPartExcelAppLevel#1](../vsto/codesnippet/VisualBasic/trin_addcustomxmlpartexcelapplevel/ThisAddIn.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartExcelAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartExcelAppLevel/ThisAddIn.cs#1)]

2. Добавьте `AddCustomXmlPartToWorkbook` метод в `ThisAddIn` класс в проекте надстройки VSTO для Excel.

3. Вызовите метод из другого кода в проекте. Например, для создания пользовательской XML-части, когда пользователь открывает книгу, вызовите метод из обработчика события <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookOpen> .

## <a name="to-add-a-custom-xml-part-to-a-word-document"></a>Добавление пользовательской XML-части в документ Word

1. Добавьте новый объект <xref:Microsoft.Office.Core.CustomXMLPart> в коллекцию <xref:Microsoft.Office.Interop.Word._Document.CustomXMLParts%2A> в документе. Объект <xref:Microsoft.Office.Core.CustomXMLPart> содержит XML-строку, которую требуется сохранить в документе.

     Следующий пример кода добавляет пользовательскую XML-часть в указанный документ.

     [!code-vb[Trin_AddCustomXmlPartWordAppLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartWordAppLevel/ThisAddIn.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartWordAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartWordAppLevel/ThisAddIn.cs#1)]

2. Добавьте `AddCustomXmlPartToDocument` метод в `ThisAddIn` класс в проекте надстройки VSTO для Word.

3. Вызовите метод из другого кода в проекте. Например, для создания пользовательской XML-части, когда пользователь открывает документ, вызовите метод из обработчика события <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> .

## <a name="to-add-a-custom-xml-part-to-a-powerpoint-presentation"></a>Добавление пользовательской XML-части в презентацию PowerPoint

1. Добавьте новый <xref:Microsoft.Office.Core.CustomXMLPart> объект в коллекцию [Microsoft. Office. Interop. PowerPoint. _Presentation. CustomXMLParts](/previous-versions/office/developer/office-2010/ff760806%28v%3doffice.14%29) в презентации. Объект <xref:Microsoft.Office.Core.CustomXMLPart> содержит XML-строку, которую требуется сохранить в презентации.

     Следующий пример кода добавляет пользовательскую XML-часть в указанную презентацию.

     [!code-csharp[Trin_AddCustomXmlPartPowerPointAppLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartPowerPointAppLevel/ThisAddIn.cs#1)]
     [!code-vb[Trin_AddCustomXmlPartPowerPointAppLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartPowerPointAppLevel/ThisAddIn.vb#1)]

2. Добавьте `AddCustomXmlPartToPresentation` метод в `ThisAddIn` класс в проекте надстройки VSTO для PowerPoint.

3. Вызовите метод из другого кода в проекте. Например, чтобы создать пользовательскую XML-часть, когда пользователь открывает презентацию, вызовите метод из обработчика событий для события [Microsoft. Office. Interop. PowerPoint. EApplication_Event. афтерпресентатионопен](/previous-versions/office/developer/office-2010/ff762843(v=office.14)) .

## <a name="robust-programming"></a>Отказоустойчивость
 Для простоты в этом примере используется XML-строка, которая определена как локальная переменная в методе. Обычно следует получать XML из внешнего источника, например файла или базы данных.

## <a name="see-also"></a>См. также
- [Общие сведения о пользовательских XML-частях](../vsto/custom-xml-parts-overview.md)
- [Как добавить пользовательские XML-части в настройки уровня документа](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md)
