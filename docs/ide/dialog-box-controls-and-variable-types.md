---
title: "Элементы управления диалоговых окон и типы переменных | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog box controls, member variables
- dialog box controls, variable types
- variables, dialog box control member variables
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 744b9da2db456a72ed386806d8a4aa34c5942f69
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-box-controls-and-variable-types"></a>Элементы управления "Диалоговые окна" и типы переменных
Можно использовать [мастер добавления переменной члена](../ide/add-member-variable-wizard.md) для добавления переменной-члена для элемента управления диалогового окна поле, созданных с помощью MFC. Тип элемента управления, для которого добавить переменную-член определяет параметры, отображаемые в диалоговом окне.  
  
 В следующей таблице описаны все типы элементов управления поле диалогового окна, поддерживаемые в MFC и [редактор диалоговых окон](../windows/dialog-editor.md), доступные типы и их значения.  
  
|Элемент управления|Тип элемента управления|Тип переменной элемента управления|Тип значения переменной|Значения Min и max (только для типа значения)|  
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|  
|Элемент управления "Анимация"|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|None; только элемент управления|Н/Д|  
|Кнопка|КНОПКА|[CButton](../mfc/reference/cbutton-class.md)|None; только элемент управления|Н/Д|  
|Флажок|ФЛАЖОК|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|Мин. / Макс.|  
|Поле со списком|ПОЛЕ СО СПИСКОМ|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|Макс. число символов|  
|Управления выбора даты и времени|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|Мин. / Макс.|  
|Поле ввода|ПРАВКА|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, UINT, long, параметр DWORD с плавающей запятой, BYTE, short, BOOL, `COleDateTime`, или **COleCurrency**|Минимальное значение и максимальное значение; Макс.|  
|Элемент управления "горячая" клавиша|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|None; только элемент управления|Н/Д|  
|Список|LISTBOX|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|Макс. число символов|  
|Элемент управления "Список"|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|None; только элемент управления|Н/Д|  
|Элемент управления "Календарь месяца"|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|Мин. / Макс.|  
|Progress control|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|None; только элемент управления|Н/Д|  
|Элемент управления Rich изменить 2|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|Макс. число символов|  
|Элемент управления Rich Edit|RICHEDIT|`CRichEditCtrl`|`CString`|Макс. число символов|  
|Полоса прокрутки (вертикальной или горизонтальной|ПОЛОСЫ ПРОКРУТКИ|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|Мин. / Макс.|  
|Ползунок - элемент управления|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|Мин. / Макс.|  
|Spin control|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|None; только элемент управления|Н/Д|  
|Элемент управления табуляции|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|None; только элемент управления|Н/Д|  
|Элемент управления "Дерево"|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|None; только элемент управления|Н/Д|  
  
## <a name="see-also"></a>См. также  
 [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md)