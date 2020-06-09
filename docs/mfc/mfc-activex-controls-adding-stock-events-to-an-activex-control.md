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
ms.openlocfilehash: a97c08baaf3c11b0436e52bb4fd4ac380999d69a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615593"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>Элементы управления ActiveX в MFC. Добавление событий хранения в элемент управления ActiveX

События на бирже отличаются от пользовательских событий тем, что они автоматически запускаются классом [COleControl](reference/colecontrol-class.md). `COleControl`содержит стандартные функции элементов, которые инициируют события, полученные в результате общих действий. Некоторые распространенные действия, реализуемые, `COleControl` включают в себя одинарные и двойные щелчки мышью, события клавиатуры и изменения в состоянии кнопок мыши. Записям схемы событий для событий акции всегда предшествует префикс EVENT_STOCK.

## <a name="stock-events-supported-by-the-add-event-wizard"></a><a name="_core_stock_events_supported_by_classwizard"></a>События хранения, поддерживаемые мастером добавления событий

`COleControl`Класс предоставляет десять стандартных событий, перечисленных в следующей таблице. Вы можете указать нужные события в элементе управления с помощью [мастера добавления событий](../ide/add-event-wizard.md).

### <a name="stock-events"></a>События акции

|Событие|Срабатывание функции|Комментарии|
|-----------|---------------------|--------------|
|Нажмите кнопку|**void Фирекликк ()**|Возникает, когда элемент управления захватывает мышь, получается любое **буттонуп** (левое, среднее или правое) сообщение, а кнопка выводится над элементом управления. События MouseDown и MouseUp происходят перед этим событием.<br /><br /> Запись схемы событий: **EVENT_STOCK_CLICK ()**|
|Кнопки|**void Фиредблкликк ()**|Аналогичен щелчку, но срабатывает при получении сообщения **буттондблклк** .<br /><br /> Запись схемы событий: **EVENT_STOCK_DBLCLICK ()**|
|Ошибка|**void фириррор (SCODE***SCODE* **, LPCSTR** `lpszDescription` **, uint** `nHelpID` **= 0)**        |Возникает при возникновении ошибки в элементе управления ActiveX за пределами области вызова метода или доступа к свойству.<br /><br /> Запись схемы событий: **EVENT_STOCK_ERROREVENT ()**|
|KeyDown|**void фирекэйдовн (короткий** `nChar` **, короткий** `nShiftState` **)**      |Возникает при `WM_SYSKEYDOWN` `WM_KEYDOWN` получении сообщения или.<br /><br /> Запись схемы событий: **EVENT_STOCK_KEYDOWN ()**|
|Бытии|**void фирекэйпресс (Short** <strong>\*</strong> `pnChar` **)**    |Возникает при `WM_CHAR` получении сообщения.<br /><br /> Запись схемы событий: **EVENT_STOCK_KEYPRESS ()**|
|KeyUp|**void фирекэйуп (короткий** `nChar` **, короткий** `nShiftState` **)**      |Возникает при `WM_SYSKEYUP` `WM_KEYUP` получении сообщения или.<br /><br /> Запись схемы событий: **EVENT_STOCK_KEYUP ()**|
|Вниз|**void фиремауседовн (Short** `nButton` **, Short** `nShiftState` **, float***x* **, float***y***)**          |Активируется, когда получается любой **PreviewMouseLeftButtonDown** (левый, средний или правый). Мышь записывается непосредственно перед срабатыванием этого события.<br /><br /> Запись схемы событий: **EVENT_STOCK_MOUSEDOWN ()**|
|Событие|**void фиремаусемове (Short** `nButton` **, Short** `nShiftState` **, float***x* **, float***y***)**          |Возникает при получении сообщения WM_MOUSEMOVE.<br /><br /> Запись схемы событий: **EVENT_STOCK_MOUSEMOVE ()**|
|Кнопка|**void фиремаусеуп (Short** `nButton` **, Short** `nShiftState` **, float***x* **, float***y***)**          |Активируется, когда получается любой **буттонуп** (левый, средний или правый). Захват мыши освобождается перед срабатыванием этого события.<br /><br /> Запись схемы событий: **EVENT_STOCK_MOUSEUP ()**|
|реадистатечанже|**void Фиререадистатечанже ()**|Возникает, когда элемент управления переходит к следующему состоянию готовности из-за объема полученных данных.<br /><br /> Запись схемы событий: **EVENT_STOCK_READYSTATECHANGE ()**|

## <a name="adding-a-stock-event-using-the-add-event-wizard"></a><a name="_core_adding_a_stock_event_using_classwizard"></a>Добавление события акции с помощью мастера добавления событий

Добавление событий акции требует меньше работы, чем добавление пользовательских событий, так как срабатывание фактического события автоматически обрабатывается базовым классом `COleControl` . Следующая процедура добавляет событие акции в элемент управления, разработанный с помощью [мастера элементов управления ActiveX MFC](reference/mfc-activex-control-wizard.md). Событие, именуемое KeyPress, срабатывает при нажатии клавиши, когда элемент управления активен. Эту процедуру также можно использовать для добавления других событий хранения. Замените выбранное имя события на бирже нажатием клавиши.

#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>Добавление события «событие акции» с помощью мастера добавления событий

1. Загрузите проект элемента управления.

1. В представление классов щелкните правой кнопкой мыши класс элемента управления ActiveX, чтобы открыть контекстное меню.

1. В контекстном меню выберите **Добавить** , а затем — **Добавить событие**.

   Откроется мастер добавления событий.

1. В раскрывающемся списке **имя события** выберите `KeyPress` .

1. Нажмите кнопку **Готово**.

## <a name="add-event-wizard-changes-for-stock-events"></a><a name="_core_classwizard_changes_for_stock_events"></a>Изменения мастера добавления событий для событий хранения

Поскольку события на бирже обрабатываются базовым классом элемента управления, мастер добавления событий не изменяет объявление класса каким-либо образом. Он добавляет событие в карту событий элемента управления и создает запись в его свойстве. IDL-файл. Следующая строка добавляется в карту событий элемента управления, расположенную в реализации класса элемента управления (. Файл CPP):

[!code-cpp[NVC_MFC_AxUI#5](codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]

Добавление этого кода вызывает событие KeyPress, когда получено WM_CHAR сообщение и элемент управления активен. Событие KeyPress может быть вызвано в другое время путем вызова функции, вызвавшей срабатывание (например, `FireKeyPress` ) в управляющем коде.

Мастер добавления событий добавляет следующую строку кода в элемент управления. IDL-файл:

[!code-cpp[NVC_MFC_AxUI#6](codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]

Эта строка связывает событие KeyPress с его стандартным ИДЕНТИФИКАТОРом диспетчеризации и позволяет контейнеру ожидать событие KeyPress.

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](mfc-activex-controls.md)<br/>
[Элементы ActiveX в MFC. Методы](mfc-activex-controls-methods.md)<br/>
[Класс COleControl](reference/colecontrol-class.md)
