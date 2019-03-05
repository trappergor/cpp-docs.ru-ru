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
ms.openlocfilehash: 3c5d147741123f97a53b18a854db9204738d0a2f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287691"
---
# <a name="processing-header-control-notifications"></a>Обработка уведомлений элемента управления "Заголовок"

В классе представления или диалогового окна, используйте окно свойств для создания [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) функцию обработчика с оператором switch для любого заголовка элемента управления ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) для уведомляющих сообщений обрабатывать (см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)). Уведомления отправляются в родительское окно, когда пользователь нажимает кнопку или дважды щелкает элемент заголовка, перетаскивания a разделитель между элементами и т. д.

Сообщения уведомлений, связанных с элементом управления заголовка перечислены в [ссылки на элемент управления заголовка](/windows/desktop/controls/header-control-reference) в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
