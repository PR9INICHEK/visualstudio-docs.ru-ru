---
title: Конструктор действий конструктор рабочих процессов TransactedReceiveScope
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.TransactedReceiveScope.UI
ms.assetid: 7ca93aad-4e83-4d81-90f4-998ee114d9b6
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 75fb1da392bce7dbd0cd7849d83b3b452521e0c7
ms.sourcegitcommit: 186c0c250d85ac74274fa1e438b4c7c7108d8a36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86875934"
---
# <a name="transactedreceivescope-activity-designer"></a>Конструктор действия TransactedReceiveScope

Конструктор **TransactedReceiveScope** используется для создания и настройки <xref:System.ServiceModel.Activities.TransactedReceiveScope> действия.

## <a name="the-transactedreceivescope-activity"></a>Действие TransactedReceiveScope

Действие <xref:System.ServiceModel.Activities.TransactedReceiveScope> позволяет передать транзакцию в состав транзакций сервера, созданных рабочим процессом или диспетчером.

### <a name="using-the-transactedreceivescope-activity-designer"></a>Использование конструктора операций TransactedReceiveScope

Доступ к конструктору действий **TransactedReceiveScope** в категории **обмена сообщениями** **панели элементов**. Конструктор действий **TransactedReceiveScope** можно перетащить из **панели элементов** в область Конструктор рабочих процессов, где обычно размещаются действия. При этом создается <xref:System.ServiceModel.Activities.TransactedReceiveScope> действие со значением **DisplayName** по умолчанию TransactedReceiveScope. <xref:System.Activities.Activity.DisplayName%2A>Можно изменить в заголовке конструктора действий **TransactedReceiveScope** или в поле **DisplayName** сетки свойств.

Конструктор **TransactedReceiveScope** содержит поля " **запрос** " и " **текст** ". Они используются для настройки свойства <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>, задающего действие <xref:System.ServiceModel.Activities.Receive> и свойство <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>, которое задает другое действие <xref:System.Activities.Activity>. Свойство <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> создает транзакцию. Затем транзакция определяется как внешняя для области <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>, так что любое действие в области выполняется внутри данной транзакции.

### <a name="the-transactedreceivescope-properties"></a>Свойства TransactedReceiveScope

В следующей таблице показаны свойства <xref:System.ServiceModel.Activities.TransactedReceiveScope> и описано их использование в конструкторе. Это <xref:System.Activities.Activity.DisplayName%2A> свойство можно изменить в сетке свойств или на конструктор рабочих процессов поверхности, но другие должны быть изменены в области конструктора.

|Имя свойства|Обязательно|Использование|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|Неверно|Необязательное понятное имя действия <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Значение по умолчанию - TransactedReceiveScope.<br /><br /> Для имени <xref:System.Activities.Activity.DisplayName%2A> нет жестких требований, однако лучше всего использовать отображаемое имя.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>|Да|Удаляет <xref:System.ServiceModel.Activities.Receive> действие в блоке **запроса** на поверхности конструктора операций.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>|Неверно|Удаляет объект <xref:System.Activities.Activity> в блоке **тела** в области конструктора действий.|

## <a name="see-also"></a>См. также раздел

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Получать](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Отправить](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)