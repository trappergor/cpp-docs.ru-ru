---
title: "Обработчики сообщений WM_ L — M | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_WM_MENUSELECT"
  - "ON_WM_MBUTTONDBLCLK"
  - "ON_WM_MOUSEACTIVATE"
  - "ON_WM_MOUSEMOVE"
  - "ON_WM_MOVING"
  - "ON_WM_LBUTTONUP"
  - "ON_WM_LBUTTONDBLCLK"
  - "ON_WM_MEASUREITEM"
  - "ON_WM_MDIACTIVATE"
  - "ON_WM_MOVE"
  - "ON_WM_LBUTTONDOWN"
  - "ON_WM_MBUTTONDOWN"
  - "ON_WM_MENUCHAR"
  - "ON_WM_MBUTTONUP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_LBUTTONDBLCLK"
  - "ON_WM_LBUTTONDOWN"
  - "ON_WM_LBUTTONUP"
  - "ON_WM_MBUTTONDBLCLK"
  - "ON_WM_MBUTTONDOWN"
  - "ON_WM_MBUTTONUP"
  - "ON_WM_MDIACTIVATE"
  - "ON_WM_MEASUREITEM"
  - "ON_WM_MENUCHAR"
  - "ON_WM_MENUSELECT"
  - "ON_WM_MOUSEACTIVATE"
  - "ON_WM_MOUSEMOVE"
  - "ON_WM_MOVE"
  - "ON_WM_MOVING"
  - "WM_ - сообщения"
ms.assetid: 96ecaaf1-6d13-4e12-a454-535635967489
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Обработчики сообщений WM_ L — M
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записи следующего сопоставления слева соответствуют прототипам функции справа:  
  
|Запись сопоставления|Прототип функции|  
|--------------------------|----------------------|  
|ON\_WM\_LBUTTONDBLCLK\(\)|afx\_msg пустое [OnLButtonDblClk](../Topic/CWnd::OnLButtonDblClk.md)\(UINT, CPoint\);|  
|ON\_WM\_LBUTTONDOWN\(\)|afx\_msg пустое [OnLButtonDown](../Topic/CWnd::OnLButtonDown.md)\(UINT, CPoint\);|  
|ON\_WM\_LBUTTONUP\(\)|afx\_msg пустое [OnLButtonUp](../Topic/CWnd::OnLButtonUp.md)\(UINT, CPoint\);|  
|ON\_WM\_MBUTTONDBLCLK\(\)|afx\_msg пустое [OnMButtonDblClk](../Topic/CWnd::OnMButtonDblClk.md)\(UINT, CPoint\);|  
|ON\_WM\_MBUTTONDOWN\(\)|afx\_msg пустое [OnMButtonDown](../Topic/CWnd::OnMButtonDown.md)\(UINT, CPoint\);|  
|ON\_WM\_MBUTTONUP\(\)|afx\_msg пустое [OnMButtonUp](../Topic/CWnd::OnMButtonUp.md)\(UINT, CPoint\);|  
|ON\_WM\_MDIACTIVATE\(\)|afx\_msg пустое [OnMDIActivate](../Topic/CWnd::OnMDIActivate.md)\(BOOL, CWnd\*, CWnd\*\);|  
|ON\_WM\_MEASUREITEM\(\)|afx\_msg пустое [OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)\(LPMEASUREITEMSTRUCT\);|  
|ON\_WM\_MENUCHAR\(\)|afx\_msg ДЛИННОЕ [OnMenuChar](../Topic/CWnd::OnMenuChar.md)\(UINT, UINT, CMenu\*\);|  
|ON\_WM\_MENUDRAG\(\)|afx\_msg UINT [OnMenuDrag](../Topic/CWnd::OnMenuDrag.md)\(UINT, CMenu\*\);|  
|ON\_WM\_MENUGETOBJECT\(\)|afx\_msg UINT [OnMenuGetObject](../Topic/CWnd::OnMenuGetObject.md)\(MENUGETOBJECTINFO\*\);|  
|ON\_WM\_MENURBUTTONUP\(\)|afx\_msg пустое [OnMenuRButtonUp](../Topic/CWnd::OnMenuRButtonUp.md)\(UINT, CMenu\*\);|  
|ON\_WM\_MENUSELECT\(\)|afx\_msg пустое [OnMenuSelect](../Topic/CWnd::OnMenuSelect.md)\(UINT, UINT, HMENU\);|  
|ON\_WM\_MOUSEACTIVATE\(\)|afx\_msg int [OnMouseActivate](../Topic/CWnd::OnMouseActivate.md)\(CWnd\*, UINT, UINT\);|  
|ON\_WM\_MOUSEHOVER\(\)|afx\_msg пустое [OnMouseHover](../Topic/CWnd::OnMouseHover.md)\(UINT, CPoint\);|  
|ON\_WM\_MOUSEHWHEEL\(\)|afx\_msg пустое [OnMouseHWheel](../Topic/CWnd::OnMouseHWheel.md)\(UINT, short, CPoint\);|  
|ON\_WM\_MOUSELEAVE\(\)|afx\_msg пустое \( [OnMouseLeave](../Topic/CWnd::OnMouseLeave.md)\);|  
|ON\_WM\_MOUSEMOVE\(\)|afx\_msg пустое [OnMouseMove](../Topic/CWnd::OnMouseMove.md)\(UINT, CPoint\);|  
|ON\_WM\_MOUSEWHEEL\(\)|afx\_msg BOOL [OnMouseWheel](../Topic/CWnd::OnMouseWheel.md)\(UINT, short, CPoint\);|  
|ON\_WM\_MOVE\(\)|afx\_msg пустое [OnMove](../Topic/CWnd::OnMove.md)\(int, int\);|  
|ON\_WM\_MOVING\(\)|afx\_msg пустое [OnMoving](../Topic/CWnd::OnMoving.md)\(UINT, LPRECT\);|  
  
## См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)   
 [Обработчики для сообщений WM\_](../../mfc/reference/handlers-for-wm-messages.md)