---
title: Обработка уведомляющих сообщений в элементах управления списками
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: 92111e3e0a4869ca06b89d2d18d38aab9f10ab7d
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908096"
---
# <a name="processing-notification-messages-in-list-controls"></a>Обработка уведомляющих сообщений в элементах управления списками

Когда пользователи щелкают заголовки столбцов, перетаскивать значки, изменять метки и т. д., элемент управления "список" ([CListCtrl](../mfc/reference/clistctrl-class.md)) отправляет сообщения уведомления в родительское окно. Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например, когда пользователь щелкает заголовок столбца, может потребоваться отсортировать элементы по содержимому столбца, выбранному щелчком мыши, как в Microsoft Outlook.

Обработка сообщений WM_NOTIFY из элемента управления "список" в классе представления или диалогового окна. Используйте [мастер классов](reference/mfc-class-wizard.md) для создания функции обработчика [ончилднотифи](../mfc/reference/cwnd-class.md#onchildnotify) с инструкцией Switch, основанной на том, какое сообщение уведомления обрабатывается.

Список уведомлений, которые элемент управления "список" может отправить в родительское окно, см. в подразделе [ссылка на элемент управления](/windows/win32/Controls/list-view-control-reference) списком в Windows SDK.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
