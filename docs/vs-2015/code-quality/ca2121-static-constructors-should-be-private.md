---
title: 'CA2121: статические конструкторы должны быть частными | Документация Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
helpviewer_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
ms.assetid: ee93c620-8fc1-4e47-866c-d389c3ca9f2e
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 7f95b33e1391ca755a6c0df261fa2bd05bd3c7a0
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85544317"
---
# <a name="ca2121-static-constructors-should-be-private"></a>CA2121. Статические конструкторы должны быть частными
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Элемент|Значение|
|-|-|
|TypeName|StaticConstructorsShouldBePrivate|
|CheckId|CA2121|
|Категория|Microsoft.Security|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина
 Тип имеет статический конструктор, который не является закрытым.

## <a name="rule-description"></a>Описание правила
 Статический конструктор, также известный как конструктор класса, используется для инициализации типа. Система вызывает статический конструктор перед созданием первого экземпляра типа или ссылкой на любые статические члены. Пользователь не может управлять при вызове статического конструктора. Если статический конструктор не является закрытым, он может быть вызван кодом, находящимся за пределами системы. В зависимости от операций, выполняемых в конструкторе, это может стать причиной непредвиденного поведения

 Это правило применяется в C# и Visual Basic компиляторах .NET.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Нарушения обычно вызываются одним из следующих способов:

- Вы определили статический конструктор для вашего типа и не сделали его частным.

- Компилятор языка программирования добавил к типу статический конструктор по умолчанию и не сделал его частным.

  Чтобы устранить нарушение первого типа, сделайте статический конструктор закрытым. Чтобы исправить второй тип, добавьте закрытый статический конструктор в тип.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Не следует отключать эти нарушения. Если для разработки программного обеспечения требуется явный вызов статического конструктора, то вполне вероятно, что проект содержит серьезные недостатки и должен быть проверен.
