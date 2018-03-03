---
title: "Классы управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 376fb3836d92a1fae348929a7faa49b44dfd866e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="control-classes"></a>Классы элементов управления
Классы элементов управления инкапсулируют широкий спектр стандартных элементов управления Windows, от статических текстовых элементов управления для элементов управления древовидного типа. Кроме того MFC предоставляет некоторые новые элементы управления, включая кнопок с растровыми и управления панелями.  
  
 Элементы управления, классов, имена которых заканчиваются на «**Ctrl**» появилась только в Windows 95 и Windows NT версии 3.51.  
  
## <a name="static-display-controls"></a>Элементы управления статическим отображением  
 [CStatic](../mfc/reference/cstatic-class.md)  
 Окно отображения static. Статические элементы управления используются для меток, поле или разделения других элементов управления в диалоговое окно или окно. Они также могут отображаться графических изображений, а не текста или поле.  
  
## <a name="text-controls"></a>Текстовые элементы управления  
 [CEdit](../mfc/reference/cedit-class.md)  
 Появится окно элемента управления для редактирования текста. Изменить элементы управления используются для приема текстовые входные данные пользователя.  
  
 [CIPAddressCtrl](../mfc/reference/cipaddressctrl-class.md)  
 Поддерживает поле ввода для манипулирования адрес протокола Интернета (IP).  
  
 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)  
 Элемент управления, в котором пользователь может вводить и редактировать текст. В отличие от элементов управления, содержащийся в `CEdit`, элементе управления rich edit поддерживает символ и форматирование абзаца и объекты OLE.  
  
## <a name="controls-that-represent-numbers"></a>Элементы управления представляют собой числа  
 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)  
 Элемент управления, содержащий ползунком, который пользователь переходит на выберите значение или набор значений.  
  
 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)  
 Пара кнопок со стрелками, пользователь может щелкнуть для увеличения или уменьшения значения.  
  
 [CProgressCtrl](../mfc/reference/cprogressctrl-class.md)  
 Отображает прямоугольник, который постепенно заполняется слева направо для отображения хода выполнения операции.  
  
 [CScrollBar](../mfc/reference/cscrollbar-class.md)  
 Окно управления полосы прокрутки. Этот класс предоставляет функциональные возможности полосу прокрутки для использования в качестве элемента управления в диалоговое окно или окно, по которому пользователь может указать позицию в пределах диапазона.  
  
## <a name="buttons"></a>Кнопки  
 [CButton](../mfc/reference/cbutton-class.md)  
 Окно элемента управления button. Класс предоставляет программный интерфейс для кнопки, флажок или переключатель в диалоговом окне.  
  
 [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)  
 Кнопка с растровое изображение, а не текст заголовка.  
  
## <a name="lists"></a>Списки  
 [CListBox](../mfc/reference/clistbox-class.md)  
 Окно управления списков. Поле со списком отображает список элементов, которые пользователь может просмотреть и выбрать.  
  
 [CDragListBox](../mfc/reference/cdraglistbox-class.md)  
 Предоставляет функции списка Windows; позволяет пользователю перемещать элементы списка, такие как имена файлов и строковых литералов, в поле списка. Списки с возможностью полезны для в порядке, за исключением алфавитный список элементов, таких как включить в проект файлов или путей.  
  
 [CComboBox](../mfc/reference/ccombobox-class.md)  
 Окно управления списком. Поле со списком состоит из элемента управления, а также в поле со списком.  
  
 [CComboBoxEx](../mfc/reference/ccomboboxex-class.md)  
 Расширяет элемент управления "поле со списком", предоставляя поддержку списков изображений.  
  
 [CCheckListBox](../mfc/reference/cchecklistbox-class.md)  
 Отображает список элементов с флажками, которые пользователь может установите или снимите флажок, рядом с каждым элементом.  
  
 [CListCtrl](../mfc/reference/clistctrl-class.md)  
 Отображает коллекцию элементов, каждый элемент состоит из значка и метки, так же, как на правую панель проводника.  
  
 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)  
 Отображает иерархический список значков и метки организованы так же, как к левой панели проводника.  
  
## <a name="toolbars-and-status-bars"></a>Панели инструментов и строки состояния  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Предоставляет функциональные возможности стандартного элемента управления "панель инструментов" Windows. Большинство MFC программы используют [CToolBar](../mfc/reference/ctoolbar-class.md) вместо этого класса.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 Окно горизонтальной обычно разделены на области, в которых выводятся сведения о состоянии приложения. Большинство MFC программы используют [CStatusBar](../mfc/reference/cstatusbar-class.md) вместо этого класса.  
  
## <a name="miscellaneous-controls"></a>Различные элементы управления  
 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md)  
 Отображает простой видеоролика.  
  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 Небольшое всплывающее окно, которое отображается одна строка текста, описывающая назначение инструмента в приложении.  
  
 [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)  
 Поддерживает элемент управления расширенного редактирования или простой интерфейс календаря, пользователь может выбрать определенную дату или значение времени.  
  
 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)  
 Отображение заголовков или меток столбцов.  
  
 [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)  
 Поддерживает элемент управления интерфейса простой календарь, позволяющий пользователю выбрать дату.  
  
 [CTabCtrl](../mfc/reference/ctabctrl-class.md)  
 Элемент управления с вкладками, на которых пользователь может щелкнуть, аналогом разделителей в записной книжке.  
  
 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)  
 Позволяет пользователю создавать горячей сочетание клавиш, который пользователь может нажать для быстрого выполнения действий.  
  
 [Классах-оболочках](../mfc/reference/clinkctrl-class.md)  
 Отображает текст более и запускает соответствующие приложения, когда пользователь щелкает ссылку.  
  
 [CHtmlEditCtrl](../mfc/reference/chtmleditctrl-class.md)  
 Предоставляет функциональные возможности элемента управления ActiveX WebBrowser в окне MFC.  
  
## <a name="related-classes"></a>Связанные классы  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Предоставляет функции списка изображений Windows. Списки изображений используются элементы управления списка и дерева. Они также могут использоваться для хранения и архивирования набора точечных рисунков, аналогичного размера.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Базовый класс для всех представлений, связанные с элементами управления Windows. Ниже описаны представления, основан на элементах управления.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Представление, содержащее Windows standard поля ввода.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Представление, содержащее Windows широкие возможности управления edit.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Представление, содержащее элемент управления списка Windows.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Представление, содержащее дерево Windows.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

