---
title: Синхронизация наборов правил проекта с политикой возврата
ms.date: 11/04/2016
ms.topic: how-to
f1_keywords:
- vs.codeanalysis.selecttfsruleset
ms.assetid: 9b02f934-2db6-41ec-aaff-9c31ceec2f04
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5e27987f7fa298ddcedf52a9f01a80f57d3d329f
ms.sourcegitcommit: 48e93538f1e352fc1f972b642bb5fcce2f6834a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2020
ms.locfileid: "85371785"
---
# <a name="how-to-synchronize-code-project-rule-sets-with-an-azure-devops-project-check-in-policy"></a>Как синхронизировать наборы правил проекта кода с политикой возврата проекта Azure DevOps

Вы синхронизируете параметры анализа кода для проектов кода с политикой возврата для проекта Azure DevOps, указывая набор правил, содержащий по крайней мере правила, указанные в наборе правил для политики возврата. Руководитель разработчика может сообщить имя и расположение набора правил для политики возврата. Чтобы убедиться в том, что для анализа кода проекта используется правильный набор правил, можно использовать один из следующих параметров:

- Если политика возврата использует один из встроенных наборов правил Майкрософт, откройте диалоговое окно Свойства для проекта кода, отобразите страницу анализ кода и выберите набор правил. Стандартные наборы правил Майкрософт автоматически устанавливаются вместе с Visual Studio и не должны редактироваться. Если наборы правил не редактируются, то правила в политике и локальных наборах правил гарантированно совпадают.

- Если политика возврата использует настраиваемый набор правил, выполните операцию Get с файлом набора правил в системе управления версиями, чтобы создать локальную копию. Затем укажите это локальное расположение в параметрах анализа кода для проекта кода. Правила гарантированно сопоставлены, если набор правил для политики возврата обновлен.

     При сопоставлении расположения системы управления версиями с локальной папкой, которая находится в той же связи с корнем проекта Azure DevOps, что и проект кода, расположение правила устанавливается с использованием относительного пути. Относительный путь гарантирует, что параметр проекта кода для анализа кода можно будет переместить на другие компьютеры.

- Настройте копию набора правил для политики возврата для проекта кода. Убедитесь, что новый набор правил содержит все правила в политике возврата, а также другие правила, которые необходимо включить. Необходимо убедиться, что набор правил включает все правила в наборе правил для политики возврата.

## <a name="to-specify-a-microsoft-standard-rule-set"></a>Указание набора стандартных правил Майкрософт

1. В **Обозреватель решений**щелкните правой кнопкой мыши проект кода и выберите пункт **свойства**.

2. Щелкните **Анализ кода**.

::: moniker range="vs-2017"

3. В списке **выполнить этот набор правил** выберите набор правил политики возврата.

::: moniker-end

::: moniker range=">=vs-2019"

3. В списке **активные правила** выберите набор правил политики возврата.

::: moniker-end

## <a name="to-specify-a-custom-check-in-policy-rule-set"></a>Указание пользовательского набора правил политики возврата

1. При необходимости выполните операцию Get с файлом набора правил, который указывает политику возврата.

2. В **Обозреватель решений**щелкните правой кнопкой мыши проект кода и выберите пункт **свойства**.

3. Щелкните **Анализ кода**.

::: moniker range="vs-2017"

4. В списке **выполнить этот набор правил** нажмите кнопку **\<Browse>** .

::: moniker-end

::: moniker range=">=vs-2019"

4. В списке **активные правила** щелкните **\<Browse>** .

::: moniker-end

5. В диалоговом окне **Открыть** укажите файл набора правил политики возврата.

## <a name="to-create-a-custom-rule-set-for-a-code-project"></a>Создание настраиваемого набора правил для проекта кода

Сведения о создании настраиваемого набора правил см. [в разделе Настройка набора правил](how-to-create-a-custom-rule-set.md).
