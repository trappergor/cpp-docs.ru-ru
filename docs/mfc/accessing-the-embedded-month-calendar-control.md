---
title: Доступ к встроенному элементу управления "Календарь на месяц"
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
ms.openlocfilehash: 69270cc5663406f2c5d38ffccdbd35f39298a3d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354185"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>Доступ к встроенному элементу управления "Календарь на месяц"

Объект управления встроенным месяцем можно `CDateTimeCtrl` получить доступ от объекта с вызовом к функции члена [GetMonthCalCtrl.](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)

> [!NOTE]
> Встроенный элемент управления календарем месяца используется только тогда, когда управление сборщиком даты и времени не имеет **набора DTS_UPDOWN** стилем.

Это полезно, если вы хотите изменить некоторые атрибуты до отображения встроенного элемента управления. Для этого обвязайте **уведомление DTN_DROPDOWN,** получите элемент управления календарем месяца (с помощью [CDateTimeCtrl::GetMonthCalCtrl)](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)и внедьте изменения. К сожалению, месячный календарный контроль не является постоянным.

Другими словами, когда пользователь запрашивает отображение элемента календаря месяца, создается новый элемент управления календарем месяца (до **уведомления DTN_DROPDOWN).** Элемент управления уничтожается (после **уведомления DTN_CLOSEUP)** при отклонении пользователем. Это означает, что любые элементы, которые вы изменяете, до отображения встроенного элемента управления теряются при удалении встроенного элемента управления.

Следующий пример демонстрирует эту процедуру, используя обработчик для **уведомления DTN_DROPDOWN.** Код изменяет фоновый цвет управления календарем месяца, с вызовом на [SetMonthCalColor,](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor)на серый. Код заключается в следующем:

[!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

Как указывалось ранее, все изменения свойств управления календарем месяца теряются, за двумя исключениями, когда встроенный элемент управления удаляется. Первое исключение, цвета месячного календарного управления, уже обсуждалось. Вторым исключением является шрифт, используемый в управлении календарем месяца. Вы можете изменить шрифт по умолчанию, сделав звонок в [CDateTimeCtrl::SetMonthCalFont,](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont)пройдя ручку существующего шрифта. В следующем примере (где `m_dtPicker` находится объект контроля даты и времени) показан один возможный метод:

[!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

После того, как шрифт был `CDateTimeCtrl::SetMonthCalFont`изменен, с вызовом к , новый шрифт хранится и используется в следующий раз календарь месяца должен быть отображается.

## <a name="see-also"></a>См. также раздел

[Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
