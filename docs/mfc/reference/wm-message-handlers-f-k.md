---
title: "Обработчики сообщений WM_ F — K | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_WM_FONTCHANGE"
  - "ON_WM_ICONERASEBKGND"
  - "ON_WM_KEYDOWN"
  - "ON_WM_GETMINMAXINFO"
  - "ON_WM_KEYUP"
  - "ON_WM_HSCROLL"
  - "ON_WM_KILLFOCUS"
  - "ON_WM_HSCROLLCLIPBOARD"
  - "ON_WM_GETDLGCODE"
  - "ON_WM_HELPINFO"
  - "ON_WM_INITMENUPOPUP"
  - "ON_WM_INITMENU"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_FONTCHANGE"
  - "ON_WM_GETDLGCODE"
  - "ON_WM_GETMINMAXINFO"
  - "ON_WM_HELPINFO"
  - "ON_WM_HSCROLL"
  - "ON_WM_HSCROLLCLIPBOARD"
  - "ON_WM_ICONERASEBKGND"
  - "ON_WM_INITMENU"
  - "ON_WM_INITMENUPOPUP"
  - "ON_WM_KEYDOWN"
  - "ON_WM_KEYUP"
  - "ON_WM_KILLFOCUS"
  - "WM_ - сообщения"
ms.assetid: 0e7de191-1499-499f-859c-62742797808e
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Обработчики сообщений WM_ F — K
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записи следующего сопоставления слева соответствуют прототипам функции справа:  
  
|Запись сопоставления|Прототип функции|  
|--------------------------|----------------------|  
|ON\_WM\_FONTCHANGE\(\)|afx\_msg пустое \( [OnFontChange](../Topic/CWnd::OnFontChange.md)\);|  
|ON\_WM\_GETDLGCODE\(\)|afx\_msg UINT [OnGetDlgCode](../Topic/CWnd::OnGetDlgCode.md)\(\);|  
|ON\_WM\_GETMINMAXINFO\(\)|afx\_msg пустое [OnGetMinMaxInfo](../Topic/CWnd::OnGetMinMaxInfo.md)\(LPPOINT\);|  
|ON\_WM\_HELPINFO\(\)|afx\_msg BOOL [OnHelpInfo](../Topic/CWnd::OnHelpInfo.md)\(HELPINFO\*\);|  
|ON\_WM\_HOTKEY\(\)|afx\_msg пустое [OnHotKey](../Topic/CWnd::OnHotKey.md)\(UINT, UINT, UINT\);|  
|ON\_WM\_HSCROLL\(\)|afx\_msg пустое [OnHScroll](../Topic/CWnd::OnHScroll.md)\(UINT, UINT, CWnd\*\);|  
|ON\_WM\_HSCROLLCLIPBOARD\(\)|afx\_msg пустое [OnHScrollClipboard](../Topic/CWnd::OnHScrollClipboard.md)\(CWnd\*, UINT, UINT\);|  
|ON\_WM\_ICONERASEBKGND\(\)|afx\_msg пустое [OnIconEraseBkgnd](../Topic/CWnd::OnIconEraseBkgnd.md)\(CDC\*\);|  
|ON\_WM\_INITMENU\(\)|afx\_msg пустое [OnInitMenu](../Topic/CWnd::OnInitMenu.md)\(CMenu\*\);|  
|ON\_WM\_INITMENUPOPUP\(\)|afx\_msg пустое [OnInitMenuPopup](../Topic/CWnd::OnInitMenuPopup.md)\(CMenu\*, UINT, BOOL\);|  
|ON\_WM\_INPUT\(\)|afx\_msg пустое [OnRawInput](../Topic/CWnd::OnRawInput.md)\(UINT, HRAWINPUT\);|  
|ON\_WM\_INPUT\_DEVICE\_CHANGE\(\)|afx\_msg пустое [OnInputDeviceChange](../Topic/CWnd::OnInputDeviceChange.md)\(unsigned short\);|  
|ON\_WM\_INPUTLANGCHANGE\(\)|afx\_msg пустое [OnInputLangChange](../Topic/CWnd::OnInputLangChange.md)\(БАЙТ, UINT\);|  
|ON\_WM\_INPUTLANGCHANGEREQUEST\(\)|afx\_msg пустое [OnInputLangChangeRequest](../Topic/CWnd::OnInputLangChangeRequest.md)\(UINT, HKL\);|  
|ON\_WM\_KEYDOWN\(\)|afx\_msg пустое [Onkeydown](../Topic/CWnd::OnKeyDown.md)\(UINT, UINT, UINT\);|  
|ON\_WM\_KEYUP\(\)|afx\_msg пустое [Onkeyup](../Topic/CWnd::OnKeyUp.md)\(UINT, UINT, UINT\);|  
|ON\_WM\_KILLFOCUS\(\)|afx\_msg пустое [OnKillFocus](../Topic/CWnd::OnKillFocus.md)\(CWnd\*\);|  
  
## См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)   
 [Обработчики для сообщений WM\_](../../mfc/reference/handlers-for-wm-messages.md)