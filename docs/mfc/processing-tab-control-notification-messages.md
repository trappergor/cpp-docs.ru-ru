---
title: Обработка уведомляющих сообщений элемента управления "Вкладка"
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
ms.openlocfilehash: cc322a038717d48f440df1ec571674cec80743ce
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908064"
---
# <a name="processing-tab-control-notification-messages"></a>Обработка уведомляющих сообщений элемента управления "Вкладка"

Когда пользователи щелкают вкладки или кнопки, элемент управления "Вкладка" ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) отправляет сообщения уведомления в родительское окно. Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например, когда пользователь щелкает вкладку, может потребоваться предварительно установить контрольные данные на странице перед ее отображением.

Обработка сообщений WM_NOTIFY из элемента управления "Вкладка" в классе представления или диалогового окна. Используйте [мастер классов](reference/mfc-class-wizard.md) для создания функции обработчика [ончилднотифи](../mfc/reference/cwnd-class.md#onchildnotify) с инструкцией Switch, основанной на том, какое сообщение уведомления обрабатывается. Список уведомлений, которые элемент управления "Вкладка" может отправить в родительское окно, см. в разделе " **уведомления** [" Справочника по элементу управления Tab](/windows/win32/controls/tab-control-reference) в Windows SDK.

## <a name="see-also"></a>См. также

[Использование CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
