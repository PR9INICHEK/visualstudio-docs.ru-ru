---
title: 'CA1058: типы не должны расширять определенные базовые типы | Документация Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: d8e267b1e6203759efc91936a3b13059368a3862
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85545396"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058. Типы не должны расширять определенные базовые типы
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Элемент|Значение|
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|Категория|Microsoft. Design|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина
 Видимый извне тип расширяет некоторые базовые типы. В настоящее время это правило сообщает о типах, производных от следующих типов:

- <xref:System.ApplicationException?displayProperty=fullName>

- <xref:System.Xml.XmlDocument?displayProperty=fullName>

- <xref:System.Collections.CollectionBase?displayProperty=fullName>

- <xref:System.Collections.DictionaryBase?displayProperty=fullName>

- <xref:System.Collections.Queue?displayProperty=fullName>

- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

- <xref:System.Collections.SortedList?displayProperty=fullName>

- <xref:System.Collections.Stack?displayProperty=fullName>

## <a name="rule-description"></a>Описание правила
 Для [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] версии 1 рекомендуется создавать новые исключения из <xref:System.ApplicationException> . Рекомендация изменилась, и новые исключения должны быть производными от <xref:System.Exception?displayProperty=fullName> или одного из его подклассов в <xref:System> пространстве имен.

 Не создавайте подкласс класса, <xref:System.Xml.XmlDocument> Если необходимо создать XML-представление базовой объектной модели или источника данных.

### <a name="non-generic-collections"></a>Неуниверсальные коллекции
 По возможности используйте и (или) расширьте универсальные коллекции. Не расширяйте неуниверсальные коллекции в коде, пока вы не отгрузили ее ранее.

 **Примеры неправильного использования**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

 **Примеры правильного использования**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, необходимо создать производный тип от другого базового типа или универсальной коллекции.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Не отключайте предупреждение о нарушении этого правила о нарушениях <xref:System.ApplicationException> . В этом правиле можно отключить вывод предупреждений о нарушениях <xref:System.Xml.XmlDocument> . Можно спокойно отключить предупреждение о неуниверсальной коллекции, если код был выпущен ранее.
