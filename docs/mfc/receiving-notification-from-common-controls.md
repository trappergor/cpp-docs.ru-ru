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
ms.openlocfilehash: 9205facb5ec4e2491308020d9667a27ab8deb96b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371784"
---
# <a name="receiving-notification-from-common-controls"></a>Получение уведомления от стандартных элементов управления

Общими элементами управления являются окна ребенка, которые отправляют сообщения уведомлений в родительское окно, когда события, такие как вход ные данные пользователя, происходят в элементе управления.

Приложение полагается на эти сообщения уведомлений, чтобы определить, какие действия пользователь хочет принять. Наиболее распространенные элементы управления отправляют сообщения уведомлений в виде WM_NOTIFY сообщений. Элементы управления Windows отправляют большинство сообщений уведомлений в качестве WM_COMMAND сообщений. [CWnd:OnNotify](../mfc/reference/cwnd-class.md#onnotify) — это обработчик WM_NOTIFY сообщения. Как `CWnd::OnCommand`и в `OnNotify` том, что реализация `OnCmdMsg` отправки уведомления сообщение для обработки в картах сообщений. Запись на карту сообщений для обработки уведомлений ON_NOTIFY. Для получения дополнительной информации см [WM_NOTIFY ON_NOTIFY.](../mfc/tn061-on-notify-and-wm-notify-messages.md)

Кроме того, полученный класс может обрабатывать свои собственные сообщения уведомлений с помощью "отражения сообщений". Для получения дополнительной информации [см.](../mfc/tn062-message-reflection-for-windows-controls.md)

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Получение позиции курсора в уведомлении

Иногда полезно определить текущее положение курсора, когда определенные сообщения уведомлений получаются общим элементом управления. Например, было бы полезно определить текущее местоположение курсора, когда общий элемент управления получает NM_RCLICK сообщение об уведомлении.

Существует простой способ для достижения `CWnd::GetCurrentMessage`этой цели, позвонив . Однако этот метод получает только положение курсора во время отправки сообщения. Поскольку курсор может быть перемещен с момента отправки сообщения, вы должны позвонить, `CWnd::GetCursorPos` чтобы получить текущее положение курсора.

> [!NOTE]
> `CWnd::GetCurrentMessage`только должны вызываться в обработчике сообщений.

Добавьте следующий код к телу обработчика уведомлений (в данном примере NM_RCLICK):

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

На этом этапе расположение курсора мыши `cursorPos` хранится в объекте.

## <a name="see-also"></a>См. также раздел

[Создание и использование элементов управления](../mfc/making-and-using-controls.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
