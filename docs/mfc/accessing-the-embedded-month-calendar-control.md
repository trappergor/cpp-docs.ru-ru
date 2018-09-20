---
title: Доступ к месяца внедренный элемент управления "Календарь" | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a92660223c84c5f53bc848e72b03316602180d36
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430297"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>Доступ к встроенному элементу управления "Календарь на месяц"

Объект управления embedded месяц календаря может осуществляться из `CDateTimeCtrl` объекта с помощью вызова [GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl) функция-член.

> [!NOTE]
>  Внедренные управляющий элемент календаря используется только в том случае, если элемент управления выбора даты и времени не имеет **DTS_UPDOWN** в стиле набора.

Это полезно, если вы хотите изменить определенные атрибуты, перед отображением внедренного элемента управления. Для этого обработайте **DTN_DROPDOWN** уведомление, извлечь управления Календарь месяца (с помощью [CDateTimeCtrl::GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)) и внесите нужные изменения. К сожалению не является постоянной управляющий элемент календаря.

Другими словами, когда пользователь запрашивает отображение элемента управления calendar month, новый месяц календаря создается элемент управления (перед **DTN_DROPDOWN** уведомлений). Уничтожении этого элемента (после **DTN_CLOSEUP** уведомлений) при закрыт пользователем. Это означает, что любые атрибуты, которые можно изменять, перед отображением внедренного элемента управления, будут потеряны при закрывании внедренного элемента управления.

В следующем примере демонстрируется Эта процедура, с помощью обработчика для **DTN_DROPDOWN** уведомлений. Код изменяет цвет фона элемента управления Календарь месяца, с помощью вызова [SetMonthCalColor](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor), к серому. Код выглядит следующим образом:

[!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

Как уже говорилось ранее, все изменения свойств элемента управления Календарь месяца будут потеряны, с двумя исключениями при закрывании внедренного элемента управления. Первое исключение цвета элемента управления calendar month, уже рассматривали. Второе исключение – шрифт, используемый элементом управления Календарь месяца. Шрифт по умолчанию можно изменить с помощью вызова [CDateTimeCtrl::SetMonthCalFont](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont), передав дескриптор существующих шрифтов. Следующий пример (где `m_dtPicker` — это объект элемента управления, дату и время) показан один из возможных способов:

[!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

После изменения шрифта, с помощью вызова `CDateTimeCtrl::SetMonthCalFont`, хранится и используется в следующий раз, месячный календарь будет отображаться новый шрифт.

## <a name="see-also"></a>См. также

[Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

