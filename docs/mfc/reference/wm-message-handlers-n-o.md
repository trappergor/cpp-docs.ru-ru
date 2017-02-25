---
title: "Обработчики сообщений WM_ N — O | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_WM_NCHITTEST"
  - "ON_WM_NCLBUTTONDOWN"
  - "ON_WM_NCCALCSIZE"
  - "ON_WM_NCLBUTTONUP"
  - "ON_WM_NCPAINT"
  - "ON_WM_NCMBUTTONUP"
  - "ON_WM_NCCREATE"
  - "ON_WM_NCACTIVATE"
  - "ON_WM_NCMOUSEMOVE"
  - "ON_WM_NCRBUTTONDBLCLK"
  - "ON_WM_NCLBUTTONDBLCLK"
  - "ON_WM_NCDESTROY"
  - "ON_WM_NCMBUTTONDBLCLK"
  - "ON_WM_NCRBUTTONDOWN"
  - "ON_WM_NCRBUTTONUP"
  - "ON_WM_NCMBUTTONDOWN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_NCACTIVATE"
  - "ON_WM_NCCALCSIZE"
  - "ON_WM_NCCREATE"
  - "ON_WM_NCDESTROY"
  - "ON_WM_NCHITTEST"
  - "ON_WM_NCLBUTTONDBLCLK"
  - "ON_WM_NCLBUTTONDOWN"
  - "ON_WM_NCLBUTTONUP"
  - "ON_WM_NCMBUTTONDBLCLK"
  - "ON_WM_NCMBUTTONDOWN"
  - "ON_WM_NCMBUTTONUP"
  - "ON_WM_NCMOUSEMOVE"
  - "ON_WM_NCPAINT"
  - "ON_WM_NCRBUTTONDBLCLK"
  - "ON_WM_NCRBUTTONDOWN"
  - "ON_WM_NCRBUTTONUP"
  - "WM_ - сообщения"
ms.assetid: 4efd1cda-b642-4e8b-89e8-73255fa70d77
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Обработчики сообщений WM_ N — O
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записи следующего сопоставления слева соответствуют прототипам функции справа:  
  
|Запись сопоставления|Прототип функции|  
|--------------------------|----------------------|  
|ON\_WM\_NCACTIVATE\(\)|afx\_msg BOOL [OnNcActivate](../Topic/CWnd::OnNcActivate.md)\(BOOL\);|  
|ON\_WM\_NCCALCSIZE\(\)|afx\_msg пустое [OnNcCalcSize](../Topic/CWnd::OnNcCalcSize.md)\(BOOL, NCCALCSIZE\_PARAMS FAR\*\);|  
|ON\_WM\_NCCREATE\(\)|afx\_msg BOOL [OnNcCreate](../Topic/CWnd::OnNcCreate.md)\(LPCREATESTRUCT\);|  
|ON\_WM\_NCDESTROY\(\)|afx\_msg пустое \( [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md)\);|  
|ON\_WM\_NCHITTEST\(\)|afx\_msg LRESULT [OnNcHitTest](../Topic/CWnd::OnNcHitTest.md)\(CPoint\);|  
|ON\_WM\_NCLBUTTONDBLCLK\(\)|afx\_msg пустое [OnNcLButtonDblClk](../Topic/CWnd::OnNcLButtonDblClk.md)\(UINT, CPoint\);|  
|ON\_WM\_NCLBUTTONDOWN\(\)|afx\_msg пустое [OnNcLButtonDown](../Topic/CWnd::OnNcLButtonDown.md)\(UINT, CPoint\);|  
|ON\_WM\_NCLBUTTONUP\(\)|afx\_msg пустое [OnNcLButtonUp](../Topic/CWnd::OnNcLButtonUp.md)\(UINT, CPoint\);|  
|ON\_WM\_NCMBUTTONDBLCLK\(\)|afx\_msg пустое [OnNcMButtonDblClk](../Topic/CWnd::OnNcMButtonDblClk.md)\(UINT, CPoint\);|  
|ON\_WM\_NCMBUTTONDOWN\(\)|afx\_msg пустое [OnNcMButtonDown](../Topic/CWnd::OnNcMButtonDown.md)\(UINT, CPoint\);|  
|ON\_WM\_NCMBUTTONUP\(\)|afx\_msg пустое [OnNcMButtonUp](../Topic/CWnd::OnNcMButtonUp.md)\(UINT, CPoint\);|  
|ON\_WM\_NCMOUSEHOVER\(\)|afx\_msg пустое [OnNcMouseHover](../Topic/CWnd::OnNcMouseHover.md)\(UINT, CPoint\);|  
|ON\_WM\_NCMOUSELEAVE\(\)|afx\_msg пустое \( [OnNcMouseLeave](../Topic/CWnd::OnNcMouseLeave.md)\);|  
|ON\_WM\_NCMOUSEMOVE\(\)|afx\_msg пустое [OnNcMouseMove](../Topic/CWnd::OnNcMouseMove.md)\(UINT, CPoint\);|  
|ON\_WM\_NCPAINT\(\)|afx\_msg пустое \( [OnNcPaint](../Topic/CWnd::OnNcPaint.md)\);|  
|ON\_WM\_NCRBUTTONDBLCLK\(\)|afx\_msg пустое [OnNcRButtonDblClk](../Topic/CWnd::OnNcRButtonDblClk.md)\(UINT, CPoint\);|  
|ON\_WM\_NCRBUTTONDOWN\(\)|afx\_msg пустое [OnNcRButtonDown](../Topic/CWnd::OnNcRButtonDown.md)\(UINT, CPoint\);|  
|ON\_WM\_NCRBUTTONUP\(\)|afx\_msg пустое [OnNcRButtonUp](../Topic/CWnd::OnNcRButtonUp.md)\(UINT, CPoint\);|  
|ON\_WM\_NCXBUTTONDBLCLK\(\)|[OnNcXButtonDblClk](../Topic/CWnd::OnNcXButtonDblClk.md)\(короткое пустое, UINT, CPoint\);|  
|ON\_WM\_NCXBUTTONDOWN\(\)|[OnNcXButtonDown](../Topic/CWnd::OnNcXButtonDown.md)\(короткое afx\_msg пустое, UINT, CPoint\);|  
|ON\_WM\_NCXBUTTONUP\(\)|[OnNcXButtonUp](../Topic/CWnd::OnNcXButtonUp.md)\(короткое afx\_msg пустое, UINT, CPoint\);|  
|ON\_WM\_NEXTMENU\(\)|afx\_msg пустое [OnNextMenu](../Topic/CWnd::OnNextMenu.md)\(UINT, LPMDINEXTMENU\);|  
|ON\_WM\_NOTIFYFORMAT\(\)|afx\_msg UINT [OnNotifyFormat](../Topic/CWnd::OnNotifyFormat.md)\(CWnd\*, UINT\);|  
  
## См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)   
 [Обработчики для сообщений WM\_](../../mfc/reference/handlers-for-wm-messages.md)