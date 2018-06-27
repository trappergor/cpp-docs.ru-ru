---
title: Установка состояния дня в месяце элемента управления "Календарь" | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MCN_GETDAYSTATE
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d4254448e3f8f5a23acd9a303788fd13afb2f84
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950799"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>Установка состояния дня в элементе управления "Календарь на месяц"
Один из атрибутов управления Календарь месяца — возможность хранения данных, называется день состояние элемента управления, для каждого дня месяца. Эта информация используется для выделения определенных дат, отображаемом.  
  
> [!NOTE]
>  `CMonthCalCtrl` Объект должен иметь MCS_DAYSTATE стиль отображения сведений о состоянии дня.  
  
 Сведения о состоянии дня выражается в виде 32-разрядный тип данных, **MONTHDAYSTATE**. Каждый бит в **MONTHDAYSTATE** битовое поле (от 1 до 31) представляет состояние дня в месяце. Если бит включен, соответствующий день будет отображаться полужирным шрифтом; в противном случае он будет отображаться с без выделения.  
  
 Существует два способа для установки состояния управления Календарь месяца дня: явно с помощью вызова [CMonthCalCtrl::SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) или путем обработки MCN_GETDAYSTATE сообщения уведомления.  
  
## <a name="handling-the-mcngetdaystate-notification-message"></a>Обработка сообщения уведомления MCN_GETDAYSTATE  
 MCN_GETDAYSTATE сообщение отправляется с помощью элемента управления для определения того, как должны отображаться дни месяца видимым.  
  
> [!NOTE]
>  Так как элемент управления кэширует предыдущего и следующего месяца, в отношении отображаемого месяца, вы получите уведомления каждый раз выбирается в новый месяц.  
  
 Чтобы правильно обработать это сообщение, необходимо определить, сколько месяцев, сведения о состоянии дня, запрошенный для инициализации массива **MONTHDAYSTATE** структур с помощью соответствующих значений и инициализация члена связанные структуры новыми данными. Следующая процедура, с подробными сведениями о необходимые действия, предполагается, что `CMonthCalCtrl` объекта с именем *m_monthcal* и массив **MONTHDAYSTATE** объектов, *mdState*.  
  
#### <a name="to-handle-the-mcngetdaystate-notification-message"></a>Для обработки сообщения уведомления MCN_GETDAYSTATE  
  
1.  С помощью окна свойств добавления обработчика уведомлений для сообщения MCN_GETDAYSTATE *m_monthcal* объекта (в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).  
  
2.  В теле обработчика добавьте следующий код:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]  
  
     В примере выполняется преобразование *pNMHDR* указатель к нужному типу определяет количество месяцев сведения были запрошены (`pDayState->cDayState`). Для каждого месяца текущего битовое поле (`pDayState->prgDayState[i]`) устанавливается равным нулю и необходимые даты заданы (в данном случае 15-й день каждого месяца).  
  
## <a name="see-also"></a>См. также  
 [Использование CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

