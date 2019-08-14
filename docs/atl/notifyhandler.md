---
title: NotifyHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
ms.openlocfilehash: d875a039b01b7458a1df46a2539cf5c68aa67e41
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915935"
---
# <a name="notifyhandler"></a>NotifyHandler

Имя функции, определяемой третьим параметром макроса NOTIFY_HANDLER в схеме сообщений.

## <a name="syntax"></a>Синтаксис

```cpp
LRESULT NotifyHandler(
    int idCtrl,
    LPNMHDR pnmh,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Параметры

*идктрл*<br/>
Идентификатор элемента управления, отправляющего сообщение.

*пнмх*<br/>
Адрес структуры [NMHDR](/windows/desktop/api/richedit/ns-richedit-nmhdr) , содержащей код уведомления и дополнительные сведения. Для некоторых сообщений с уведомлениями этот параметр указывает на большую структуру, в `NMHDR` которой структура является первым элементом.

*бхандлед*<br/>
Схема сообщений устанавливает для *бхандлед* значение true перед вызовом *нотифихандлер* . Если *нотифихандлер* не обрабатывает сообщение полностью, ему следует присвоить параметру *бхандлед* значение **false** , чтобы указать, что сообщение требует дальнейшей обработки.

## <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщения. 0 в случае успеха.

## <a name="remarks"></a>Примечания

Пример использования этого обработчика сообщений в схеме сообщений см. в разделе [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).

## <a name="see-also"></a>См. также

[Реализация окна](../atl/implementing-a-window.md)<br/>
[Схемы сообщений](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/desktop/controls/wm-notify)
