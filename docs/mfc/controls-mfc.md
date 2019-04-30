---
title: Элементы управления (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC]
- common controls [MFC]
- controls [MFC]
ms.assetid: b2842884-6435-4b8f-933b-21671bf8af95
ms.openlocfilehash: c0738128d20839046e0885e7489b494d84349e4d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297272"
---
# <a name="controls-mfc"></a>Элементы управления (MFC)

Элементы управления — это объекты, используемые для ввода данных и работы с ними. Как правило, они отображаются в диалоговых окнах и на панелях инструментов. В этом документе рассматриваются три основных типа элементов управления.

- Стандартные элементы управления Windows, включая создаваемые владельцем элементы управления

- Элементы управления ActiveX

- Другие классы элементов управления из библиотеки MFC

## <a name="windows-common-controls"></a>Стандартные элементы управления Windows

В ОС Windows всегда существовал ряд стандартных элементов управления Windows. Эти объекты элементов управления являются программируемыми и редактор диалоговых окон Visual C++ поддерживает их добавление в диалоговые окна. Библиотека MFC предоставляет классы, инкапсулирующие все эти элементы управления, как показано в таблице [Стандартные элементы управления Windows и классы MFC](#_core_windows_common_controls_and_mfc_classes). (Для некоторых элементов в таблице существуют связанные разделы с дальнейшим описанием. Если для элементов управления связанные разделы отсутствуют, см. документацию по классу MFC.)

Класс [CWnd](../mfc/reference/cwnd-class.md) является базовым для всех классов окон, включая все классы элементов управления.

## <a name="activex-controls"></a>Элементы управления ActiveX

Элементы управления ActiveX, ранее известные как элементы управления OLE, можно использовать в диалоговых окнах в приложениях для Windows или на HTML-страницах в Интернете. Более подробную информацию см. в разделе [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md).

## <a name="other-mfc-control-classes"></a>Другие классы элементов управления MFC

Наряду с классами, инкапсулирующими все стандартные элементы управления Windows и поддерживающими программирование пользовательских элементов управления ActiveX (или использование элементов управления ActiveX, предоставляемых другими пользователями), MFC предоставляет следующие свои классы элементов управления:

- [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)

- [CCheckListBox](../mfc/reference/cchecklistbox-class.md)

- [CDragListBox](../mfc/reference/cdraglistbox-class.md)

##  <a name="_core_finding_information_about_windows_common_controls"></a> Сведения о стандартных элементах управления Windows

В следующей таблице содержится краткое описание стандартных элементов управления Windows, включая класс-оболочку MFC элемента управления.

### <a name="_core_windows_common_controls_and_mfc_classes"></a>  Стандартные элементы управления Windows и классы MFC

|Элемент управления|Класс MFC|Описание|Новое в Windows 95|
|-------------|---------------|-----------------|------------------------|
|[анимация](../mfc/using-canimatectrl.md)|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|Отображение последовательных кадров видеоролика AVI.|Да|
|button|[CButton](../mfc/reference/cbutton-class.md)|Кнопки, вызывающие действия; также используется для флажков, переключателей и полей групп.|Нет|
|поле со списком|[CComboBox](../mfc/reference/ccombobox-class.md)|Комбинация текстового поля и поля со списком.|Нет|
|[элемент выбора даты и времени](../mfc/using-cdatetimectrl.md)|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|Позволяет выбирать определенное значение даты или времени.|Да|
|поле ввода|[CEdit](../mfc/reference/cedit-class.md)|Поля для ввода текста.|Нет|
|[расширенное поле со списком](../mfc/using-ccomboboxex.md)|[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)|Поле со списком с возможностью отображения изображений.|Да|
|[заголовок](../mfc/using-cheaderctrl.md)|[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)|Кнопка, которая появляется над столбцом текста. Определяет ширину отображаемого текста.|Да|
|[сочетание клавиш](../mfc/using-chotkeyctrl.md)|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|Окно, позволяющее создавать сочетания клавиш для быстрого выполнения действий.|Да|
|[список изображений](../mfc/using-cimagelist.md)|[CImageList](../mfc/reference/cimagelist-class.md)|Коллекция изображений, используемых для управления большими наборами значков и точечных рисунков (на самом деле список изображений не является элементом управления — он поддерживает списки, используемые другими элементами управления).|Да|
|[list](../mfc/using-clistctrl.md)|[CListCtrl](../mfc/reference/clistctrl-class.md)|Окно, отображающее список текста со значками.|Да|
|список|[CListBox](../mfc/reference/clistbox-class.md)|Поле, содержащее список строк.|Нет|
|[календарь месяца](../mfc/using-cmonthcalctrl.md)|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|Элемент управления, отображающий сведения о дате.|Да|
|[ход выполнения](../mfc/using-cprogressctrl.md)|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|Окно, в котором отображается ход выполнения длительной операции.|Да|
|[главная панель](../mfc/using-crebarctrl.md)|[CRebarCtrl](../mfc/reference/crebarctrl-class.md)|Панель инструментов, которая может содержать дополнительные дочерние окна в виде элементов управления.|Да|
|[ввод с форматированием](../mfc/using-cricheditctrl.md)|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|Окно, в котором можно выполнять редактирование с форматированием символов и абзацев (см. раздел [Классы, связанные с элементами управления Rich Edit](../mfc/classes-related-to-rich-edit-controls.md)).|Да|
|полоса прокрутки|[CScrollBar](../mfc/reference/cscrollbar-class.md)|Полоса прокрутки, используемая как элемент управления в диалоговом окне (не в окне).|Нет|
|[ползунок](../mfc/using-csliderctrl.md)|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|Окно, содержащее элемент управления "Ползунок" с необязательными делениями.|Да|
|[кнопка "Счетчик"](../mfc/using-cspinbuttonctrl.md)|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|Пара кнопок со стрелками для увеличения или уменьшения значения.|Да|
|статический текст|[CStatic](../mfc/reference/cstatic-class.md)|Текст для надписей других элементов управления.|Нет|
|[строка состояния](../mfc/using-cstatusbarctrl.md)|[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)|Окно для отображения сведений о состоянии, аналогичное классу MFC `CStatusBar`.|Да|
|[вкладка](../mfc/using-ctabctrl.md)|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|Аналог разделителей в записной книжке. Используется в диалоговых окнах с вкладками или таблицах свойств.|Да|
|[панель инструментов](../mfc/using-ctoolbarctrl.md)|[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)|Окно с генерирующими команды кнопками, аналогичное классу MFC `CToolBar`.|Да|
|[подсказка](../mfc/using-ctooltipctrl.md)|[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)|Небольшое всплывающее окно с описанием назначения кнопки панели инструментов или другого инструмента.|Да|
|[дерево](../mfc/using-ctreectrl.md)|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|Окно, в котором отображается иерархический список элементов.|Да|

### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- Отдельный элемент управления: см. таблицу [Стандартные элементы управления Windows и классы MFC](#_core_windows_common_controls_and_mfc_classes) в этом разделе, содержащую ссылки на все элементы управления.

- [Создание и использование элементов управления](../mfc/making-and-using-controls.md)

- [Использование редактора диалоговых окон для добавления элементов управления](../mfc/using-the-dialog-editor-to-add-controls.md)

- [Добавление элементов управления в диалоговое окно вручную](../mfc/adding-controls-by-hand.md)

- [Наследование классов элементов управления от классов элементов управления MFC](../mfc/deriving-controls-from-a-standard-control.md)

- [Использование стандартных элементов управления в качестве дочерних окон](../mfc/using-a-common-control-as-a-child-window.md)

- [Уведомления из стандартных элементов управления](../mfc/receiving-notification-from-common-controls.md)

- [Добавление стандартных элементов управления в диалоговое окно](../mfc/using-common-controls-in-a-dialog-box.md)

- [Получение элемента управления из стандартного элемента управления Windows](../mfc/deriving-controls-from-a-standard-control.md)

- [Доступ к элементам управления диалогового окна с безопасностью типа](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [Получение уведомлений из стандартных элементов управления](../mfc/receiving-notification-from-common-controls.md)

- [Примеры](../mfc/common-control-sample-list.md)

Сведения о стандартных элементах управления Windows в пакете SDK для Windows, см. в разделе [стандартные элементы управления](/windows/desktop/Controls/common-controls-intro).

## <a name="see-also"></a>См. также

[Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)<br/>
[Редактор диалоговых окон](../windows/dialog-editor.md)
