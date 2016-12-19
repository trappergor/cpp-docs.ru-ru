---
title: "CMFCWindowsManagerDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCWindowsManagerDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCWindowsManagerDialog class"
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCWindowsManagerDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Объект `CMFCWindowsManagerDialog` позволяет пользователю управлять дочерние окна MDI в приложении MDI.  
  
## Синтаксис  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](../Topic/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog.md)|Создает объект `CMFCWindowsManagerDialog`.|  
  
## Заметки  
 `CMFCWindowsManagerDialog` содержит список дочерних окон MDI, которые в данный момент открыты в приложении.  Пользователь может вручную отслеживать состояние дочерних окон MDI с помощью этого диалогового окна.  
  
 `CMFCWindowsManagerDialog` внедрено в [Класс CMDIFrameWndEx](../Topic/CMDIFrameWndEx%20Class.md).  `CMFCWindowsManagerDialog` не является классом, который необходимо создать вручную.  Вместо этого вызовите функцию [CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md), и она создает и отображает объект `CMFCWindowsManagerDialog`.  
  
## Пример  
 В следующем примере показано, как создать объект `CMFCWindowsManagerDialog` путем вызова `CMDIFrameWndEx::ShowWindowsDialog`.  Этот фрагмент кода является частью [Пример demo Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/reference/codesnippet/CPP/cmfcwindowsmanagerdialog-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  
  
## Требования  
 **заголовок:** afxWindowsManagerDialog.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [Класс CMDIFrameWndEx](../Topic/CMDIFrameWndEx%20Class.md)   
 [CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md)