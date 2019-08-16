---
title: Обработка уведомляющих сообщений в элементах управления списками
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: e93e91a3219f81bf4027549fc84f1c85c8defb5b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507870"
---
# <a name="processing-notification-messages-in-list-controls"></a>Обработка уведомляющих сообщений в элементах управления списками

Когда пользователи щелкают заголовки столбцов, перетаскивать значки, изменять метки и т. д., элемент управления "список" ([CListCtrl](../mfc/reference/clistctrl-class.md)) отправляет сообщения уведомления в родительское окно. Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например, когда пользователь щелкает заголовок столбца, может потребоваться отсортировать элементы по содержимому столбца, выбранному щелчком мыши, как в Microsoft Outlook.

Обработка сообщений WM_NOTIFY из элемента управления "список" в классе представления или диалогового окна. Используйте окно свойств, чтобы создать функцию обработчика [ончилднотифи](../mfc/reference/cwnd-class.md#onchildnotify) с инструкцией Switch, основанной на том, какое сообщение уведомления обрабатывается.

Список уведомлений, которые элемент управления "список" может отправить в родительское окно, см. в подразделе [ссылка на элемент управления](/windows/win32/Controls/list-view-control-reference) списком в Windows SDK.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
