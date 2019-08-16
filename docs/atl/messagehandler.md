---
title: MessageHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: aa044ef88ba3c872c2652cd774ac50024e52c68c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492311"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler`имя функции, определяемой вторым параметром макроса MESSAGE_HANDLER в схеме сообщений.

## <a name="syntax"></a>Синтаксис

```
LRESULT MessageHandler(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>Параметры

*Uiacp*<br/>
Указывает сообщение.

*wParam*<br/>
Дополнительные сведения, относящиеся к конкретному сообщению.

*lParam*<br/>
Дополнительные сведения, относящиеся к конкретному сообщению.

*бхандлед*<br/>
Схема сообщений устанавливает для *бхандлед* значение true перед `MessageHandler` вызовом метода. Если `MessageHandler` не полностью обрабатывает сообщение, необходимо установить *бхандлед* в значение false, чтобы указать, что сообщение требует дальнейшей обработки.

## <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщения. 0 в случае успеха.

## <a name="remarks"></a>Примечания

Пример использования этого обработчика сообщений в схеме сообщений см. в разделе [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler).

## <a name="see-also"></a>См. также

[Реализация окна](../atl/implementing-a-window.md)<br/>
[Схемы сообщений](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
