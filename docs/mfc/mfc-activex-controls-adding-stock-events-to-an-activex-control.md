---
title: 'Элементы управления ActiveX MFC: Добавление событий хранения в элемент управления ActiveX | Документы Microsoft'
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
ms.openlocfilehash: 41445015f30eb953675f763652fb85ef3eeb857a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930791"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>Элементы управления ActiveX в MFC. Добавление событий хранения в элемент управления ActiveX
Событий хранения отличаются от пользовательских событий, автоматически запускаются классом [COleControl](../mfc/reference/colecontrol-class.md). `COleControl` содержит функции стандартных элементов, которые инициируют события, возникающие в результате общие действия. Некоторые общие действия, реализуемый `COleControl` включить одним - и двойным - clicks на элемент управления, события клавиатуры и изменения в состояние кнопок мыши. События сопоставления записи для бумагу события всегда предшествует EVENT_STOCK-префикс.  
  
##  <a name="_core_stock_events_supported_by_classwizard"></a> События, поддерживаемые Stock мастер добавления события  
 `COleControl` Класс предоставляет десять событий хранения, перечисленные в следующей таблице. Можно указать события, в элементе управления с помощью [мастер добавления события](../ide/add-event-wizard.md).  
  
### <a name="stock-events"></a>Событий хранения  
  
|событие|Вызов функции|Комментарии|  
|-----------|---------------------|--------------|  
|Нажмите кнопку|**void (FireClick)**|Возникает, когда элемент управления захватывает мышь, все **BUTTONUP** (левая, Средняя или правая) сообщение и отпускается кнопка над элементом управления. Биржевая MouseDown и MouseUp события возникают до этого события.<br /><br /> Запись сопоставления событий: **(EVENT_STOCK_CLICK)**|  
|Двойное нажатие кнопки|**void (FireDblClick)**|Аналогично щелкните создается, но при **BUTTONDBLCLK** сообщение.<br /><br /> Запись сопоставления событий: **(EVENT_STOCK_DBLCLICK)**|  
|Error|**void FireError (SCODE***scode* **, LPCSTR** `lpszDescription` **, UINT**`nHelpID`**= 0)** |Возникает, когда происходит ошибка в элементе управления ActiveX вне области метода вызова или доступ к свойству.<br /><br /> Запись сопоставления событий: **(EVENT_STOCK_ERROREVENT)**|  
|KeyDown|**void FireKeyDown (короткое** `nChar` **, short**`nShiftState`**)** |Возникает, когда `WM_SYSKEYDOWN` или `WM_KEYDOWN` сообщение.<br /><br /> Запись сопоставления событий: **(EVENT_STOCK_KEYDOWN)**|  
|Нажатие клавиши|**void FireKeyPress (короткое\***`pnChar`**)** |Возникает, когда `WM_CHAR` сообщение.<br /><br /> Запись сопоставления событий: **(EVENT_STOCK_KEYPRESS)**|  
|Клавиша вверх|**void FireKeyUp (короткое** `nChar` **, short**`nShiftState`**)** |Возникает, когда `WM_SYSKEYUP` или `WM_KEYUP` сообщение.<br /><br /> Запись сопоставления событий: **(EVENT_STOCK_KEYUP)**|  
|MouseDown|**void FireMouseDown (короткое** `nButton` **, short** `nShiftState` **, float***x* **, float** *y***)** |Возникает, если любой **BUTTONDOWN** получении (влево, среднего или вправо). Мышь захвачена непосредственно перед этого события.<br /><br /> Запись сопоставления событий: **(EVENT_STOCK_MOUSEDOWN)**|  
|MouseMove|**void FireMouseMove (короткое** `nButton` **, short** `nShiftState` **, float***x* **, float** *y***)** |Возникает, когда получает сообщение WM_MOUSEMOVE.<br /><br /> Запись сопоставления событий: **(EVENT_STOCK_MOUSEMOVE)**|  
|MouseUp|**void FireMouseUp (короткое** `nButton` **, short** `nShiftState` **, float***x* **, float** *y***)** |Возникает, если любой **BUTTONUP** получении (влево, среднего или вправо). Захват мыши освобождается до этого события.<br /><br /> Запись сопоставления событий: **(EVENT_STOCK_MOUSEUP)**|  
|ReadyStateChange|**void (FireReadyStateChange)**|Возникает, когда выполняется передача управления в следующее состояние готовности, из-за количество полученных данных.<br /><br /> Запись сопоставления событий: **(EVENT_STOCK_READYSTATECHANGE)**|  
  
##  <a name="_core_adding_a_stock_event_using_classwizard"></a> Стандартное событие, используя мастер добавления события  
 Добавление событий хранения требует меньше работы, чем при добавлении пользовательских событий, так как срабатывание Фактическое событие обрабатывается базовым классом, автоматически `COleControl`. В следующей процедуре добавляется стандартное событие для элемента управления, который был разработан с использованием [мастер элементов управления ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md). Событие вызывается нажатие клавиши, срабатывает при нажатии клавиши и элемент управления является активным. Эта процедура может также использоваться для добавления других стандартных событий. Замените имя выбранного стандартное событие для нажатие клавиши.  
  
#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>Чтобы добавить стандартное событие KeyPress, используя мастер добавления события  
  
1.  Загрузите проект элемента управления.  
  
2.  В представлении классов щелкните правой кнопкой мыши по классу элемента управления ActiveX, чтобы открыть контекстное меню.  
  
3.  В контекстном меню щелкните **добавить** и нажмите кнопку **добавить событие**.  
  
     Откроется мастер добавления события.  
  
4.  В **имя события** раскрывающемся списке выберите `KeyPress`.  
  
5.  Нажмите кнопку **Готово**.  
  
##  <a name="_core_classwizard_changes_for_stock_events"></a> Добавить мастер изменения событий для стандартных событий  
 Так как биржевые события обрабатываются базовый класс элемента управления, мастер добавления события не изменяется каким-либо образом объявления класса. Он добавляет событие элемента управления карты событий и делает запись в его. IDL-файл. Следующая строка добавляется схема событий элемента управления, расположенных в реализацию класса элемента управления (. Файл .cpp):  
  
 [!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]  
  
 Добавление этот код запускает событие Нажатие клавиши, если получено сообщение WM_CHAR и элемент управления является активным. KeyPress-событие может генерироваться в других случаях путем вызова функции обработки (например, `FireKeyPress`) из кода элемента управления.  
  
 Мастер добавления события добавляет следующую строку кода в элемент управления. IDL-файла:  
  
 [!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]  
  
 Эта строка связывает KeyPress-событие с Идентификатором его стандартной диспетчеризации, предоставляет контейнеру возможность предвидеть KeyPress-событие.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)   
 [Элементы управления MFC ActiveX: методы](../mfc/mfc-activex-controls-methods.md)   
 [Класс COleControl](../mfc/reference/colecontrol-class.md)
