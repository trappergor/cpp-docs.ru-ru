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
ms.openlocfilehash: 66a9ef7fd49ea81ddac4779aa6d1c3f12fbe4c55
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617374"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>Доступ к встроенному элементу управления "Календарь на месяц"

Доступ к объекту элемента управления Calendar month можно получить из `CDateTimeCtrl` объекта с помощью вызова функции-члена [жетмонскалктрл](reference/cdatetimectrl-class.md#getmonthcalctrl) .

> [!NOTE]
> Элемент управления "месячный календарь" используется только в том случае, если для элемента управления "Выбор даты и времени" не задан стиль **DTS_UPDOWN** .

Это полезно, если необходимо изменить определенные атрибуты перед отображением внедренного элемента управления. Для этого обработайте уведомление **DTN_DROPDOWN** , извлеките элемент управления "месячный календарь" (с помощью [CDateTimeCtrl:: жетмонскалктрл](reference/cdatetimectrl-class.md#getmonthcalctrl)) и внесите необходимые изменения. К сожалению, элемент управления "Календарь на месяц" не является постоянным.

Иными словами, когда пользователь запрашивает отображение элемента управления "месячный календарь", создается элемент управления "Календарь на месяц" (перед уведомлением **DTN_DROPDOWN** ). Элемент управления уничтожается (после уведомления **DTN_CLOSEUP** ) при закрытии пользователем. Это означает, что любые изменяемые атрибуты перед отображением внедренного элемента управления теряются при закрытии внедренного элемента управления.

В следующем примере показана эта процедура с помощью обработчика для **DTN_DROPDOWN** уведомления. Код изменяет цвет фона элемента управления "Календарь на месяц" с помощью вызова [сетмонскалколор](reference/cdatetimectrl-class.md#setmonthcalcolor)на серый. Код выглядит следующим образом:

[!code-cpp[NVC_MFCControlLadenDialog#5](codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

Как уже отмечалось ранее, все изменения свойств элемента управления "календарь месяца" теряются с двумя исключениями при закрытии внедренного элемента управления. Первое исключение, цвет элемента управления "календарь месяца", уже обсуждалось. Вторым исключением является шрифт, используемый элементом управления "месячный календарь". Шрифт по умолчанию можно изменить, сделав вызов [CDateTimeCtrl:: сетмонскалфонт](reference/cdatetimectrl-class.md#setmonthcalfont), передав ему маркер существующего шрифта. В следующем примере (где `m_dtPicker` — объект элемента управления даты и времени) демонстрируется один из возможных методов:

[!code-cpp[NVC_MFCControlLadenDialog#6](codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

После изменения шрифта с помощью вызова `CDateTimeCtrl::SetMonthCalFont` новый шрифт сохраняется и используется в следующий раз, когда будет отображаться месячный календарь.

## <a name="see-also"></a>См. также раздел

[Использование CDateTimeCtrl](using-cdatetimectrl.md)<br/>
[Элементы управления](controls-mfc.md)
