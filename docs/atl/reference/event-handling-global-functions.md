---
title: Глобальные функции для обработки событий
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
ms.openlocfilehash: bb109c63b497420ad6e797cd8e0b366ce4dc0475
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57292228"
---
# <a name="event-handling-global-functions"></a>Глобальные функции для обработки событий

Эта функция предоставляет обработчик событий.

> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.

|||
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Ожидает объекта сигнала, в то же время диспетчеризации сообщений окна, при необходимости.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="atlwaitwithmessageloop"></a>  AtlWaitWithMessageLoop

Ожидает объекта, о котором требуется сигнализировать; во время ожидания производит требуемую диспетчеризацию сообщений.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>Параметры

*hEvent*<br/>
[in] Дескриптор объекта ожидания.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объект оповещении.

### <a name="remarks"></a>Примечания

Это полезно в том случае, если вы хотите ждать события объекта, и получать оповещения о них происходит, но разрешить окно сообщения для отправки во время ожидания.

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
