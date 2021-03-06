---
title: Конструктор действий отправки конструктор рабочих процессов
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.Send.UI
ms.assetid: b514f2e4-767c-4b94-ac61-dd3a54d4b96d
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dd1eff0a52dfb258d7f7af49b03543fd741bc88c
ms.sourcegitcommit: 186c0c250d85ac74274fa1e438b4c7c7108d8a36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86875960"
---
# <a name="send-activity-designer"></a>Конструктор действия Send

Конструктор действий **отправки** используется для создания и настройки <xref:System.ServiceModel.Activities.Send> действия.

## <a name="the-send-activity"></a>Действие Send

 Действие <xref:System.ServiceModel.Activities.Send> предназначено для отправки сообщения службе. Действие <xref:System.ServiceModel.Activities.ReceiveReply> может быть привязано к действию <xref:System.ServiceModel.Activities.Send>, которое получает сообщение в процессе обмена сообщениями по шаблону «запрос-ответ» на стороне клиента.

### <a name="using-the-send-activity-designer"></a>Использование конструктора действия Send

Доступ к конструктору действий **отправки** в категории **Обмен сообщениями** **панели элементов**. Конструктор действий **отправки** можно перетащить из **панели элементов** в конструктор рабочих процессов область, где обычно размещаются действия. Будет создано действие <xref:System.ServiceModel.Activities.Send> со значением по умолчанию <xref:System.Activities.Activity.DisplayName%2A> Send. <xref:System.Activities.Activity.DisplayName%2A>Можно изменить в заголовке конструктора действий **отправки** или в поле **DisplayName** сетки свойств.

Чтобы создать <xref:System.ServiceModel.Activities.ReceiveReply> действие и привязать его к выбранному <xref:System.ServiceModel.Activities.Send> действию, щелкните правой кнопкой мыши конструктор действий **отправки** , в контекстном меню щелкните **создать элемент ReceiveReply** , и конструктор **рецеивереплифорсенд** появится под конструктором **отправки** . Действие <xref:System.ServiceModel.Activities.ReceiveReply> получает сообщение в процессе обмена сообщениями по шаблону «запрос-ответ» на стороне клиента. Его можно настроить с помощью конструктора **рецеивереплифорсенд** .

Кроме того, конструктор шаблонов **SendAndReceiveReply** в категории **сообщений** **панели элементов** можно использовать для создания пары предварительно настроенных <xref:System.ServiceModel.Activities.Send> <xref:System.ServiceModel.Activities.ReceiveReply> действий и. Дополнительные сведения об использовании шаблонов **SendAndReceiveReply** и **рецеивереплифорсенд** см. в разделе [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) .

### <a name="the-send-activity-properties"></a>Свойства действия Send

В следующей таблице показаны свойства <xref:System.ServiceModel.Activities.Send> и описано их использование в конструкторе. Эти свойства можно изменять в сетке свойств или на конструктор рабочих процессов поверхности.

