---
title: 'Элементы ActiveX в MFC: Добавление событий хранения в элемент управления ActiveX | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bf023dbc52ccac7311a62aba1a290b1a03190dd
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060563"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>Элементы управления ActiveX в MFC. Добавление событий хранения в элемент управления ActiveX

Событий хранения отличаются от пользовательских событий, что они запускаются автоматически классом [COleControl](../mfc/reference/colecontrol-class.md). `COleControl` содержит функции стандартных элементов, которые инициируют события, полученные в результате распространенных действий. Некоторые стандартные действия, реализуемый `COleControl` включить одним - и двойным - clicks на элемент управления, события клавиатуры и изменения в состояние кнопок мыши. Записей для акции, которые события всегда предшествует event_stock-префикс сопоставления событий.

##  <a name="_core_stock_events_supported_by_classwizard"></a> Биржевые события, поддерживаемые мастер добавления события

`COleControl` Класс предоставляет десять основных событий биржевых, перечисленные в следующей таблице. Можно указать события, в элемент управления с помощью [мастер добавления событий](../ide/add-event-wizard.md).

### <a name="stock-events"></a>Событий биржевых

|событие|Запуск функции|Комментарии|
|-----------|---------------------|--------------|
|Нажмите кнопку|**void (FireClick)**|Возникает, когда элемент управления захвате мыши, в любом **BUTTONUP** (левая, Средняя или правая) сообщение и кнопка отпущена над элементом управления. Биржевая MouseDown и MouseUp события возникают до этого события.<br /><br /> Запись сопоставления событий: **EVENT_STOCK_CLICK)**|
|Двойное нажатие кнопки|**void (FireDblClick)**|Аналогично до щелчка, но возникающее когда **BUTTONDBLCLK** сообщение.<br /><br /> Запись сопоставления событий: **EVENT_STOCK_DBLCLICK)**|
|Error|**void FireError (SCODE***scode* **, LPCSTR** `lpszDescription` **, целое число без знака**`nHelpID`**= 0)**|Инициируется при возникновении ошибки в элементе управления ActiveX за пределами области метода вызова или свойство с доступом.<br /><br /> Запись сопоставления событий: **EVENT_STOCK_ERROREVENT)**|
|KeyDown|**void FireKeyDown (короткий** `nChar` **, short**`nShiftState`**)**|Возникает, когда `WM_SYSKEYDOWN` или `WM_KEYDOWN` сообщение.<br /><br /> Запись сопоставления событий: **EVENT_STOCK_KEYDOWN)**|
|Нажатие клавиши|**void FireKeyPress (короткий** <strong>\*</strong> `pnChar` **)**|Которые возникают после `WM_CHAR` сообщение.<br /><br /> Запись сопоставления событий: **EVENT_STOCK_KEYPRESS)**|
|KeyUp|**void FireKeyUp (короткий** `nChar` **, short**`nShiftState`**)**|Возникает, когда `WM_SYSKEYUP` или `WM_KEYUP` сообщение.<br /><br /> Запись сопоставления событий: **EVENT_STOCK_KEYUP)**|
|MouseDown|**void FireMouseDown (короткий** `nButton` **, short** `nShiftState` **, число с плавающей запятой***x* **, число с плавающей запятой** *y***)**|Возникает, если любой **BUTTONDOWN** получении (слева, середине или справа). Непосредственно перед это событие срабатывает, захват мыши.<br /><br /> Запись сопоставления событий: **EVENT_STOCK_MOUSEDOWN)**|
|MouseMove|**void FireMouseMove (короткий** `nButton` **, short** `nShiftState` **, число с плавающей запятой***x* **, число с плавающей запятой** *y***)**|Инициируется, когда поступает сообщение WM_MOUSEMOVE.<br /><br /> Запись сопоставления событий: **EVENT_STOCK_MOUSEMOVE)**|
|MouseUp|**void FireMouseUp (короткий** `nButton` **, short** `nShiftState` **, число с плавающей запятой***x* **, число с плавающей запятой** *y***)**|Возникает, если любой **BUTTONUP** получении (слева, середине или справа). Захват мыши освобождается, прежде чем это событие вызывается.<br /><br /> Запись сопоставления событий: **EVENT_STOCK_MOUSEUP)**|
|ReadyStateChange|**void (FireReadyStateChange)**|Инициируется при переходе элемента управления в следующее состояние готовности, из-за количество полученных данных.<br /><br /> Запись сопоставления событий: **EVENT_STOCK_READYSTATECHANGE)**|

##  <a name="_core_adding_a_stock_event_using_classwizard"></a> Стандартное событие, используя мастер добавления события

Добавление событий хранения требует меньше усилий, чем добавление пользовательских событий, поскольку обработке фактического события автоматически обрабатывается базовым классом, `COleControl`. В следующей процедуре добавляется стандартное событие элемента управления, который был разработан с использованием [мастер элементов управления ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md). Событие, называется KeyPress, возникает, когда нажата клавиша и элемент управления активен. Эта процедура также может использоваться для добавления других событий биржевых. Подставьте имя выбранного стандартное событие KeyPress.

#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>Чтобы добавить стандартное событие нажатия клавиши, с помощью мастера добавления события

1. Загрузите проект элемента управления.

1. В представлении классов щелкните правой кнопкой мыши по классу элемента управления ActiveX, чтобы открыть контекстное меню.

1. В контекстном меню, щелкните **добавить** и нажмите кнопку **добавить событие**.

   Откроется мастер добавления события.

1. В **имя события** стрелку раскрывающегося списка выберите `KeyPress`.

1. Нажмите кнопку **Готово**.

##  <a name="_core_classwizard_changes_for_stock_events"></a> Добавить мастер изменения событий для событий биржевых

Поскольку событий биржевых обрабатываются базовый класс элемента управления, мастер добавления события не приводит к изменению к объявлению класса любым способом. Она добавляет событие схема событий элемента управления и делает запись в его. IDL-файла. Следующая строка добавляется схема событий элемента управления, расположенный в реализации класса элемента управления (. Файл CPP):

[!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]

Добавив следующий код запускает событие KeyPress при получении сообщения WM_CHAR и элемент управления активен. Это событие нажатия клавиши может генерироваться в другое время путем вызова функции обработки (например, `FireKeyPress`) из кода элемента управления.

Мастер добавления события добавляется следующая строка кода для элемента управления. IDL-файла:

[!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]

Эта строка связывает событие нажатия клавиши с его идентификатор диспетчеризации standard и позволяет контейнеру реагировать на событие нажатия клавиши.

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)<br/>
[Элементы ActiveX в MFC. Методы](../mfc/mfc-activex-controls-methods.md)<br/>
[Класс COleControl](../mfc/reference/colecontrol-class.md)
