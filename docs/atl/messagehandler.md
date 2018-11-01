---
title: MessageHandler
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MessageHandler
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: 3627dadde60a5ba0ece90497b85e2085f33e0919
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448403"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler` — имя функции, заданных в качестве второго параметра макроса MESSAGE_HANDLER в схему сообщения.

## <a name="syntax"></a>Синтаксис

```
LRESULT MessageHandler(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>Параметры

*uMsg*<br/>
Задает сообщение.

*wParam*<br/>
Дополнительные сведения, относящиеся к сообщению.

*lParam*<br/>
Дополнительные сведения, относящиеся к сообщению.

*bHandled*<br/>
Карта наборов сообщений *bHandled* значение TRUE перед `MessageHandler` вызывается. Если `MessageHandler` не полностью обрабатывает сообщение, она должна задать *bHandled* значение false, чтобы указать, должна дальнейшей обработки сообщения.

## <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщения. 0 в случае успеха.

## <a name="remarks"></a>Примечания

Пример использования этого обработчика сообщений в схеме сообщений, см. в разделе [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler).

## <a name="see-also"></a>См. также

[Реализация окна](../atl/implementing-a-window.md)<br/>
[Схемы сообщений](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)
