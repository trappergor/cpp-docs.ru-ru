---
title: "Сообщения WM_ S | Microsoft Docs"
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
  - "ON_WM_SYSDEADCHAR"
  - "ON_WM_SYSKEYDOWN"
  - "ON_WM_STYLECHANGING"
  - "ON_WM_STYLECHANGED"
  - "ON_WM_SPOOLERSTATUS"
  - "ON_WM_SYSCHAR"
  - "ON_WM_SETFOCUS"
  - "ON_WM_SIZE"
  - "ON_WM_SIZING"
  - "ON_WM_SETCURSOR"
  - "ON_WM_SYSCOMMAND"
  - "ON_WM_SETTINGCHANGE"
  - "ON_WM_SHOWWINDOW"
  - "ON_WM_SYSKEYUP"
  - "ON_WM_SIZECLIPBOARD"
  - "ON_WM_SYSCOLORCHANGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_SETCURSOR"
  - "ON_WM_SETFOCUS"
  - "ON_WM_SETTINGCHANGE"
  - "ON_WM_SHOWWINDOW"
  - "ON_WM_SIZE"
  - "ON_WM_SIZECLIPBOARD"
  - "ON_WM_SIZING"
  - "ON_WM_SPOOLERSTATUS"
  - "ON_WM_STYLECHANGED"
  - "ON_WM_STYLECHANGING"
  - "ON_WM_SYSCHAR"
  - "ON_WM_SYSCOLORCHANGE"
  - "ON_WM_SYSCOMMAND"
  - "ON_WM_SYSDEADCHAR"
  - "ON_WM_SYSKEYDOWN"
  - "ON_WM_SYSKEYUP"
  - "WM_ - сообщения"
ms.assetid: 4b9aec79-a98f-4aa0-a3d9-110941b6dcbc
caps.latest.revision: 14
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Сообщения WM_ S
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записи следующего сопоставления соответствуют прототипам функции.  
  
|Запись сопоставления|Прототип функции|  
|--------------------------|----------------------|  
|ON\_WM\_SETCURSOR \(\)|afx\_msg BOOL [OnSetCursor](../Topic/CWnd::OnSetCursor.md)\(CWnd\*, UINT, UINT\);|  
|ON\_WM\_SETFOCUS \(\)|afx\_msg пустое [OnSetFocus](../Topic/CWnd::OnSetFocus.md)\(CWnd\*\);|  
|ON\_WM\_SETTINGCHANGE \(\)|afx\_msg пустое [OnSettingChange](../Topic/CWnd::OnSettingChange.md)\(uFlags UINT, lpszSection LPCTSTR\);|  
|ON\_WM\_SHOWWINDOW \(\)|afx\_msg пустое [OnShowWindow](../Topic/CWnd::OnShowWindow.md)\(BOOL, UINT\);|  
|ON\_WM\_SIZE \(\)|afx\_msg пустое [OnSize](../Topic/CWnd::OnSize.md)\(UINT, int, int\);|  
|ON\_WM\_SIZECLIPBOARD \(\)|afx\_msg пустое [OnSizeClipboard](../Topic/CWnd::OnSizeClipboard.md)\(CWnd\*, HANDLE\);|  
|ON\_WM\_SIZING \(\)|afx\_msg пустое [OnSizing](../Topic/CWnd::OnSizing.md)\(UINT, LPRECT\);|  
|ON\_WM\_SPOOLERSTATUS \(\)|afx\_msg пустое [OnSpoolerStatus](../Topic/CWnd::OnSpoolerStatus.md)\(UINT, UINT\);|  
|ON\_WM\_STYLECHANGED \(\)|afx\_msg пустое [OnStyleChanged](../Topic/CWnd::OnStyleChanged.md)\(int, LPSTYLESTRUCT\);|  
|ON\_WM\_STYLECHANGING \(\)|afx\_msg пустое [OnStyleChanging](../Topic/CWnd::OnStyleChanging.md)\(int, LPSTYLESTRUCT\);|  
|ON\_WM\_SYSCHAR \(\)|afx\_msg пустое [OnSysChar](../Topic/CWnd::OnSysChar.md)\(UINT, UINT, UINT\);|  
|ON\_WM\_SYSCOLORCHANGE \(\)|afx\_msg пустое \( [OnSysColorChange](../Topic/CWnd::OnSysColorChange.md)\);|  
|ON\_WM\_SYSCOMMAND \(\)|afx\_msg пустое [OnSysCommand](../Topic/CWnd::OnSysCommand.md)\(UINT, ДЛИННИЕ\);|  
|ON\_WM\_SYSDEADCHAR \(\)|afx\_msg пустое [OnSysDeadChar](../Topic/CWnd::OnSysDeadChar.md)\(UINT, UINT, UINT\);|  
|ON\_WM\_SYSKEYDOWN \(\)|afx\_msg пустое [OnSysKeyDown](../Topic/CWnd::OnSysKeyDown.md)\(UINT, UINT, UINT\);|  
|ON\_WM\_SYSKEYUP \(\)|afx\_msg пустое [OnSysKeyUp](../Topic/CWnd::OnSysKeyUp.md)\(UINT, UINT, UINT\);|  
  
## См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)   
 [Обработчики для сообщений WM\_](../../mfc/reference/handlers-for-wm-messages.md)