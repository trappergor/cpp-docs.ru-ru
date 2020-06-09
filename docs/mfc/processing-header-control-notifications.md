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
ms.openlocfilehash: c313382b8be7538ba5bb465c6ba383955e414662
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619797"
---
# <a name="processing-header-control-notifications"></a>Обработка уведомлений элемента управления "Заголовок"

В классе представления или диалогового окна используйте [мастер классов](reference/mfc-class-wizard.md) , чтобы создать функцию обработчика [ончилднотифи](reference/cwnd-class.md#onchildnotify) с оператором Switch для любого сообщения уведомления элемента управления заголовка ([CHeaderCtrl](reference/cheaderctrl-class.md)), которое необходимо обменять (см. раздел [сопоставление сообщений функциям](reference/mapping-messages-to-functions.md)). Уведомления отправляются в родительское окно, когда пользователь щелкает или дважды щелкает элемент заголовка, перетаскивает разделитель между элементами и т. д.

Сообщения уведомления, связанные с элементом управления "заголовок", перечислены в [справочнике по элементу управления заголовком](/windows/win32/controls/header-control-reference) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Использование CHeaderCtrl](using-cheaderctrl.md)<br/>
[Элементы управления](controls-mfc.md)
