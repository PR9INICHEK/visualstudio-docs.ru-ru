---
title: 'CA2104: не объявляйте изменяемые ссылочные типы только для чтения | Документация Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotDeclareReadOnlyMutableReferenceTypes
- CA2104
helpviewer_keywords:
- CA2104
- DoNotDeclareReadOnlyMutableReferenceTypes
ms.assetid: 81b83ee5-4db5-4be0-9f8d-90b53894ec3b
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: ff42cc2b8543fe8e1cf980a3574ae15922febf9b
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85521047"
---
# <a name="ca2104-do-not-declare-read-only-mutable-reference-types"></a>CA2104. Не объявляйте изменяющиеся ссылочные типы только для чтения
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Элемент|Значение|
|-|-|
|TypeName|DoNotDeclareReadOnlyMutableReferenceTypes|
|CheckId|CA2104|
|Категория|Microsoft.Security|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина
 Видимый извне тип содержит видимое извне и доступное только для чтение поле, являющееся изменяемым ссылочным типом.

## <a name="rule-description"></a>Описание правила
 Изменяемый тип — это тип, экземпляр которого может быть изменен. <xref:System.Text.StringBuilder?displayProperty=fullName>Класс является примером изменяемого ссылочного типа. Он содержит члены, которые могут изменять значение экземпляра класса. Примером неизменяемого ссылочного типа является <xref:System.String?displayProperty=fullName> класс. После создания экземпляра его значение не может изменяться.

 Модификатор только для чтения ([ReadOnly](https://msdn.microsoft.com/library/2f8081f6-0de2-4903-898d-99696c48d2f4) в C#, [ReadOnly](https://msdn.microsoft.com/library/e868185d-6142-4359-a2fd-a7965cadfce8) in [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] и [const](https://msdn.microsoft.com/library/b21c0271-1ad0-40a0-b21c-5e812bba0318) в c++) для поля ссылочного типа (указатель в c++) предотвращает замену поля другим экземпляром ссылочного типа. Однако модификатор не предотвращает изменение данных экземпляра поля с помощью ссылочного типа.

 Поля массива, доступные только для чтения, исключаются из этого правила, но это приводит к нарушению работы [полей CA2105: Array не должно быть](../code-quality/ca2105-array-fields-should-not-be-read-only.md) правилом только для чтения.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, удалите модификатор "только для чтения" или, если критическое изменение допустимо, замените поле неизменяемым типом.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Можно отключить вывод предупреждений из этого правила, если тип поля является неизменяемым.

## <a name="example"></a>Пример
 В следующем примере показано объявление поля, которое вызывает нарушение этого правила.

 [!code-cpp[FxCop.Security.MutableReferenceTypes#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Security.MutableReferenceTypes/cpp/FxCop.Security.MutableReferenceTypes.cpp#1)]
 [!code-csharp[FxCop.Security.MutableReferenceTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.MutableReferenceTypes/cs/FxCop.Security.MutableReferenceTypes.cs#1)]
 [!code-vb[FxCop.Security.MutableReferenceTypes#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Security.MutableReferenceTypes/vb/FxCop.Security.MutableReferenceTypes.vb#1)]
