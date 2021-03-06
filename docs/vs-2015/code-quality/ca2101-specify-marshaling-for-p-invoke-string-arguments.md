---
title: 'CA2101: укажите маршалирование для строковых аргументов P-Invoke | Документация Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyMarshalingForPInvokeStringArguments
- CA2101
helpviewer_keywords:
- CA2101
- SpecifyMarshalingForPInvokeStringArguments
ms.assetid: 9d1abfc3-d320-41e0-9f6e-60cefe6ffe1b
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: ae65e922d1b4946300155bbf148abac574a2ec2a
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85544382"
---
# <a name="ca2101-specify-marshaling-for-pinvoke-string-arguments"></a>CA2101: укажите тип маршалинга для строковых аргументов P/Invoke
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Item|Значение|
|-|-|
|TypeName|SpecifyMarshalingForPInvokeStringArguments|
|CheckId|CA2101|
|Категория|Microsoft. Globalization|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина
 Член неуправляемого кода допускает частично доверенные вызывающие объекты, имеет строковый параметр и не маршалирует строку явным образом.

## <a name="rule-description"></a>Описание правила
 При преобразовании из Юникода в ANSI возможно, что не все символы Юникода могут быть представлены в определенной кодовой странице ANSI. *Наилучшее сопоставление* пытается решить эту проблему, подставив символ для символа, который не может быть представлен. Использование этой функции может вызвать потенциальную уязвимость системы безопасности, поскольку нельзя управлять выбранным символом. Например, вредоносный код может намеренно создать строку в Юникоде, содержащую символы, не найденные в определенной кодовой странице, которые преобразуются в специальные символы файловой системы, такие как ".." или '/'. Обратите внимание, что проверки безопасности для специальных символов часто возникают перед преобразованием строки в ANSI.

 Для неуправляемого преобразования по умолчанию используется наилучшее соответствие, WChar — МБ. Если явно не отключить сопоставление наилучшего соответствия, код может содержать уязвимость системы безопасности, которую можно использовать злоумышленником.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, явно маршалировать строковые типы данных.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Для этого правила отключать вывод предупреждений не следует.

## <a name="example"></a>Пример
 В следующем примере показан метод, нарушающий это правило, а затем показано, как устранить нарушение.

 [!code-csharp[FxCop.Security.PinvokeAnsiUnicode#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.PinvokeAnsiUnicode/cs/FxCop.Security.PinvokeAnsiUnicode.cs#1)]
