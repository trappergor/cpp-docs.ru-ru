---
title: Обработка уведомляющих сообщений в месяц календаря элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5bbdb3728009cdee978bb08ef8df8817f1ef5e41
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378180"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Обработка уведомляющих сообщений в элементах управления "Календарь на месяц"

Как пользователи взаимодействуют с элементом управления Календарь месяца (выбор дат или просмотр другой месяц), элемент управления (`CMonthCalCtrl`) отправляет сообщения уведомления своему родительскому окну, обычно объект представления или диалогового окна. Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например когда пользователь выбирает новый месяц для просмотра, можно предоставить набор дат, которые необходимо подчеркнуть.

Используйте окно свойств для добавления обработчиков уведомлений в родительский класс сообщений, которые необходимо реализовать.

Ниже перечислены различные уведомления, отправляемые элементом управления Календарь месяца.

- Запросы MCN_GETDAYSTATE сведения о том, какие дни должны отображаться полужирным шрифтом. Дополнительные сведения об обработке этого уведомления, см. в разделе [Установка состояния дня элемента управления Calendar Month](../mfc/setting-the-day-state-of-a-month-calendar-control.md).

- Уведомляет MCN_SELCHANGE родителя, который был изменен выбранную дату или диапазон даты.

- Уведомляет MCN_SELECT родителя, который явной даты выбраны.

## <a name="see-also"></a>См. также

[Использование CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

