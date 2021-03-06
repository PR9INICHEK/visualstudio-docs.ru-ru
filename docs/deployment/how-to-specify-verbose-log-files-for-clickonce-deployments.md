---
title: Как указать подробные файлы журнала для развертываний ClickOnce | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- logs, ClickOnce deployment
- ClickOnce deployment, logging
ms.assetid: 0807a28d-2e40-4a51-ab10-308d808ded6b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1e1d2ca7c58d7da85ad67e56eae7713e517a1d2c
ms.sourcegitcommit: 3f491903e0c10db9a3f3fc0940f7b587fcbf9530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85381773"
---
# <a name="how-to-specify-verbose-log-files-for-clickonce-deployments"></a>Практическое руководство. Указание подробных файлов журнала для развертывания ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]поддерживает файлы журналов действий для всех развертываний. В этих журналах содержатся сведения, относящиеся к установке, инициализации, обновлению и удалению [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] развертывания. Чтобы увеличить детализацию [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] записи в эти файлы журнала, используйте редактор реестра (*regedit.exe*), чтобы указать уровень детализации.

> [!CAUTION]
> Неправильное использование редактора реестра может привести к серьезным проблемам, которые могут потребовать переустановки операционной системы. Используйте редактор реестра на свой страх и риск.

 Следующая процедура описывает, как указать уровень детализации для [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] файлов журнала для текущего пользователя. Чтобы уменьшить уровень детализации, удалите это значение реестра.

### <a name="to-specify-verbose-log-files"></a>Указание подробных файлов журнала

1. Откройте *Regedit.exe*.

2. Перейдите к узлу **HKEY_CURRENT_USER \софтваре\классес\софтваре\микрософт\виндовс\куррентверсион\деплоймент**.

3. При необходимости создайте новое строковое значение с именем `LogVerbosityLevel` .

4. Установите для `LogVerbosityLevel` значение `1`.

## <a name="see-also"></a>См. также
- [Устранение неполадок развертываний ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)