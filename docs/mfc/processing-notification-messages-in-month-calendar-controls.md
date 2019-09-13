---
title: Обработка уведомляющих сообщений в элементах управления "Календарь на месяц"
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
ms.openlocfilehash: 452d24bf1ffd157366f357a510e8c8cfaad28d91
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908080"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Обработка уведомляющих сообщений в элементах управления "Календарь на месяц"

При взаимодействии пользователей с элементом управления "Календарь на месяц" (выбор дат и/или просмотре другого месяца)`CMonthCalCtrl`элемент управления () отправляет сообщения уведомления своему родительскому окну (обычно это представление или объект диалогового окна). Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например, когда пользователь выбирает новый месяц для просмотра, можно указать набор дат, которые должны быть выделены.

Используйте [мастер классов](reference/mfc-class-wizard.md) для добавления обработчиков уведомлений в родительский класс для тех сообщений, которые требуется реализовать.

В следующем списке описаны различные уведомления, отправляемые элементом управления "календарь месяца".

- MCN_GETDAYSTATE запрашивает информацию о том, какие дни должны отображаться полужирным шрифтом. Сведения об обработке этого уведомления см. в разделе [Задание состояния дня для элемента управления "месячный календарь"](../mfc/setting-the-day-state-of-a-month-calendar-control.md).

- MCN_SELCHANGE уведомляет родительский элемент о том, что выбранная дата или диапазон даты изменились.

- MCN_SELECT уведомляет родительский элемент о том, что была сделана явная выборка даты.

## <a name="see-also"></a>См. также

[Использование CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
