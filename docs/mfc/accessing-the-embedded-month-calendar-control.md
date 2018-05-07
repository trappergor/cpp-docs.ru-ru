---
title: Доступ к месяц внедренный элемент управления "Календарь" | Документы Microsoft
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
ms.openlocfilehash: cfbc9ce7b99efc1f8d99f5735c16c252ff613c59
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-the-embedded-month-calendar-control"></a>Доступ к встроенному элементу управления "Календарь на месяц"
Объект элемента управления Календарь месяца embedded может осуществляться из `CDateTimeCtrl` объекта с помощью вызова [GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl) функции-члена.  
  
> [!NOTE]
>  Внедренные управляющий элемент календаря используется только в том случае, если элемент управления выбора даты и времени не имеет **DTS_UPDOWN** стиля набора.  
  
 Это полезно, если вы хотите изменить некоторые атрибуты перед отображением внедренного элемента управления. Для этого обработайте **DTN_DROPDOWN** уведомления, получения управления Календарь месяца (с помощью [CDateTimeCtrl::GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)) и внесите нужные изменения. К сожалению не является постоянным управления Календарь месяца.  
  
 Другими словами, когда пользователь запрашивает отображение элемента управления calendar month, новый месяц календаря создается элемент управления (перед **DTN_DROPDOWN** уведомления). Элемент управления удаляется (после **DTN_CLOSEUP** уведомления) при закрыт пользователем. Это означает, что все атрибуты, которые можно изменить, перед отображением внедренного элемента управления теряются при закрытии внедренного элемента управления.  
  
 Ниже приведен пример этой процедуры, с помощью обработчика для **DTN_DROPDOWN** уведомления. Код изменяет цвет фона элемента управления calendar month, с помощью вызова [SetMonthCalColor](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor), серый. Код выглядит следующим образом:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]  
  
 Как уже говорилось ранее, все изменения свойств элемента управления calendar month будут потеряны, за двумя исключениями при закрытии внедренного элемента управления. Первое исключение цвета элемента управления calendar month, уже описан. Второе исключение: шрифт, используемый элементом управления Календарь месяца. Шрифт по умолчанию можно изменить путем вызова [CDateTimeCtrl::SetMonthCalFont](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont), передавая дескриптор существующих шрифтов. В следующем примере (где `m_dtPicker` объектом управления даты и времени) демонстрирует один из возможных способов:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]  
  
 После изменения шрифта, с помощью вызова `CDateTimeCtrl::SetMonthCalFont`, хранимых и используемых при очередном месячный календарь будет отображаться новый шрифт.  
  
## <a name="see-also"></a>См. также  
 [Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

