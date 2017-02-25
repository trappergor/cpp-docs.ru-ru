---
title: "Обработчики сообщений WM_ A — C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_WM_CREATE"
  - "ON_WM_COMPACTING"
  - "ON_WM_CHARTOITEM"
  - "ON_WM_ASKCBFORMATNAME"
  - "ON_WM_CTLCOLOR"
  - "ON_WM_COMPAREITEM"
  - "ON_WM_CHILDACTIVATE"
  - "ON_WM_CONTEXTMENU"
  - "ON_WM_ACTIVATE"
  - "ON_WM_CANCELMODE"
  - "ON_WM_CLOSE"
  - "ON_WM_CAPTURECHANGED"
  - "ON_WM_ACTIVATEAPP"
  - "ON_WM_CHAR"
  - "ON_WM_CHANGECBCHAIN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_ACTIVATE"
  - "ON_WM_ACTIVATEAPP"
  - "ON_WM_ASKCBFORMATNAME"
  - "ON_WM_CANCELMODE"
  - "ON_WM_CAPTURECHANGED"
  - "ON_WM_CHANGECBCHAIN"
  - "ON_WM_CHAR"
  - "ON_WM_CHARTOITEM"
  - "ON_WM_CHILDACTIVATE"
  - "ON_WM_CLOSE"
  - "ON_WM_COMPACTING"
  - "ON_WM_COMPAREITEM"
  - "ON_WM_CONTEXTMENU"
  - "ON_WM_CREATE"
  - "ON_WM_CTLCOLOR"
  - "WM_ - сообщения"
ms.assetid: 4e315896-d646-4b87-b0ab-41a4a753b045
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Обработчики сообщений WM_ A — C
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записи следующего сопоставления слева соответствуют прототипам функции справа:  
  
|Запись сопоставления|Прототип функции|  
|--------------------------|----------------------|  
|ON\_WM\_ACTIVATE\(\)|afx\_msg пустое [OnActivate](../Topic/CWnd::OnActivate.md)\(UINT, CWnd\*, BOOL\);|  
|ON\_WM\_ACTIVATEAPP\(\)|afx\_msg пустое [OnActivateApp](../Topic/CWnd::OnActivateApp.md)\(BOOL, DWORD\);|  
|ON\_WM\_APPCOMMAND\(\)|afx\_msg пустое [OnAppCommand](../Topic/CWnd::OnAppCommand.md)\(CWnd\*, UINT, UINT, UINT\);|  
|ON\_WM\_ASKCBFORMATNAME\(\)|afx\_msg пустое [OnAskCbFormatName](../Topic/CWnd::OnAskCbFormatName.md)\(UINT, LPSTR\);|  
|ON\_WM\_CANCELMODE\(\)|afx\_msg пустое \( [OnCancelMode](../Topic/CWnd::OnCancelMode.md)\);|  
|ON\_WM\_CAPTURECHANGED\(\)|afx\_msg пустое [OnCaptureChanged](../Topic/CWnd::OnCaptureChanged.md)\(CWnd\*\);|  
|ON\_WM\_CHANGECBCHAIN\(\)|afx\_msg пустое [OnChangeCbChain](../Topic/CWnd::OnChangeCbChain.md)\(HWND, HWND\);|  
|ON\_WM\_CHAR\(\)|afx\_msg пустое [OnChar](../Topic/CWnd::OnChar.md)\(UINT, UINT, UINT\);|  
|ON\_WM\_CHARTOITEM\(\)|afx\_msg int [OnCharToItem](../Topic/CWnd::OnCharToItem.md)\(UINT, CWnd\*, UINT\);|  
|ON\_WM\_CHILDACTIVATE\(\)|afx\_msg пустое \( [OnChildActivate](../Topic/CWnd::OnChildActivate.md)\);|  
|ON\_WM\_CLIPBOARDUPDATE\(\)|afx\_msg пустое \( [OnClipboardUpdate](../Topic/CWnd::OnClipboardUpdate.md)\);|  
|ON\_WM\_CLOSE\(\)|afx\_msg пустое \( [OnClose](../Topic/CWnd::OnClose.md)\);|  
|ON\_WM\_COMPACTING\(\)|afx\_msg пустое [OnCompacting](../Topic/CWnd::OnCompacting.md)\(UINT\);|  
|ON\_WM\_COMPAREITEM\(\)|afx\_msg int [OnCompareItem](../Topic/CWnd::OnCompareItem.md)\(LPCOMPAREITEMSTRUCT\);|  
|ON\_WM\_CONTEXTMENU\(\)|afx\_msg пустое [OnContextMenu](../Topic/CWnd::OnContextMenu.md)\(CWnd\*, CPoint\);|  
|ON\_WM\_COPYDATA\(\)|afx\_msg BOOL [OnCopyData](../Topic/CWnd::OnCopyData.md)\(pWnd CWnd\*, pCopyDataStruct COPYDATASTRUCT\*\);|  
|ON\_WM\_CREATE\(\)|afx\_msg int [OnCreate](../Topic/CWnd::OnCreate.md)\(LPCREATESTRUCT\);|  
|ON\_WM\_CTLCOLOR\(\)|afx\_msg HBRUSH [OnCtlColor](../Topic/CWnd::OnCtlColor.md)\(CDC\*, CWnd\*, UINT\);|  
  
## См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)   
 [Обработчики для сообщений WM\_](../../mfc/reference/handlers-for-wm-messages.md)