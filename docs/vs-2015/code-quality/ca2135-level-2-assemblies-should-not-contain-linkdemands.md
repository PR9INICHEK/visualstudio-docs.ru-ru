---
title: 'CA2135: сборки уровня 2 не должны содержать LinkDemands | Документация Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: cbb68855832e84150b81c8a8a6fde47bf9433edc
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85547710"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135. Сборки уровня 2 не должны содержать LinkDemands
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Элемент|Значение|
|-|-|
|TypeName|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2135|
|Категория|Microsoft.Security|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина
 Класс или член класса использует <xref:System.Security.Permissions.SecurityAction> в приложении, использующем безопасность уровня 2.

## <a name="rule-description"></a>Описание правила
 Требования LinkDemand являются устаревшими в наборе правил безопасности уровня 2. Вместо использования LinkDemand для обеспечения безопасности во время JIT-компиляции пометьте методы, типы и поля <xref:System.Security.SecurityCriticalAttribute> атрибутом.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, удалите <xref:System.Security.Permissions.SecurityAction> и пометьте тип или член <xref:System.Security.SecurityCriticalAttribute> атрибутом.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Для этого правила отключать вывод предупреждений не следует.

## <a name="example"></a>Пример
 В следующем примере <xref:System.Security.Permissions.SecurityAction> следует удалить и метод, помеченный <xref:System.Security.SecurityCriticalAttribute> атрибутом.

 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2135.securityrulesetlevel2methodsshouldnotbeprotectedwithlinkdemands/cs/ca2135.cs#1)]
