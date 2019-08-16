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
ms.openlocfilehash: f60a0c918476702881984f976b220130727cf4b0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507947"
---
# <a name="processing-header-control-notifications"></a>Обработка уведомлений элемента управления "Заголовок"

В классе представления или диалогового окна используйте окно свойств, чтобы создать функцию обработчика [ончилднотифи](../mfc/reference/cwnd-class.md#onchildnotify) с оператором Switch для любых сообщений уведомления элемента управления заголовка ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)), которые необходимо обменять (см. раздел [сопоставление сообщений с функциями). ](../mfc/reference/mapping-messages-to-functions.md)). Уведомления отправляются в родительское окно, когда пользователь щелкает или дважды щелкает элемент заголовка, перетаскивает разделитель между элементами и т. д.

Сообщения уведомления, связанные с элементом управления "заголовок", перечислены в справочнике по [элементу управления](/windows/win32/controls/header-control-reference) заголовком в Windows SDK.

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
