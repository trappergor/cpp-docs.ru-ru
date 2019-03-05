---
title: Установка состояния дня в элементе управления "Календарь на месяц"
ms.date: 11/04/2016
f1_keywords:
- MCN_GETDAYSTATE
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
ms.openlocfilehash: c75b560509738e071accdc3dba31dfdea35a14aa
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262369"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>Установка состояния дня в элементе управления "Календарь на месяц"

Один из атрибутов управления Календарь месяца является возможность хранения данных, называется состояния дня элемента управления, для каждого дня месяца. Эта информация используется для выделения определенных дат за месяц отображается в текущий момент.

> [!NOTE]
>  `CMonthCalCtrl` Объект должен иметь MCS_DAYSTATE стиль отображения сведений о состоянии дня.

Сведения о состоянии дня выражается в виде 32-разрядный тип данных, **MONTHDAYSTATE**. Каждый бит в **MONTHDAYSTATE** битовое поле (от 1 до 31) представляет состояние в день в месяц. Если бит равен в, соответствующий день будет отображаться полужирным шрифтом; в противном случае он будет отображаться с отсутствие курсива.

Существует два метода для Установка состояния дня элемента управления calendar month: явным образом с помощью вызова [CMonthCalCtrl::SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) или путем обработки MCN_GETDAYSTATE сообщения уведомления.

## <a name="handling-the-mcngetdaystate-notification-message"></a>Обработка сообщения уведомления MCN_GETDAYSTATE

MCN_GETDAYSTATE сообщение отправляется элементом управления определяют отображение дней, в течение месяцев видимым.

> [!NOTE]
>  Так как элемент управления кэширует предыдущие и следующие месяцы, в отношении отображаемого месяца, вы получите это уведомление каждый раз выбирается новый месяц.

Чтобы правильно обработать это сообщение, необходимо определить, сколько месяцев, сведения о состоянии дня, запрошенный для инициализации массива **MONTHDAYSTATE** структур с соответствующими значениями и инициализировать элемент связанные структуры новыми данными. В следующей процедуре, подробным описанием действий, необходимых, предполагается, что у вас есть `CMonthCalCtrl` объект под названием *m_monthcal* и массив **MONTHDAYSTATE** объектов, *mdState*.

#### <a name="to-handle-the-mcngetdaystate-notification-message"></a>Для обработки сообщения уведомления MCN_GETDAYSTATE

1. В окне свойств, добавление обработчика уведомлений для сообщения MCN_GETDAYSTATE *m_monthcal* объекта (см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).

1. В теле обработчика добавьте следующий код:

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   В примере выполняется преобразование *pNMHDR* указатель к нужному типу, затем определяет, сколько месяцев сведения запрашиваются (`pDayState->cDayState`). Для каждого месяца текущего битовое поле (`pDayState->prgDayState[i]`) устанавливается равным нулю и затем необходимую даты заданы (в данном случае 15-й день каждого месяца).

## <a name="see-also"></a>См. также

[Использование CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
