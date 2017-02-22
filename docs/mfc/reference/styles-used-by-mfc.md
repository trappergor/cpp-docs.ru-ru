---
title: "Стили, используемые MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.styles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "кнопки, Панели инструментов MFC"
  - "поля со списком, стили"
  - "изменение стилей [MFC]"
  - "расширенные стили окна"
  - "окна фрейма, стили"
  - "списки, стили"
  - "стили окна сообщений"
  - "стили полосы прокрутки [MFC]"
  - "статические стили"
  - "стили"
  - "стили, MFC - библиотека"
  - "стили окна, в MFC"
ms.assetid: d3b9af37-31b5-4c97-a8ad-189fd724b04c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Стили, используемые MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используйте следующие стили при создании соответствующий объект MFC.  В большинстве случаев эти стили заданы в параметр `dwStyle` функции **Создать**  класса.  
  
### Стили MFC  
  
|Стиль|Описание|  
|-----------|--------------|  
|[Стили кнопки](../../mfc/reference/button-styles.md)|Применяет к [Класс CButton](../../mfc/reference/cbutton-class.md) объекты, например переключатели, флажки и кнопки.  Определение стилей сочетания из в параметре `dwStyle`[CButton::Create](../Topic/CButton::Create.md).|  
|[Стили поля со списком](../../mfc/reference/combo-box-styles.md)|Применяет к [Класс CComboBox](../../mfc/reference/ccombobox-class.md) объекты.  Определение стилей сочетания из в параметре `dwStyle`[CComboBox::Create](../Topic/CComboBox::Create.md).|  
|[Правка стили](../../mfc/reference/edit-styles.md)|Применяет к [Класс CEdit](../Topic/CEdit%20Class.md) объекты.  Определение стилей сочетания из в параметре `dwStyle`[CEdit::Create](../Topic/CEdit::Create.md).|  
|[Стили фреймового окна](../../mfc/reference/frame-window-styles-mfc.md)|Применяет к [Класс CFrameWnd](../../mfc/reference/cframewnd-class.md) объекты.  Определение стилей сочетания из в параметре `dwStyle`[CFrameWnd::Create](../Topic/CFrameWnd::Create.md).|  
|[Стили списка](../../mfc/reference/list-box-styles.md)|Применяет к [Класс CListBox](../Topic/CListBox%20Class.md) объекты.  Определение стилей сочетания из в параметре `dwStyle`[CListBox::Create](../Topic/CListBox::Create.md).|  
|[Стили окна сообщений](../../mfc/reference/message-box-styles.md)|Применяет к [AfxMessageBox](../Topic/AfxMessageBox.md) элементов.  Определение стилей сочетания из в параметре `nType``AfxMessageBox`.|  
|[Стили полосы прокрутки](../../mfc/reference/scroll-bar-styles.md)|Применяет к [Класс CScrollBar](../../mfc/reference/cscrollbar-class.md) объекты.  Определение стилей сочетания из в параметре `dwStyle`[CScrollBar::Create](../Topic/CScrollBar::Create.md).|  
|[Статические стили](../../mfc/reference/static-styles.md)|Применяет к [Класс CStatic](../Topic/CStatic%20Class.md) объекты.  Определение стилей сочетания из в параметре `dwStyle`[CStatic::Create](../Topic/CStatic::Create.md).|  
|[Стили окна](../Topic/Window%20Styles.md)|Применяет к [Класс CWnd](../Topic/CWnd%20Class.md) объекты.  Определение стилей сочетания из в параметре `dwStyle`[CWnd::Create](../Topic/CWnd::Create.md) или [CWnd::CreateEx](../Topic/CWnd::CreateEx.md).|  
|[Расширенные стили окна](../Topic/Extended%20Window%20Styles.md)|Применяет к [Класс CWnd](../Topic/CWnd%20Class.md) объекты.  Определение стилей сочетания из в параметре `dwExStyle`[CWnd::CreateEx](../Topic/CWnd::CreateEx.md).|  
  
## См. также  
 [Общие сведения о классах](../../mfc/class-library-overview.md)