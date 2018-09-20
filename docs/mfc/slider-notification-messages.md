---
title: Уведомляющие сообщения ползунка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 775ca98ff19266343631ff54bac16bebfff9e264
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399539"
---
# <a name="slider-notification-messages"></a>Уведомляющие сообщения ползунка

Элемент управления "ползунок" уведомляет родительского окна действий пользователя, отправляя родительского сообщения WM_HSCROLL и WM_VSCROLL сообщения, в зависимости от ориентации элемента управления "ползунок". Чтобы обработать эти сообщения, добавьте обработчики для сообщения WM_HSCROLL и WM_VSCROLL родительского окна. [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) и [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) функции-члены будут передаваться код уведомления, положение ползунка и указатель на [CSliderCtrl](../mfc/reference/csliderctrl-class.md) объекта. Обратите внимание, что указатель типа `CScrollBar *` несмотря на то, что он указывает `CSliderCtrl` объекта. Может потребоваться выполнить приведение этого указателя, если требуется выполнять операции управления "ползунок".

Вместо использования прокрутки штрих-коды уведомления, элементы управления "ползунок" Отправить другой набор кодов уведомления. Элемент управления "ползунок" отправляет коды уведомления TB_BOTTOM, TB_LINEDOWN, TB_LINEUP и TB_TOP только в том случае, когда пользователь взаимодействует с элементом управления "ползунок" с помощью клавиатуры. TB_THUMBPOSITION и TB_THUMBTRACK сообщений уведомления отправляются только в том случае, когда пользователь использует указатель мыши. Коды уведомления TB_ENDTRACK TB_PAGEDOWN и TB_PAGEUP отправляются в обоих случаях.

В следующей таблице перечислены уведомляющих сообщений элемента управления "ползунок" и события (коды виртуальных клавиш или события мыши), которые вызывают отправку уведомлений. (Список стандартные коды виртуальных клавиш, см. в разделе Winuser.h.)

|Сообщение уведомления|Событие, вызывая уведомления|
|--------------------------|-------------------------------------------|
|TB_BOTTOM|VK_END|
|TB_ENDTRACK|WM_KEYUP (Пользователь отпустил ключ, который отправлен соответствующий виртуальному коду клавиши)|
|TB_LINEDOWN|VK_RIGHT или VK_DOWN|
|TB_LINEUP|VK_LEFT или VK_UP|
|TB_PAGEDOWN|VK_NEXT (пользователь щелкнул канал ниже или справа от ползунка)|
|TB_PAGEUP|VK_PRIOR (пользователь щелкнул канал выше или слева от ползунка)|
|TB_THUMBPOSITION|Следуя сообщение уведомления TB_THUMBTRACK WM_LBUTTONUP|
|TB_THUMBTRACK|Перемещение ползунка (пользователь перетащить ползунок)|
|TB_TOP|VK_HOME|

## <a name="see-also"></a>См. также

[Использование CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

