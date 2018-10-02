---
title: 'Практическое: использование точек останова в XSLT | Документация Майкрософт'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf7bbc2c-71dc-4cac-a6fc-add6b27d92ed
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 30ddb1fa8d56a55c5fc7a9811e4c836cabe4da0c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47561699"
---
# <a name="how-to-use-breakpoints-with-xslt"></a>Практическое руководство. Использование точек останова в XSLT
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Точки останова можно задать в таблице стилей XSLT или в исходном XML-документе. Если задать точку останова на теге, то при выполнении точка останова переходит к следующему оператору, у которого есть сведения исходной строки.  
  
 Дополнительные сведения см. в разделе [основы отладки: точки останова](http://msdn.microsoft.com/en-us/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e).  
  
## <a name="set-a-breakpoint-in-a-style-sheet"></a>Задание точки останова в таблице стилей  
 Точки останова можно задать на открывающих тегах, закрывающих тегах и текстовых узлах таблицы стилей XSLT. Точки останова можно также задать в коде блока скрипта.  
  
#### <a name="to-set-a-breakpoint-in-a-style-sheet"></a>Задание точки останова в таблице стилей  
  
1.  Откройте таблицу стилей в редакторе XML.  
  
2.  Поместите курсор в точке останова, щелкните правой кнопкой мыши, укажите **точки останова**и нажмите кнопку **вставить точку останова**.  
  
3.  Нажмите кнопку обзора (**...** ) на **ввода** поле из окна свойств документа.  
  
4.  Найдите исходный XML-документ и нажмите кнопку **откройте**.  
  
     Таким образом задается файл исходного документа, используемого в XSLT-преобразовании.  
  
5.  Нажмите кнопку **Отладка XSL** кнопки на панели инструментов редактора XML.  
  
## <a name="set-a-breakpoint-in-an-xml-source-document"></a>Задание точки останова в исходном XML-документе   
 В исходном XML-документе точки останова можно задать на элементах, атрибутах, узле пространства имен, комментариях, инструкции по обработке и текстовых узлах исходного XML-документа. Невозможно задать точку останова на узле документа или на узле пространства имен, который наследуется от родительского элемента.  
  
#### <a name="to-set-a-breakpoint-in-an-xml-source-document"></a>Задание точки останова в исходном XML-документе   
  
1.  Откройте XML-документ в XML-редакторе.  
  
2.  Поместите курсор в точке останова, щелкните правой кнопкой мыши, укажите **точки останова**и нажмите кнопку **вставить точку останова**.  
  
3.  Нажмите кнопку обзора (**...** ) на **таблицы стилей** поле из окна свойств документа.  
  
4.  Найдите исходный XML-документ и нажмите кнопку **откройте**.  
  
     Таким образом задается файл исходного документа, используемого в XSLT-преобразовании.  
  
5.  Нажмите кнопку **Отладка XSL** кнопки на панели инструментов редактора XML.  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство: отладка таблицы стилей XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)
