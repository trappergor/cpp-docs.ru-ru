---
title: Классов элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.control
dev_langs:
- C++
helpviewer_keywords:
- static display controls [MFC]
- control classes [MFC]
- buttons, MFC control classes
- controls [MFC], MFC control classes
- controls [MFC]
- list boxes [MFC], MFC control classes
- control classes [MFC], MFC
- text, controls for input [MFC]
- user input [MFC], MFC control classes
ms.assetid: f9876606-9f5b-44cb-9135-213298d1df8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a159677ffa12961e7f065b2cba2b1287c8ef7a58
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432468"
---
# <a name="control-classes"></a>Классы элементов управления

Классы элементов управления инкапсулировать широкий спектр стандартных элементов управления Windows, от статических текстовых элементов управления, элементов управления. Кроме того MFC предоставляет некоторые новые элементы управления, включая кнопки с полосами точечные рисунки и управления.

Элементы управления, класс, имена которых заканчиваются на "**Ctrl**" впервые появившихся в Windows 95 и Windows NT версии 3.51.

## <a name="static-display-controls"></a>Элементы управления статическим отображением

[CStatic](../mfc/reference/cstatic-class.md)<br/>
Static-окно. Статические элементы управления используются для меток, поле или разделения других элементов управления в диалоговое окно или окно. Они также могут отображаться графических изображений, а не текст или поля.

## <a name="text-controls"></a>Текстовые элементы управления

[CEdit](../mfc/reference/cedit-class.md)<br/>
Окно ввода и редактирования текста элемента управления. Изменить элементы управления используются для приема текстовые входные данные от пользователя.

[CIPAddressCtrl](../mfc/reference/cipaddressctrl-class.md)<br/>
Поддерживает поле ввода для манипулирования адрес протокола Интернета (IP).

[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)<br/>
Элемент управления, в котором пользователь может вводить и редактировать текст. В отличие от элемента управления, инкапсулированных в `CEdit`, элементе управления rich edit поддерживает символов и абзацев и объекты OLE.

## <a name="controls-that-represent-numbers"></a>Элементы управления представляют собой числа

[CSliderCtrl](../mfc/reference/csliderctrl-class.md)<br/>
Элемент управления, содержащий "ползунок", в которой пользователь переходит на выберите значение или набор значений.

[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)<br/>
Пару кнопок со стрелками, пользователь может щелкнуть для увеличения или уменьшения значения.

[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)<br/>
Отображает прямоугольник, который постепенно заполняется слева направо для отображения хода выполнения операции.

[CScrollBar](../mfc/reference/cscrollbar-class.md)<br/>
Окно управления полосы прокрутки. Этот класс предоставляет функциональные возможности для полосы прокрутки, для использования в качестве элемента управления в диалоговое окно или окно, через который пользователь может указать положение в пределах диапазона.

## <a name="buttons"></a>Кнопки

[CButton](../mfc/reference/cbutton-class.md)<br/>
Окно элемента управления кнопки. Класс предоставляет программный интерфейс для кнопки, "флажок" или "переключатель" в диалоговом окне.

[CBitmapButton](../mfc/reference/cbitmapbutton-class.md)<br/>
Кнопка с точечный рисунок, а не текст подписи.

## <a name="lists"></a>Списки

[CListBox](../mfc/reference/clistbox-class.md)<br/>
Окно списка элемента управления. Поле со списком отображает список элементов, которые пользователь может просмотреть и выбрать.

[CDragListBox](../mfc/reference/cdraglistbox-class.md)<br/>
Предоставляет функции списка Windows; пользователь может перемещать элементы списка, такие как имена файлов и строковые литералы, в поле со списком. Списки с множественным благодаря этой возможности можно использовать для списка элементов в порядке, отличный от алфавитный, такие как включить пути или файлы в проект.

[CComboBox](../mfc/reference/ccombobox-class.md)<br/>
Окно управления полем со списком. Поле со списком состоит из элемента управления, а также в поле со списком.

[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)<br/>
Расширяет элемент управления "поле со списком", предоставляя поддержку списков изображений.

[CCheckListBox](../mfc/reference/cchecklistbox-class.md)<br/>
Отображает список элементов с флажками, которые пользователь может установите или снимите флажок, рядом с каждым элементом.

[CListCtrl](../mfc/reference/clistctrl-class.md)<br/>
Отображает коллекцию элементов, каждый элемент состоит из значок и метку, так же, как на правую панель проводника.

[CTreeCtrl](../mfc/reference/ctreectrl-class.md)<br/>
Отображает иерархический список значкам и меткам, расположенные в так же, как к левой панели проводника.

## <a name="toolbars-and-status-bars"></a>Панели инструментов и строки состояния

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)<br/>
Предоставляет функциональные возможности стандартного элемента управления "панель инструментов" Windows. Большинство MFC программы используют [CToolBar](../mfc/reference/ctoolbar-class.md) вместо этого класса.

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)<br/>
Окна по горизонтали, обычно разделены на области, в которых приложение может выводить сведения о состоянии. Большинство MFC программы используют [CStatusBar](../mfc/reference/cstatusbar-class.md) вместо этого класса.

## <a name="miscellaneous-controls"></a>Прочие элементы управления

[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)<br/>
Отображает простой видеоклипа.

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)<br/>
Небольшое всплывающее окно, которое отображается одна строка текста, описывающая назначение инструмента в приложении.

[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)<br/>
Поддерживает элемент управления расширенного редактирования или простой интерфейс календаря, позволяющий пользователю выбрать определенную дату или значение времени.

[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)<br/>
Отображение заголовков или меток столбцов.

[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)<br/>
Поддерживает элемент управления интерфейс простой календарь, позволяющий пользователю выбрать дату.

[CTabCtrl](../mfc/reference/ctabctrl-class.md)<br/>
Элемент управления с вкладками, на которых пользователь может щелкнуть, аналог разделителей в записной книжке.

[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)<br/>
Позволяет пользователю создавать "Горячий" сочетание клавиш, который пользователь может нажать для быстрого выполнения действий.

[CLinkCtrl](../mfc/reference/clinkctrl-class.md)<br/>
Отображает текст, помеченный и запускает соответствующие приложения, когда пользователь щелкает внедренную ссылку.

[CHtmlEditCtrl](../mfc/reference/chtmleditctrl-class.md)<br/>
Предоставляет функциональные возможности элемента управления ActiveX WebBrowser в окне MFC.

## <a name="related-classes"></a>Связанные классы

[CImageList](../mfc/reference/cimagelist-class.md)<br/>
Предоставляет функциональные возможности списка изображений Windows. Списки изображений используются с элементами управления списка и дерева элементов управления. Они также можно сохранить и заархивировать набора же разрядности точечных рисунков.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Базовый класс для всех представлений, связанных с элементами управления Windows. Ниже приведено описание представления, основанные на элементы управления.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Представление, содержащее Windows стандартного элемента управления edit.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Поле ввода представление, содержащее широкими возможностями Windows.

[CListView](../mfc/reference/clistview-class.md)<br/>
Представление, содержащее элемент управления списка Windows.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Представление, содержащее дерево Windows.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

