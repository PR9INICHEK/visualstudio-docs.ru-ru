---
title: 'CA1500: имена переменных не должны совпадать с именами полей | Документация Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
caps.latest.revision: 25
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 9565bc1ae3166c0475e8af7f0fde381497309b01
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85547918"
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500. Имена переменных не должны совпадать с именами полей
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю документацию по Visual Studio см. в разделе [CA1500: имена переменных не должны совпадать с именами полей](/visualstudio/code-quality/ca1500-variable-names-should-not-match-field-names).

|Item|Значение|
|-|-|
|TypeName|VariableNamesShouldNotMatchFieldNames|
|CheckId|CA1500|
|Категория|Поддержка Microsoft.|
|Критическое изменение|При срабатывании параметра, имя которого совпадает с именем поля:<br /><br /> -Не критическое — если и поле, и метод, объявляющий параметр, не видны за пределами сборки, независимо от внесенных изменений.<br />— Критическое — при изменении имени поля, которое может отображаться за пределами сборки.<br />-Критическое — если изменить имя параметра, а метод, объявляющий его, может просматриваться за пределами сборки.<br /><br /> При срабатывании в локальной переменной, имя которой совпадает с именем поля:<br /><br /> — Не критическое — если поле не отображается за пределами сборки, независимо от внесенных изменений.<br />— Не критическое — если изменяется имя локальной переменной и не изменяется имя поля.<br />-Критическое. Если изменить имя поля, оно может отображаться за пределами сборки.|

## <a name="cause"></a>Причина
 Метод экземпляра объявляет параметр или локальную переменную, имя которой соответствует полю экземпляра объявляющего типа. Для перехвата локальных переменных, нарушающих правило, проверенная сборка должна быть построена с помощью отладочной информации, а соответствующий файл базы данных программы (PDB) должен быть доступен.

## <a name="rule-description"></a>Описание правила
 Если имя поля экземпляра совпадает с именем параметра или локальной переменной, доступ к полю экземпляра осуществляется с помощью `this` `Me` [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ключевого слова (in) в теле метода. При сохранении кода можно легко забыть это различие и предположить, что параметр/локальная переменная ссылается на поле экземпляра, что приводит к ошибкам. Это справедливо особенно для длинных тела методов.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, переименуйте параметр или переменную или поле.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Для этого правила отключать вывод предупреждений не следует.

## <a name="example"></a>Пример
 В следующем примере показаны два нарушения правила.

 [!code-csharp[FxCop.Maintainability.VarMatchesField#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Maintainability.VarMatchesField/cs/FxCop.Maintainability.VarMatchesField.cs#1)]
 [!code-vb[FxCop.Maintainability.VarMatchesField#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Maintainability.VarMatchesField/vb/FxCop.Maintainability.VarMatchesField.vb#1)]