| Имя свойства | Обязательно | Использование |
|-|----------|-|
| <xref:System.Activities.Activity.DisplayName%2A> | Неверно | Понятное имя действия <xref:System.ServiceModel.Activities.Send>. Значение по умолчанию - Send. Несмотря на то что свойство <xref:System.Activities.Activity.DisplayName%2A> не является обязательным, его все же рекомендуется использовать. |
| <xref:System.ServiceModel.Activities.Send.OperationName%2A> | Да | Имя операции службы, вызываемой этим действием <xref:System.ServiceModel.Activities.Send>. Это свойство используется для создания значения по умолчанию для свойства **Action** , если свойство **Action** не задано явно. |
| <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> | Да | Имя контракта службы, который реализуется вызываемой службой. |
| <xref:System.ServiceModel.Activities.Send.Content%2A> | Неверно | Указывает получаемое содержимое сообщения или параметра. Это может быть либо действие <xref:System.ServiceModel.Activities.ReceiveMessageContent>, либо действие <xref:System.ServiceModel.Activities.ReceiveParametersContent>. Измените это свойство, нажав кнопку с многоточием рядом с полем **содержимое** в сетке свойств или нажав кнопку **определить...** рядом с меткой **содержимого** в области конструктора действий **получения** . В обоих окнах отображается диалоговое окно **определения содержимого** . Дополнительные сведения об использовании этого поля см. в разделе [диалогового окна «Определение содержимого](../workflow-designer/content-definition-dialog-box.md) ». |
| <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> | Неверно | Задает метод <xref:System.ServiceModel.Activities.CorrelationHandle>, используемый для перенаправления сообщения в соответствующий экземпляр рабочего процесса.<br /><br /> Нажмите кнопку с многоточием рядом со <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> свойством в сетке свойства, чтобы открыть диалоговое окно **Редактор выражений** . Дополнительные сведения об использовании этого диалогового окна см. в разделе [инструкции. Использование редактора выражений](../workflow-designer/how-to-use-the-expression-editor.md) . |
| <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> | Неверно | Указывает коллекцию объектов <xref:System.ServiceModel.Activities.CorrelationInitializer>, инициализирующих несколько объектов <xref:System.ServiceModel.Activities.CorrelationHandle>, которые настраивают это действие <xref:System.ServiceModel.Activities.Send> в рамках рабочего процесса. Нажмите кнопку с многоточием рядом со <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> свойством в сетке свойства, чтобы открыть диалоговое окно **Добавление инициализаторов корреляции** . Дополнительные сведения об использовании этого поля см. в разделе « [Добавление CorrelationInitializers в диалоговом окне](../workflow-designer/add-correlationinitializers-dialog-box.md) ». |
| <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> | Неверно | Коллекция известных типов для операции службы, вызываемой этим действием <xref:System.ServiceModel.Activities.Send>. Это свойство должно использоваться вместе со свойством <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>, установленным в значение <xref:System.Runtime.Serialization.DataContractSerializer>. Не учитывается, если используется <xref:System.Xml.Serialization.XmlSerializer>.<br /><br /> Нажмите кнопку с многоточием рядом с полем **кновнтипес** в сетке свойств, чтобы открыть диалоговое окно **Редактор коллекции типов** , в котором можно добавить соответствующие типы.<br /><br /> Нажмите кнопку с многоточием рядом с полем **кновнтипес** в сетке свойств, чтобы открыть диалоговое окно **Редактор коллекции типов** , в котором можно добавить соответствующие типы. Дополнительные сведения об использовании этого поля см. в разделе [диалогового окна Редактор коллекции типов](../workflow-designer/type-collection-editor-dialog-box.md) . |
| <xref:System.ServiceModel.Activities.Send.ProtectionLevel%2A> | Да | Задает <xref:System.Net.Security.ProtectionLevel> для сообщения.<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> обозначает только проверку подлинности.<br />2. <xref:System.Net.Security.ProtectionLevel> означает подписывание данных для обеспечения целостности передаваемых данных.<br />3. <xref:System.Net.Security.ProtectionLevel> означает шифрование и подписывание данных для обеспечения конфиденциальности и целостности передаваемых данных. |
| <xref:System.ServiceModel.Activities.Send.SerializerOption%2A> | Да | Сериализатор, используемый для этой операции службы, вызываемой действием <xref:System.ServiceModel.Activities.Send>. Значение по умолчанию - <xref:System.Runtime.Serialization.DataContractSerializer>, при котором производится сериализация и десериализация экземпляра типа в XML-поток или документ с использованием переданного контракта данных. |
| <xref:System.ServiceModel.Activities.Send.Action%2A> | Неверно | Указывает заголовок действия сообщения. Если параметр не задан явно, его значение по умолчанию равно: `https://tempuri.org/{service contract namespace}/{service contract name}/{operation name}` . Если задано для действия <xref:System.ServiceModel.Activities.Send>, то для успешной доставки сообщения действие <xref:System.ServiceModel.Activities.Receive>, принимающее сообщение, должно иметь то же значение. |
| <xref:System.ServiceModel.Activities.Send.TokenImpersonationLevel%2A> | | <xref:System.Security.Principal.TokenImpersonationLevel>, допустимое для получателя сообщения. Он определяет уровни олицетворения безопасности, определяющие степень, до которой серверный процесс может выполнять от имени клиентского процесса.<xref:System.Security.Principal.TokenImpersonationLevel>  указывает, что уровень олицетворения не назначается. <xref:System.Security.Principal.TokenImpersonationLevel>Указывает, что серверный процесс не может получить идентификационную информацию о клиенте и не может олицетворить клиента. <xref:System.Security.Principal.TokenImpersonationLevel>Указывает, что серверный процесс может получать сведения о клиенте, например идентификаторы безопасности и привилегии, но не может олицетворять клиента. Это может оказаться полезным в том случае, если сервер экспортирует свои собственные объекты, например базы данных, из которых экспортируются таблицы и представления. Используя полученную информацию безопасности клиента, сервер может принимать решения в отношении проверки доступа, не имея возможности применять другие службы, использующие контекст безопасности клиента. <xref:System.Security.Principal.TokenImpersonationLevel>Указывает, что серверный процесс может олицетворять контекст безопасности клиента в своей локальной системе. Олицетворение клиента сервером в удаленных системах невозможно. <xref:System.Security.Principal.TokenImpersonationLevel>Указывает, что серверный процесс может олицетворять контекст безопасности клиента в удаленных системах. |
| <xref:System.ServiceModel.Activities.Send.Endpoint%2A> | | <xref:System.ServiceModel.Endpoint>, которому действие <xref:System.ServiceModel.Activities.Send> отправляет сообщение. Если это свойство установлено, <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> свойство должно иметь **значение NULL**. |
| <xref:System.ServiceModel.Activities.Send.EndpointAddress%2A> | | <xref:System.ServiceModel.EndpointAddress>, которому направляется сообщение. |
| <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> | | Имя конфигурации конечной точки. Это свойство задается при настройке конечной точки в файле конфигурации. Этому свойству должно быть присвоено имя, заданное в **\<endpoint>** элементе в файле конфигурации. Если это свойство задано, <xref:System.ServiceModel.Activities.Send.Endpoint%2A> свойство должно иметь **значение NULL**. |

## <a name="see-also"></a>См. также раздел

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Получать](../workflow-designer/receive-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)