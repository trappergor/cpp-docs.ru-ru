---
title: Элементы управления ActiveX в MFC. Добавление событий хранения в элемент управления ActiveX
ms.date: 11/04/2016
f1_keywords:
- EVENT__STOCK_ERROR
- EVENT__STOCK_READYSTATECHANGE
- ReadyStateChange
- EVENT__STOCK_MOUSEMOVE
- EVENT__STOCK_MOUSEUP
- EVENT__STOCK_DBLCLICK
- KeyPress
- EVENT__STOCK_KEYDOWN
- EVENT__STOCK
- EVENT__STOCK_MOUSEDOWN
- EVENT__STOCK_KEYPRESS
- EVENT__STOCK_CLICK
- EVENT__STOCK_KEYUP
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- KeyPress event
- FireDblClick event
- FireMouseDown event
- events [MFC], stock
- FireKeyPress event
- EVENT_STOCK_MOUSEMOVE event
- EVENT_STOCK_CLICK event
- FireClick event
- FireKeyUp event
- FireMouseUp event
- EVENT_STOCK_ERROREVENT event
- EVENT_STOCK_KEYDOWN event
- EVENT_STOCK_MOUSEDOWN event
- EVENT_STOCK_KEYPRESS macro [MFC]
- EVENT_STOCK_KEYUP event
- EVENT_STOCK_DBLCLICK event
- FireError event
- FireKeyDown event
- ReadyStateChange event
- EVENT_STOCK_MOUSEUP event
- FireMouseMove event
- EVENT_STOCK prefix
- EVENT_STOCK_READYSTATECHANGE event
- EVENT_STOCK_KEYPRESS event
ms.assetid: 3eeadc67-4b3d-4444-8caa-53054073988a
ms.openlocfilehash: 79cd4fc572e55c67cc5a2cfe3a00e04f2a4a7850
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364690"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>Элементы управления ActiveX в MFC. Добавление событий хранения в элемент управления ActiveX

Фондовые события отличаются от пользовательских событий тем, что они автоматически увольняются классом [COleControl.](../mfc/reference/colecontrol-class.md) `COleControl`содержит предопределенные функции членов, которые приводят к событиям, возникающим в результате общих действий. Некоторые общие действия `COleControl` включают одно- и двойные клики на элемент управления, события клавиатуры и изменения состояния кнопок мыши. Записи карты событий для фондовых событий всегда предшествует EVENT_STOCK префикс.

## <a name="stock-events-supported-by-the-add-event-wizard"></a><a name="_core_stock_events_supported_by_classwizard"></a>Фондовые события, поддерживаемые Мастером События Добавления

Класс `COleControl` предоставляет десять событий, перечисленных в следующей таблице. Вы можете указать события, которые вы хотите в вашем управлении с помощью [Мастера Событий Добавления](../ide/add-event-wizard.md).

### <a name="stock-events"></a>Фондовые события

