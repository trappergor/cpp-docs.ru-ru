---
title: Получение уведомления от стандартных элементов управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30e89c8d25d78477ed98bae0fd06a704e32d3906
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349717"
---
# <a name="receiving-notification-from-common-controls"></a>Получение уведомления от стандартных элементов управления
Стандартные элементы управления являются дочерних окон, отправки сообщений уведомления в родительское окно, когда происходят события, такие как входные данные пользователя, в элементе управления.  
  
 Приложение использует эти сообщения уведомления, чтобы определить, какое действие пользователю его выполнять. Наиболее распространенных элементов управления отправки сообщений уведомления как **WM_NOTIFY** сообщений. Элементы управления Windows отправки большинство сообщений уведомления как **WM_COMMAND** сообщений. [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) обработчика для **WM_NOTIFY** сообщения. Как и в `CWnd::OnCommand`, реализация `OnNotify` отправляет сообщение уведомления в `OnCmdMsg` для обработки в схемы сообщений. Запись схемы сообщений для обработки уведомления `ON_NOTIFY`. Дополнительные сведения см. в разделе [технические 61 Примечание: ON_NOTIFY и Wm_notify](../mfc/tn061-on-notify-and-wm-notify-messages.md).  
  
 Кроме того производный класс может обрабатывать сообщения уведомления, с помощью «отражения сообщения». Дополнительные сведения см. в разделе [технические 62 Примечание: сообщение отражения для элементов управления Windows](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Получение курсора в сообщение уведомления  
 В некоторых случаях полезно для определения текущей позиции курсора, при определенных сообщений уведомлений, полученных от стандартного элемента управления. Например, могут быть полезными для определения текущего положения курсора, при получении стандартного элемента управления **NM_RCLICK** сообщение уведомления.  
  
 Нет простого способа это сделать, вызвав `CWnd::GetCurrentMessage`. Однако этот метод извлекает только позицию курсора во время отправки сообщения. Поскольку курсор был перемещен, так как было отправлено сообщение, необходимо вызвать **CWnd::GetCursorPos** для получения текущей позиции курсора.  
  
> [!NOTE]
>  `CWnd::GetCurrentMessage` должен вызываться только в пределах обработчика сообщений.  
  
 Добавьте следующий код в теле обработчика сообщений уведомления (в этом примере **NM_RCLICK**):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]  
  
 На этом этапе положение курсора мыши хранится в `cursorPos` объекта.  
  
## <a name="see-also"></a>См. также  
 [Создание и использование элементов управления](../mfc/making-and-using-controls.md)   
 [Элементы управления](../mfc/controls-mfc.md)

