---
title: Получение уведомления от стандартных элементов управления
ms.date: 11/04/2016
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
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
ms.openlocfilehash: 8813a7f86bde417b48d5ab2d943d296efef5e91c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542653"
---
# <a name="receiving-notification-from-common-controls"></a>Получение уведомления от стандартных элементов управления

Стандартные элементы управления являются дочерними окнами, которые отправляют сообщения уведомления в родительское окно, при возникновении события, такие как входные данные пользователя, в элементе управления.

Приложение использует эти уведомления, чтобы определить, какие действия пользователь хочет его выполнять. Наиболее распространенных элементов управления отправки уведомлений, как сообщения WM_NOTIFY. Элементы управления Windows отправлять большинство сообщений уведомления как сообщения WM_COMMAND. [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) обработки сообщения WM_NOTIFY. Как и в `CWnd::OnCommand`, реализация `OnNotify` отправляет сообщение уведомления `OnCmdMsg` для обработки в схемы сообщений. Запись схемы сообщений для обработки уведомлений является ON_NOTIFY. Дополнительные сведения см. в разделе [технические 61 Примечание: ON_NOTIFY и Wm_notify](../mfc/tn061-on-notify-and-wm-notify-messages.md).

Кроме того производный класс может обрабатывать собственные сообщения уведомления, с помощью «отражение сообщений». Дополнительные сведения см. в разделе [технические 62 Примечание: отражения для Windows Управление сообщениями](../mfc/tn062-message-reflection-for-windows-controls.md).

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Получение курсора в сообщение уведомления

В некоторых случаях полезно для определения текущей позиции курсора, при получении определенных сообщений уведомлений, общего элемента управления. Например было бы полезно для определения текущего положения курсора, получив уведомление NM_RCLICK общего элемента управления.

Есть простой способ это сделать, вызвав `CWnd::GetCurrentMessage`. Тем не менее этот метод извлекает только позицию курсора во время отправки сообщения. Поскольку курсор был перемещен с момента отправки сообщения необходимо вызвать метод `CWnd::GetCursorPos` для получения текущей позиции курсора.

> [!NOTE]
>  `CWnd::GetCurrentMessage` должен вызываться только в пределах обработчика сообщений.

Добавьте следующий код в тело обработчик сообщений уведомления (в данном примере NM_RCLICK):

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

На этом этапе положения курсора мыши хранится в `cursorPos` объекта.

## <a name="see-also"></a>См. также

[Создание и использование элементов управления](../mfc/making-and-using-controls.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

