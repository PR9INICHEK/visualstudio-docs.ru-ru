---
title: BP_RESOLUTION_INFO Документы Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_RESOLUTION_INFO
helpviewer_keywords:
- BP_RESOLUTION_INFO structure
ms.assetid: ba0c162a-61e8-4a0b-811f-4c1d8a5d82f0
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 70e66a936ec1eaf1f818ad249aa4eb14b0b63749
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "80737825"
---
# <a name="bp_resolution_info"></a>BP_RESOLUTION_INFO
Описывает информацию о связанной точке разрыва для точки разрыва кода или точки разрыва данных.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct _BP_RESOLUTION_INFO {
    BPRESI_FIELDS          dwFields;
    BP_RESOLUTION_LOCATION bpResLocation;
    IDebugProgram2*        pProgram;
    IDebugThread2*         pThread;
} BP_RESOLUTION_INFO;
```

```csharp
public struct BP_RESOLUTION_INFO {
    public uint                   dwFields;
    public BP_RESOLUTION_LOCATION bpResLocation;
    public IDebugProgram2         pProgram;
    public IDebugThread2          pThread;
};
```

## <a name="members"></a>Участники
`dwFields`\
Коллекция флагов [из BPRESI_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md) перечисления, которая определяет, какие поля заполнены.

`bpResLocation`\
[Структура BP_RESOLUTION_LOCATION,](../../../extensibility/debugger/reference/bp-resolution-location.md) которая определяет местоположение точки разрыва в коде или данных.

`pProgram`\
Объект [IDebugProgram2,](../../../extensibility/debugger/reference/idebugprogram2.md) представляющий приложение, в котором произошла ошибка точки разрыва.

`pThread`\
Объект [IDebugThread2,](../../../extensibility/debugger/reference/idebugthread2.md) представляющий поток, в котором выполняется ошибка точки разрыва.

## <a name="remarks"></a>Примечания
Эта структура возвращается [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md).

## <a name="requirements"></a>Требования
Заголовок: msdbg.h

Название: Microsoft.VisualStudio.Debugger.Interop

Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Структуры и объединения](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)
- [BPRESI_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md)
- [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