|Событие|Функция стрельбы|Комментарии|
|-----------|---------------------|--------------|
|Щелкните |**пустота FireClick ()**|Когда элемент управления захватывает мышь, получается любое сообщение **BUTTONUP** (слева, посередине или справа), и кнопка освобождается над управлением. События акции MouseDown и MouseUp происходят до этого события.<br /><br /> Запись на карту событий: **EVENT_STOCK_CLICK ()**|
|DblClick|**пустота FireDblClick ()**|Подобно нажмите кнопку, но выстрелил, когда **сообщение BUTTONDBLCLK** получено.<br /><br /> Запись на карту событий: **EVENT_STOCK_DBLCLICK ()**|
|Error|**пустота FireError (SCODE***scode* **, LPCSTR** `lpszDescription` , **UINT**`nHelpID`**No 0 )**        |Выполняется при возникновении ошибки в элементе управления ActiveX вне сферы действия вызова метода или доступа к свойствам.<br /><br /> Вход на карту событий: **EVENT_STOCK_ERROREVENT ()**|
|KeyDown|**пустота FireKeyDown (короткий,** `nChar` **короткий**`nShiftState`**)**      |Уволен, `WM_SYSKEYDOWN` когда `WM_KEYDOWN` получено сообщение или сообщение.<br /><br /> Вход на карту событий: **EVENT_STOCK_KEYDOWN ()**|
|Keypress|**пустота FireKeyPress (короткий** <strong>\*</strong> `pnChar` **)**    |Уволен о `WM_CHAR` своем сообщении.<br /><br /> Запись на карту событий: **EVENT_STOCK_KEYPRESS ()**|
|KeyUp|**пустота FireKeyUp (короткий,** `nChar` **короткий**`nShiftState`**)**      |Уволен, `WM_SYSKEYUP` когда `WM_KEYUP` получено сообщение или сообщение.<br /><br /> Запись на карту событий: **EVENT_STOCK_KEYUP()**|
|Mousedown|**пустота FireMouseDown (короткий,** `nButton` **короткий** `nShiftState` **, поплавок***х* **, поплавок***у***)**          |Уволен, если получено **какое-либо КНОПКДАУН** (слева, середине или справа). Мышь захватывается непосредственно перед этим событием.<br /><br /> Вход на карту событий: **EVENT_STOCK_MOUSEDOWN ()**|
|Mousemove|**пустота FireMouseMove (короткий,** `nButton` **короткий** `nShiftState` **, поплавок***х* **, поплавок***у***)**          |Уволен о своем WM_MOUSEMOVE сообщении.<br /><br /> Запись на карту событий: **EVENT_STOCK_MOUSEMOVE ()**|
|Mouseup|**пустота FireMouseUp (короткий,** `nButton` **короткий** `nShiftState` **, поплавок***х* **, поплавок***у***)**          |Уволен, если **получен** остановится (слева, середине или вправо). Захват мыши освобождается до того, как это событие будет запущено.<br /><br /> Запись на карту событий: **EVENT_STOCK_MOUSEUP()**|
|ReadyStateChange|**пустота FireReadyStateChange ()**|Сражан при переходе элемента управления в следующее готовое состояние из-за объема полученных данных.<br /><br /> Вход на карту событий: **EVENT_STOCK_READYSTATECHANGE ()**|

## <a name="adding-a-stock-event-using-the-add-event-wizard"></a><a name="_core_adding_a_stock_event_using_classwizard"></a>Добавление события stock с использованием мастера события добавления

Добавление событий запасов требует меньше работы, чем добавление пользовательских событий, поскольку запуск фактического события обрабатывается автоматически базовым классом. `COleControl` Следующая процедура добавляет событие запаса в элемент управления, который был разработан с помощью [MFC ActiveX Control Wizard.](../mfc/reference/mfc-activex-control-wizard.md) Событие, называемое KeyPress, пожаров, когда ключ нажат и контроль активен. Эта процедура также может быть использована для добавления других событий акций. Замените выбранное название события акции для KeyPress.

#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>Чтобы добавить событие акции KeyPress с помощью Мастера событий Добавления

1. Загрузите проект элемента управления.

1. В классе View, правой кнопкой мыши вашего класса управления ActiveX, чтобы открыть меню ярлыка.

1. Из меню ярлыка нажмите **Добавить,** а затем нажмите **Добавить событие**.

   Это открывает Мастер события добавления.

1. В списке выпадающих имен `KeyPress` **события** выберите .

1. Нажмите кнопку **Готово**.

## <a name="add-event-wizard-changes-for-stock-events"></a><a name="_core_classwizard_changes_for_stock_events"></a>Добавление изменений мастера событий для событий стока

Поскольку события стока обрабатываются базовым классом элемента управления, мастер событий Add Никоим образом не изменяет декларацию класса. Он добавляет событие в карту событий элемента управления и делает запись в ее . IdL файл. Следующая строка добавляется на карту событий элемента управления, расположенную в реализации класса управления (. CPP) файл:

[!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]

Добавление этого кода запускает событие KeyPress, когда получено WM_CHAR сообщение и управление активен. Событие KeyPress может быть уволено в другое время, `FireKeyPress`позвонив в функцию стрельбы (например, ) из кода управления.

Мастер событий Добавить добавляет следующую строку кода в элемент управления. IDL файл:

[!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]

Эта линия ассоциирует событие KeyPress с его стандартным идентификатором отправки и позволяет контейнеру предвидеть событие KeyPress.

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)<br/>
[Элементы ActiveX в MFC. Методы](../mfc/mfc-activex-controls-methods.md)<br/>
[Класс COleControl](../mfc/reference/colecontrol-class.md)
