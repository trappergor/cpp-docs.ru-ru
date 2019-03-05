---
title: Обработка отраженных сообщений
ms.date: 11/04/2016
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
ms.openlocfilehash: 973e8cff24eca37b1806207d081636f0d1b38365
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275380"
---
# <a name="handling-reflected-messages"></a>Обработка отраженных сообщений

Отражение позволяет обрабатывать сообщения для элемента управления, такие как сообщения **WM_CTLCOLOR**, **WM_COMMAND**, и **WM_NOTIFY**, внутри себя. Это делает элемент управления более автономной и переносной. Этот механизм работает с помощью стандартных элементов управления Windows, а также с элементами управления ActiveX (ранее называвшихся элементов управления OLE).

Сообщение, отражение позволяет повторно использовать ваши `CWnd`-производные классы более эффективно. Сообщения works отражение через [CWnd::OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify), с помощью специальных **ON_XXX_REFLECT** записей карты сообщений: например, **ON_CTLCOLOR_REFLECT** и **ON_CONTROL_REFLECT**. [Технические заметки 62](../mfc/tn062-message-reflection-for-windows-controls.md) объясняет отражение сообщений более подробно.

## <a name="what-do-you-want-to-do"></a>Что Вы хотите делать

- [Дополнительные сведения об отражении сообщения](../mfc/tn062-message-reflection-for-windows-controls.md)

- [Реализовать отражение сообщений для общего элемента управления](../mfc/tn062-message-reflection-for-windows-controls.md)

- [Реализовать отражение сообщений для элемента управления ActiveX](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)

## <a name="see-also"></a>См. также

[Объявление функций обработчиков сообщений](../mfc/declaring-message-handler-functions.md)
