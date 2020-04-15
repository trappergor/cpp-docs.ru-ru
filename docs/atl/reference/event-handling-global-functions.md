---
title: Обработка событий глобальных функций
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
ms.openlocfilehash: f2f8269dcf0f59a5d0794d3f16d4c4f85d8841ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330134"
---
# <a name="event-handling-global-functions"></a>Обработка событий глобальных функций

Эта функция обеспечивает обработчик событий.

> [!IMPORTANT]
> Функция, указанная в следующей таблице, не может использоваться в приложениях, выполняющих в Windows Runtime.

|||
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Ожидает сигнализировать объект, тем временем отправляя оконные сообщения по мере необходимости.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atlwaitwithmessageloop"></a><a name="atlwaitwithmessageloop"></a>AtlWaitWithMessageLoop

Ожидает объекта, о котором требуется сигнализировать; во время ожидания производит требуемую диспетчеризацию сообщений.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>Параметры

*hEvent*<br/>
(в) Ручку объекта ждать.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если объект был сигнализирован.

### <a name="remarks"></a>Remarks

Это полезно, если вы хотите дождаться события объекта и получить уведомление о его возникновении, но разрешить отправку сообщений окон во время ожидания.

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)
