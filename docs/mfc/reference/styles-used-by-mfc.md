---
title: "Стили, используемые MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.styles
dev_langs:
- C++
helpviewer_keywords:
- edit styles [MFC]
- window styles, in MFC
- styles
- frame windows, styles
- message-box styles
- styles, MFC
- buttons, MFC toolbars
- list boxes, styles
- static styles
- scroll-bar styles [MFC]
- combo boxes, styles
- extended window styles
ms.assetid: d3b9af37-31b5-4c97-a8ad-189fd724b04c
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 344d2ce3de15403e17f29dc9504253cbb0ade607
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="styles-used-by-mfc"></a>Стили, используемые MFC
Используйте следующие стили при создании соответствующего объекта MFC. В большинстве случаев эти стили заданы в `dwStyle` параметр класса **создать** функции.  
  
### <a name="mfc-styles"></a>Стили MFC  
  
|Стиль|Описание|  
|-----------|-----------------|  
|[Стили кнопок](../../mfc/reference/button-styles.md)|Применяется к [класс CButton](../../mfc/reference/cbutton-class.md) проверьте объекты, такие как переключатели, поля и кнопок. Определение сочетания стили в `dwStyle` параметр [CButton::Create](../../mfc/reference/cbutton-class.md#create).|  
|[Стили полей со списками](../../mfc/reference/combo-box-styles.md)|Применяется к [CComboBox-класс](../../mfc/reference/ccombobox-class.md) объектов. Определение сочетания стили в `dwStyle` параметр [CComboBox::Create](../../mfc/reference/ccombobox-class.md#create).|  
|[Изменение стилей](../../mfc/reference/edit-styles.md)|Применяется к [CEdit Class](../../mfc/reference/cedit-class.md) объектов. Определение сочетания стили в `dwStyle` параметр [CEdit::Create](../../mfc/reference/cedit-class.md#create).|  
|[Стили окна фрейма](../../mfc/reference/frame-window-styles-mfc.md)|Применяется к [класса CFrameWnd](../../mfc/reference/cframewnd-class.md) объектов. Определение сочетания стили в `dwStyle` параметр [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create).|  
|[Стили списков](../../mfc/reference/list-box-styles.md)|Применяется к [CListBox-класс](../../mfc/reference/clistbox-class.md) объектов. Определение сочетания стили в `dwStyle` параметр [CListBox::Create](../../mfc/reference/clistbox-class.md#create).|  
|[Стили окна сообщений](../../mfc/reference/message-box-styles.md)|Применяется к [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) элементов. Определение сочетания стили в `nType` параметр `AfxMessageBox`.|  
|[Стили полосы прокрутки](../../mfc/reference/scroll-bar-styles.md)|Применяется к [CScrollBar класс](../../mfc/reference/cscrollbar-class.md) объектов. Определение сочетания стили в `dwStyle` параметр [CScrollBar::Create](../../mfc/reference/cscrollbar-class.md#create).|  
|[Статические стили](../../mfc/reference/static-styles.md)|Применяется к [CStatic класс](../../mfc/reference/cstatic-class.md) объектов. Определение сочетания стили в `dwStyle` параметр [CStatic::Create](../../mfc/reference/cstatic-class.md#create).|  
|[Стили окна](../../mfc/reference/window-styles.md)|Применяется к [класс CWnd](../../mfc/reference/cwnd-class.md) объектов. Определение сочетания стили в `dwStyle` параметр [CWnd::Create](../../mfc/reference/cwnd-class.md#create) или [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex).|  
|[Расширенные стили окна](../../mfc/reference/extended-window-styles.md)|Применяется к [класс CWnd](../../mfc/reference/cwnd-class.md) объектов. Определение сочетания стили в `dwExStyle` параметр [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex).|  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../mfc/class-library-overview.md)


