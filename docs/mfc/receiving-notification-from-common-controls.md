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
ms.openlocfilehash: 80fefde054ed411dcb30836b2b89cef89cc54e64
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928798"
---
# <a name="receiving-notification-from-common-controls"></a>Получение уведомления от стандартных элементов управления
Стандартные элементы управления являются дочерних окон, отправки сообщений уведомления в родительское окно, когда происходят события, такие как входные данные пользователя, в элементе управления.  
  
 Приложение использует эти сообщения уведомления, чтобы определить, какое действие пользователю его выполнять. Наиболее распространенных элементов управления отправки сообщений уведомления как сообщения WM_NOTIFY. Элементы управления Windows отправка большинство уведомляющих сообщений в качестве WM_COMMAND-сообщения. [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) обработки сообщения WM_NOTIFY. Как и в `CWnd::OnCommand`, реализация `OnNotify` отправляет сообщение уведомления в `OnCmdMsg` для обработки в схемы сообщений. Запись схемы сообщений для обработки уведомлений является ON_NOTIFY. Дополнительные сведения см. в разделе [технические 61 Примечание: ON_NOTIFY и Wm_notify](../mfc/tn061-on-notify-and-wm-notify-messages.md).  
  
 Кроме того производный класс может обрабатывать сообщения уведомления, с помощью «отражения сообщения». Дополнительные сведения см. в разделе [технические 62 Примечание: сообщение отражения для элементов управления Windows](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Получение курсора в сообщение уведомления  
 В некоторых случаях полезно для определения текущей позиции курсора, при определенных сообщений уведомлений, полученных от стандартного элемента управления. Например могут быть полезными для определения текущего положения курсора, получив уведомление NM_RCLICK стандартного элемента управления.  
  
 Нет простого способа это сделать, вызвав `CWnd::GetCurrentMessage`. Однако этот метод извлекает только позицию курсора во время отправки сообщения. Поскольку курсор был перемещен, так как было отправлено сообщение, необходимо вызвать метод `CWnd::GetCursorPos` для получения текущей позиции курсора.  
  
> [!NOTE]
>  `CWnd::GetCurrentMessage` должен вызываться только в пределах обработчика сообщений.  
  
 Добавьте следующий код в теле обработчика сообщений уведомления (в данном примере NM_RCLICK):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]  
  
 На этом этапе положение курсора мыши хранится в `cursorPos` объекта.  
  
## <a name="see-also"></a>См. также  
 [Создание и использование элементов управления](../mfc/making-and-using-controls.md)   
 [Элементы управления](../mfc/controls-mfc.md)

