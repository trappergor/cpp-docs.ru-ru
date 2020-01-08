---
title: Получение уведомления от стандартных элементов управления
ms.date: 11/04/2016
helpviewer_keywords:
- OnNotify method [MFC]
- common controls [MFC], notifications
- ON_NOTIFY macro [MFC]
- controls [MFC], notifications
- receiving notifications from common controls
- notifications [MFC], common controls
- Windows common controls [MFC], notifications
- WM_NOTIFY message
ms.assetid: 50194592-d60d-44d0-8ab3-338a2a2c63e7
ms.openlocfilehash: 73315d4a1107204bc6adc885729fdeeaeb7f98d0
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298978"
---
# <a name="receiving-notification-from-common-controls"></a>Получение уведомления от стандартных элементов управления

Общие элементы управления — это дочерние окна, которые отправляют сообщения уведомления родительскому окну, когда события, такие как входные данные пользователя, происходят в элементе управления.

Приложение использует эти уведомления для определения действия, которое пользователь хочет предпринять. Большинство стандартных элементов управления отправляют сообщения уведомлений как WM_NOTIFY сообщения. Элементы управления Windows отправляют большинство сообщений с уведомлениями как WM_COMMAND сообщения. [CWnd:: OnNotify](../mfc/reference/cwnd-class.md#onnotify) — обработчик для сообщения WM_NOTIFY. Как и в случае с `CWnd::OnCommand`, реализация `OnNotify` отправляет сообщение уведомления `OnCmdMsg` для обработки в картах сообщений. Запись схемы сообщений для обработки уведомлений ON_NOTIFY. Дополнительные сведения см. в [техническом примечании 61: ON_NOTIFY и WM_NOTIFY сообщения](../mfc/tn061-on-notify-and-wm-notify-messages.md).

Кроме того, производный класс может управлять собственными сообщениями уведомления с помощью "отражения сообщений". Дополнительные сведения см. в [техническом примечании 62: отражение сообщений для элементов управления Windows](../mfc/tn062-message-reflection-for-windows-controls.md).

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Получение позиции курсора в сообщении уведомления

В некоторых случаях полезно определить текущую позицию курсора при получении определенных сообщений об уведомлениях общим элементом управления. Например, было бы полезно определить текущее положение курсора, когда общий элемент управления получит NM_RCLICK сообщение уведомления.

Это можно сделать простым способом, вызвав `CWnd::GetCurrentMessage`. Однако этот метод получает только позицию курсора на момент отправки сообщения. Так как курсор мог быть перемещен с момента отправки сообщения, необходимо вызвать метод `CWnd::GetCursorPos`, чтобы получить текущую позицию курсора.

> [!NOTE]
>  `CWnd::GetCurrentMessage` следует вызывать только в обработчике сообщений.

Добавьте следующий код в тело обработчика сообщений уведомления (в этом примере NM_RCLICK):

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

На этом этапе расположение курсора мыши сохраняется в объекте `cursorPos`.

## <a name="see-also"></a>См. также:

[Создание и использование элементов управления](../mfc/making-and-using-controls.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
