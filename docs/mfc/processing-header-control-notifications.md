---
title: Обработка уведомлений элемента управления "Заголовок"
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
ms.openlocfilehash: bc811763fe3f4717b8baaeb4a23df1ae59bb1979
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908126"
---
# <a name="processing-header-control-notifications"></a>Обработка уведомлений элемента управления "Заголовок"

В классе представления или диалогового окна используйте [мастер классов](reference/mfc-class-wizard.md) , чтобы создать функцию обработчика [ончилднотифи](../mfc/reference/cwnd-class.md#onchildnotify) с оператором Switch для любого сообщения уведомления, которое требуется обменять[(см](../mfc/reference/cheaderctrl-class.md). раздел [сопоставление сообщений с Функции](../mfc/reference/mapping-messages-to-functions.md)). Уведомления отправляются в родительское окно, когда пользователь щелкает или дважды щелкает элемент заголовка, перетаскивает разделитель между элементами и т. д.

Сообщения уведомления, связанные с элементом управления "заголовок", перечислены в [справочнике по элементу управления заголовком](/windows/win32/controls/header-control-reference) в Windows SDK.

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
