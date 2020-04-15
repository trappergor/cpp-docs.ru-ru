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
ms.openlocfilehash: 9892f2d853687787dd76428fc9bc95f3a4f74565
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365427"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>Установка состояния дня в элементе управления "Календарь на месяц"

Одним из атрибутов месячного календарного контроля является возможность хранения информации, называемой дневным состоянием элемента управления, для каждого дня месяца. Эта информация используется для того, чтобы подчеркнуть определенные даты на отображаемый в настоящее время месяц.

> [!NOTE]
> Объект `CMonthCalCtrl` должен иметь MCS_DAYSTATE стиль для отображения информации о состоянии дня.

Информация о состоянии дня выражается как 32-битный тип данных, **MONTHDAYSTATE**. Каждый бит в поле бита **MONTHDAYSTATE** (от 1 до 31) представляет состояние дня в месяц. Если немного на, соответствующий день будет отображаться жирным шрифтом; в противном случае он будет отображаться без акцента.

Существует два способа настройки дневного состояния элемента календарного управления месяца: явно с вызовом на [CMonthCalCtrl::SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) или при обработке MCN_GETDAYSTATE сообщением уведомления.

## <a name="handling-the-mcn_getdaystate-notification-message"></a>Обработка сообщения MCN_GETDAYSTATE уведомления

Сообщение MCN_GETDAYSTATE отправляется элементом управления, чтобы определить, как должны отображаться дни в течение видимых месяцев.

> [!NOTE]
> Поскольку контрольный кэш в предыдущие и последующие месяцы, по отношению к видимому месяцу, вы будете получать это уведомление каждый раз, когда выбирается новый месяц.

Чтобы правильно обрабатывать это сообщение, необходимо определить, сколько месяцев дня запрашивается государственная информация, инициализировать массив структур **MONTHDAYSTATE** с соответствующими значениями и инициализировать связанный член структуры с новой информацией. Следующая процедура, описывающая необходимые шаги, `CMonthCalCtrl` предполагает, что у вас есть объект под названием *m_monthcal* и массив объектов **MONTHDAYSTATE,** *mdState.*

#### <a name="to-handle-the-mcn_getdaystate-notification-message"></a>Обработка сообщения MCN_GETDAYSTATE уведомления

1. Используя [«Мастер класса»,](reference/mfc-class-wizard.md)добавьте обработчик уведомлений для MCN_GETDAYSTATE сообщение *на объект m_monthcal* (см. [Отображение сообщений к функциям).](../mfc/reference/mapping-messages-to-functions.md)

1. В теле обработчика добавьте следующий код:

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   Пример преобразует указатель *pNMHDR* в правильный тип, а затем определяет, сколько`pDayState->cDayState`месяцев запрашивается информация (). Для каждого месяца текущее`pDayState->prgDayState[i]`битфилд () инициируется до нуля, а затем устанавливаются необходимые даты (в данном случае 15 числа каждого месяца).

## <a name="see-also"></a>См. также раздел

[Использование CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
