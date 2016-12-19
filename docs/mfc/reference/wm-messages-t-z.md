---
title: "Сообщения WM_ T — Z | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_WM_TCARD"
  - "ON_WM_WININICHANGE"
  - "ON_WM_VSCROLLCLIPBOARD"
  - "ON_WM_VSCROLL"
  - "ON_WM_WINDOWPOSCHANGED"
  - "ON_WM_TIMECHANGE"
  - "ON_WM_TIMER"
  - "ON_WM_VKEYTOITEM"
  - "ON_WM_WINDOWPOSCHANGING"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_TCARD"
  - "ON_WM_TIMECHANGE"
  - "ON_WM_TIMER"
  - "ON_WM_VKEYTOITEM"
  - "ON_WM_VSCROLL"
  - "ON_WM_VSCROLLCLIPBOARD"
  - "ON_WM_WINDOWPOSCHANGED"
  - "ON_WM_WINDOWPOSCHANGING"
  - "ON_WM_WININICHANGE"
  - "WM_ - сообщения"
ms.assetid: c528bb2e-ddb5-4da6-b652-432a387408b8
caps.latest.revision: 16
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Сообщения WM_ T — Z
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записи следующего сопоставления соответствуют прототипам функции:  
  
|Запись сопоставления|Прототип функции|  
|--------------------------|----------------------|  
|ON\_WM\_TCARD\(\)|afx\_msg пустое [OnTCard](../Topic/CWnd::OnTCard.md)\(UINT, DWORD\);|  
|ON\_WM\_TIMECHANGE\(\)|afx\_msg пустое \( [OnTimeChange](../Topic/CWnd::OnTimeChange.md)\);|  
|ON\_WM\_TIMER\(\)|afx\_msg пустое [OnTimer](../Topic/CWnd::OnTimer.md)\(UINT\_PTR\);|  
|ON\_WM\_UNICHAR\(\)|afx\_msg пустое [OnUniChar](../Topic/CWnd::OnUniChar.md)\(UINT, UINT, UINT\);|  
|ON\_WM\_UNINITMENUPOPUP\(\)|afx\_msg пустое [OnUnInitMenuPopup](../Topic/CWnd::OnUnInitMenuPopup.md)\(CMenu\*, UINT\);|  
|ON\_WM\_USERCHANGED\(\)|afx\_msg пустое \( [OnUserChanged](../Topic/CWnd::OnUserChanged.md)\);|  
|ON\_WM\_VKEYTOITEM\(\)|afx\_msg int [OnVKeyToItem](../Topic/CWnd::OnVKeyToItem.md)\(UINT, CWnd\*, UINT\);|  
|ON\_WM\_VSCROLL\(\)|afx\_msg пустое [OnVScroll](../Topic/CWnd::OnVScroll.md)\(UINT, UINT, CWnd\*\);|  
|ON\_WM\_VSCROLLCLIPBOARD\(\)|afx\_msg пустое [OnVScrollClipboard](../Topic/CWnd::OnVScrollClipboard.md)\(CWnd\*, UINT, UINT\);|  
|ON\_WM\_WINDOWPOSCHANGED\(\)|afx\_msg пустое [OnWindowPosChanged](../Topic/CWnd::OnWindowPosChanged.md)\(WINDOWPOS\*\);|  
|ON\_WM\_WINDOWPOSCHANGING\(\)|afx\_msg пустое [OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md)\(WINDOWPOS\*\);|  
|ON\_WM\_WININICHANGE\(\)|afx\_msg пустое LPSTR \( [OnWinIniChange](../Topic/CWnd::OnWinIniChange.md)\);|  
|ON\_WM\_WTSSESSION\_CHANGE\(\)|afx\_msg пустое [OnSessionChange](../Topic/CWnd::OnSessionChange.md)\(UINT, UINT\);|  
|ON\_WM\_XBUTTONDBLCLK\(\)|afx\_msg пустое [OnXButtonDblClk](../Topic/CWnd::OnXButtonDblClk.md)\(UINT, UINT, CPoint\);|  
|ON\_WM\_XBUTTONDOWN\(\)|afx\_msg пустое [OnXButtonDown](../Topic/CWnd::OnXButtonDown.md)\(UINT, UINT, CPoint\);|  
|ON\_WM\_XBUTTONUP\(\)|afx\_msg пустое [OnXButtonUp](../Topic/CWnd::OnXButtonUp.md)\(UINT, UINT, CPoint\);|  
  
## См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)   
 [Обработчики для сообщений WM\_](../../mfc/reference/handlers-for-wm-messages.md)