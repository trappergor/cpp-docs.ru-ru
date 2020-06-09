---
title: Элементы управления (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC]
- common controls [MFC]
- controls [MFC]
ms.assetid: b2842884-6435-4b8f-933b-21671bf8af95
ms.openlocfilehash: accbee66cdee4e7b849da2b034d253b1c206d8f1
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617182"
---
# <a name="controls-mfc"></a>Элементы управления (MFC)

Элементы управления — это объекты, используемые для ввода данных и работы с ними. Как правило, они отображаются в диалоговых окнах и на панелях инструментов. В этом документе рассматриваются три основных типа элементов управления.

- Стандартные элементы управления Windows, включая создаваемые владельцем элементы управления

- Элементы управления ActiveX

- Другие классы элементов управления из библиотеки MFC

## <a name="windows-common-controls"></a>Стандартные элементы управления Windows

В ОС Windows всегда существовал ряд стандартных элементов управления Windows. Эти объекты элементов управления являются программируемыми и редактор диалоговых окон Visual C++ поддерживает их добавление в диалоговые окна. Библиотека MFC предоставляет классы, инкапсулирующие все эти элементы управления, как показано в таблице [Стандартные элементы управления Windows и классы MFC](#_core_windows_common_controls_and_mfc_classes). (Для некоторых элементов в таблице существуют связанные разделы с дальнейшим описанием. Если для элементов управления связанные разделы отсутствуют, см. документацию по классу MFC.)

Класс [CWnd](reference/cwnd-class.md) является базовым для всех классов окон, включая все классы элементов управления.

## <a name="activex-controls"></a>Элементы управления ActiveX

Элементы управления ActiveX, ранее известные как элементы управления OLE, можно использовать в диалоговых окнах в приложениях для Windows или на HTML-страницах в Интернете. Дополнительные сведения см. в разделе [элементы управления ActiveX в MFC](mfc-activex-controls.md).

## <a name="other-mfc-control-classes"></a>Другие классы элементов управления MFC

Наряду с классами, инкапсулирующими все стандартные элементы управления Windows и поддерживающими программирование пользовательских элементов управления ActiveX (или использование элементов управления ActiveX, предоставляемых другими пользователями), MFC предоставляет следующие свои классы элементов управления:

- [CBitmapButton](reference/cbitmapbutton-class.md)

- [CCheckListBox](reference/cchecklistbox-class.md)

- [CDragListBox](reference/cdraglistbox-class.md)

## <a name="finding-information-about-windows-common-controls"></a><a name="_core_finding_information_about_windows_common_controls"></a> Сведения о стандартных элементах управления Windows

В следующей таблице содержится краткое описание стандартных элементов управления Windows, включая класс-оболочку MFC элемента управления.

### <a name="windows-common-controls-and-mfc-classes"></a><a name="_core_windows_common_controls_and_mfc_classes"></a>Общие элементы управления Windows и классы MFC

|Control|Класс MFC|Описание|Новые в Windows 95|
|-------------|---------------|-----------------|------------------------|
|[захоронен](using-canimatectrl.md)|[CAnimateCtrl](reference/canimatectrl-class.md)|Отображение последовательных кадров видеоролика AVI.|Да|
|кнопка|[CButton](reference/cbutton-class.md)|Кнопки, вызывающие действия; также используется для флажков, переключателей и полей групп.|Нет|
|поле со списком|[CComboBox](reference/ccombobox-class.md)|Комбинация текстового поля и поля со списком.|Нет|
|[элемент выбора даты и времени](using-cdatetimectrl.md)|[CDateTimeCtrl](reference/cdatetimectrl-class.md)|Позволяет выбирать определенное значение даты или времени.|Да|
|поле ввода|[CEdit](reference/cedit-class.md)|Поля для ввода текста.|Нет|
|[расширенное поле со списком](using-ccomboboxex.md)|[CComboBoxEx](reference/ccomboboxex-class.md)|Поле со списком с возможностью отображения изображений.|Да|
|[заголовок](using-cheaderctrl.md)|[CHeaderCtrl](reference/cheaderctrl-class.md)|Кнопка, которая появляется над столбцом текста. Определяет ширину отображаемого текста.|Да|
|[определяем](using-chotkeyctrl.md)|[CHotKeyCtrl](reference/chotkeyctrl-class.md)|Окно, позволяющее создавать сочетания клавиш для быстрого выполнения действий.|Да|
|[список изображений](using-cimagelist.md)|[CImageList](reference/cimagelist-class.md)|Коллекция изображений, используемых для управления большими наборами значков и точечных рисунков (на самом деле список изображений не является элементом управления — он поддерживает списки, используемые другими элементами управления).|Да|
|[list](using-clistctrl.md)|[CListCtrl](reference/clistctrl-class.md)|Окно, отображающее список текста со значками.|Да|
|список|[CListBox](reference/clistbox-class.md)|Поле, содержащее список строк.|Нет|
|[месячный календарь](using-cmonthcalctrl.md)|[CMonthCalCtrl](reference/cmonthcalctrl-class.md)|Элемент управления, отображающий сведения о дате.|Да|
|[двигается](using-cprogressctrl.md)|[CProgressCtrl](reference/cprogressctrl-class.md)|Окно, в котором отображается ход выполнения длительной операции.|Да|
|[главная панель](using-crebarctrl.md)|[CRebarCtrl](reference/crebarctrl-class.md)|Панель инструментов, которая может содержать дополнительные дочерние окна в виде элементов управления.|Да|
|[ввод с форматированием](using-cricheditctrl.md)|[CRichEditCtrl](reference/cricheditctrl-class.md)|Окно, в котором можно выполнять редактирование с форматированием символов и абзацев (см. раздел [Классы, связанные с элементами управления Rich Edit](classes-related-to-rich-edit-controls.md)).|Да|
|полоса прокрутки|[CScrollBar](reference/cscrollbar-class.md)|Полоса прокрутки, используемая как элемент управления в диалоговом окне (не в окне).|Нет|
|[группу](using-csliderctrl.md)|[CSliderCtrl](reference/csliderctrl-class.md)|Окно, содержащее элемент управления "Ползунок" с необязательными делениями.|Да|
|[кнопка "Счетчик"](using-cspinbuttonctrl.md)|[CSpinButtonCtrl](reference/cspinbuttonctrl-class.md)|Пара кнопок со стрелками для увеличения или уменьшения значения.|Да|
|статический текст|[CStatic](reference/cstatic-class.md)|Текст для надписей других элементов управления.|Нет|
|[Строка состояния](using-cstatusbarctrl.md)|[CStatusBarCtrl](reference/cstatusbarctrl-class.md)|Окно для отображения сведений о состоянии, аналогичное классу MFC `CStatusBar`.|Да|
|[вкладке](using-ctabctrl.md)|[CTabCtrl](reference/ctabctrl-class.md)|Аналог разделителей в записной книжке. Используется в диалоговых окнах с вкладками или таблицах свойств.|Да|
|[панелей](using-ctoolbarctrl.md)|[CToolBarCtrl](reference/ctoolbarctrl-class.md)|Окно с генерирующими команды кнопками, аналогичное классу MFC `CToolBar`.|Да|
|[всплывающая подсказка](using-ctooltipctrl.md)|[CToolTipCtrl](reference/ctooltipctrl-class.md)|Небольшое всплывающее окно с описанием назначения кнопки панели инструментов или другого инструмента.|Да|
|[tree](using-ctreectrl.md)|[CTreeCtrl](reference/ctreectrl-class.md)|Окно, в котором отображается иерархический список элементов.|Да|

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- Отдельный элемент управления: см. таблицу [Стандартные элементы управления Windows и классы MFC](#_core_windows_common_controls_and_mfc_classes) в этом разделе, содержащую ссылки на все элементы управления.

- [Создание и использование элементов управления](making-and-using-controls.md)

- [Использование редактора диалоговых окон для добавления элементов управления](using-the-dialog-editor-to-add-controls.md)

- [Добавление элементов управления в диалоговое окно вручную](adding-controls-by-hand.md)

- [Наследование классов элементов управления от классов элементов управления MFC](deriving-controls-from-a-standard-control.md)

- [Использование стандартных элементов управления в качестве дочерних окон](using-a-common-control-as-a-child-window.md)

- [Уведомления из стандартных элементов управления](receiving-notification-from-common-controls.md)

- [Добавление стандартных элементов управления в диалоговое окно](using-common-controls-in-a-dialog-box.md)

- [Получение элемента управления из стандартного элемента управления Windows](deriving-controls-from-a-standard-control.md)

- [Доступ к элементам управления диалогового окна с безопасностью типа](type-safe-access-to-controls-in-a-dialog-box.md)

- [Получение уведомлений из стандартных элементов управления](receiving-notification-from-common-controls.md)

- [Примеры](common-control-sample-list.md)

Сведения о стандартных элементах управления Windows в Windows SDK см. в разделе [Общие элементы управления](/windows/win32/Controls/common-controls-intro).

## <a name="see-also"></a>См. также раздел

[Элементы пользовательского интерфейса](user-interface-elements-mfc.md)<br/>
[Редактор диалоговых окон](../windows/dialog-editor.md)
