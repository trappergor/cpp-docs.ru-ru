---
title: Элементы управления "Диалоговое окно" и типы переменных | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog box controls, member variables
- dialog box controls, variable types
- variables, dialog box control member variables
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2fbae37072f50898181334a9059a7dc9c6a83a9
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "33335069"
---
# <a name="dialog-box-controls-and-variable-types"></a>Элементы управления "Диалоговые окна" и типы переменных
Вы можете использовать [мастер добавления переменной-члена](../ide/add-member-variable-wizard.md) для добавления переменной-члена в элемент управления диалогового окна, созданный с помощью MFC. Тип элемента управления, для которого вы добавляете переменную-член, определяет параметры, отображаемые в диалоговом окне.  
  
 В следующей таблице описаны все типы элементов управления диалогового окна, поддерживаемые в MFC и [редакторе диалоговых окон](../windows/dialog-editor.md), а также доступные типы и значения для них.  
  
|Элемент управления|Тип элемента управления|Тип переменной элемента управления|Тип переменной значения|Минимальное и максимальное значения (только тип значения)|  
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|  
|Элемент управления "Анимация"|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|Нет, только элемент управления|Н/Д|  
|Кнопка|BUTTON|[CButton](../mfc/reference/cbutton-class.md)|Нет, только элемент управления|Н/Д|  
|Флажок|CHECK|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|Минимальное и максимальное значения|  
|Поле со списком|COMBOBOX|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|Максимальное число символов|  
|Элемент управления "Выбор даты и времени"|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|Минимальное и максимальное значения|  
|Поле ввода|ПРАВКА|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, UINT, long, DWORD, float, double, BYTE, short, BOOL, `COleDateTime` или **COleCurrency**|Минимальное и максимальное значения; некоторые поддерживают максимальное количество символов|  
|Элемент управления "Сочетание клавиш"|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|Нет, только элемент управления|Н/Д|  
|Список|LISTBOX|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|Максимальное число символов|  
|Элемент управления "Список"|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|Нет, только элемент управления|Н/Д|  
|Элемент управления "Календарь месяца"|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|Минимальное и максимальное значения|  
|Progress control|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|Нет, только элемент управления|Н/Д|  
|Элемент управления Rich Edit 2|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|Максимальное число символов|  
|Элемент управления Rich Edit|RICHEDIT|`CRichEditCtrl`|`CString`|Максимальное число символов|  
|Полоса прокрутки (вертикальная или горизонтальная)|SCROLLBAR|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|Минимальное и максимальное значения|  
|Ползунок - элемент управления|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|Минимальное и максимальное значения|  
|Spin control|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|Нет, только элемент управления|Н/Д|  
|Элемент управления табуляции|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|Нет, только элемент управления|Н/Д|  
|Элемент управления "Дерево"|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|Нет, только элемент управления|Н/Д|  
  
## <a name="see-also"></a>См. также  
 [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md)