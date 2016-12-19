---
title: "CPaintDC Class | Microsoft Docs"
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
  - "CPaintDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaintDC class"
  - "OnPaint handler"
  - "WM_PAINT message"
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPaintDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс устройство\- контекста, производный от [CDC](../Topic/CDC%20Class.md).  
  
## Синтаксис  
  
```  
class CPaintDC : public CDC  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPaintDC::CPaintDC](../Topic/CPaintDC::CPaintDC.md)|Создает `CPaintDC` подключенный к указанному [CWnd](../Topic/CWnd%20Class.md).|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CPaintDC::m\_ps](../Topic/CPaintDC::m_ps.md)|Содержит [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md), используемый для закрашивания клиентскую область.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CPaintDC::m\_hWnd](../Topic/CPaintDC::m_hWnd.md)|`HWND`, к которому этот объект `CPaintDC` вложить.|  
  
## Заметки  
 Она выполняет [CWnd::BeginPaint](../Topic/CWnd::BeginPaint.md) во время разработки и во время [CWnd::EndPaint](../Topic/CWnd::EndPaint.md) удаления.  
  
 Объект `CPaintDC` можно использовать только отвечающий на сообщение [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213), обычно в функции\-члене обработчика сообщений `OnPaint`.  
  
 Дополнительные сведения об использовании `CPaintDC` см. в разделе [контексты устройства](../Topic/Device%20Contexts.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDC](../Topic/CDC%20Class.md)  
  
 `CPaintDC`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [MFC, пытается интерфейс MDI](../../top/visual-cpp-samples.md)   
 [Класс CDC](../Topic/CDC%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)